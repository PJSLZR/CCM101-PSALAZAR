# Laboratory 10: The Enterprise Cloud Architect 

## Mission Overview

As the final mission of the CCM101 Cloud Computing course, I independently designed, deployed, secured, and automated a complete multi-tier enterprise infrastructure from scratch, without step-by-step instructions. The stack consists of a WordPress application tier and a MySQL database tier, deployed via Docker Compose on a self-provisioned Ubuntu Server virtual machine, hardened with a UFW firewall, and backed up nightly through a custom Bash automation script scheduled with cron.

## Architecture

See [architecture-diagram.png](architecture-diagram.png) for the full topology: host machine → VirtualBox hypervisor → Ubuntu Server VM → UFW firewall → Docker Engine → WordPress + MySQL containers with a persistent volume.

## Stack Chosen

**WordPress + MySQL**, deployed via Docker Compose with a named persistent volume for the database.

## Requirements Met

- [x] Architecture diagram and VM provisioning (Ubuntu Server under VirtualBox)
- [x] Multi-tier deployment via Docker Compose with persistent volumes
- [x] UFW firewall with default-deny policy, SSH + app port only
- [x] Automated nightly database backup via Bash script + cron
- [x] Full operational manual and final reflection

## Files

- [architecture-diagram.png](architecture-diagram.png) — network topology
- [docker-compose.yml](docker-compose.yml) — multi-tier infrastructure as code
- [automation-script.sh](automation-script.sh) — automated database backup
- [operational-manual.md](operational-manual.md) — deployment, security, and recovery guide
- [final-reflection.md](final-reflection.md) — synthesis of the full semester
