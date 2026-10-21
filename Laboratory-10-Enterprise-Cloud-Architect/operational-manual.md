# Operational Manual — Enterprise WordPress + MySQL Infrastructure

## Overview

This infrastructure runs a multi-tier WordPress + MySQL application on a dedicated Ubuntu Server virtual machine, hosted under VirtualBox on local hardware. The server is hardened with a host-based firewall and automatically backs up its own database every night.

## Architecture

See `architecture-diagram.png`. The host machine runs VirtualBox (Type 2 hypervisor), which runs an Ubuntu Server VM. Inside the VM, UFW enforces a default-deny firewall policy, and Docker Engine runs two linked containers: `wordpress` (web/app tier, exposed on port 8080) and `db` (MySQL database tier, internal-only, backed by a persistent named volume `db_data`). A cron job on the VM's host OS runs a Bash backup script nightly.

## Deployment

1. Provision an Ubuntu Server VM (2+ GB RAM, 20+ GB disk) under VirtualBox with bridged or port-forwarded networking.
2. Install Docker: `sudo apt-get install -y docker.io docker-compose-plugin`, then `sudo systemctl enable --now docker`.
3. Copy `docker-compose.yml` into a working directory on the VM (e.g. `~/enterprise-stack/`).
4. Run `docker compose up -d`.
5. Access the application at `http://<VM-IP>:8080`.

## Security Configuration

The firewall is configured with UFW using a default-deny-incoming policy. Only two ports are explicitly allowed:

- **22 (SSH)** — for remote administration.
- **8080 (HTTP)** — for the WordPress application.

The MySQL database (port 3306) is never exposed to the host or the network — it has no `ports:` mapping in `docker-compose.yml`, so it is reachable only from the `wordpress` container over Docker's internal network. Setup commands:

```bash
sudo ufw allow ssh
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow 8080/tcp
sudo ufw enable
```

## Persistent Storage

The `db_data` named Docker volume stores all MySQL data outside the container's writable layer. This means the database survives `docker compose down`, container recreation, and a full VM reboot — only an explicit `docker compose down -v` would remove it.

## Backup and Automation

`automation-script.sh` runs nightly at 2:00 AM via cron. It uses `docker exec` to run `mysqldump` inside the running `db` container, compresses the resulting SQL dump with gzip, stores it in `~/backups/`, and automatically deletes backups older than 7 days to prevent unbounded disk growth.

Cron entry:
```
0 2 * * * /home/<username>/scripts/backup.sh
```

## Disaster Recovery

To restore from a backup:

```bash
gunzip -c ~/backups/db_backup_YYYYMMDD_HHMMSS.sql.gz | docker exec -i enterprise-db mysql -uroot -p"CloudNova2026Root!" wordpress_db
```

## Known Limitations / Production Notes

Database credentials are stored in plain text in `docker-compose.yml` and `automation-script.sh` for this lab. In a production deployment, these would be moved to a `.env` file excluded from version control via `.gitignore`, or managed with a dedicated secrets manager (e.g. Docker Secrets, HashiCorp Vault). TLS/HTTPS is also not configured here; a production deployment would sit behind a reverse proxy (e.g. Nginx or Caddy) handling certificates via Let's Encrypt.
