# Firewall Configuration

## Command Used to Allow SSH

```bash
sudo ufw allow ssh
```

## Commands Used to Set the Default Deny Policy

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

## Command Used to Allow Port 8080

```bash
sudo ufw allow 8080/tcp
```

## Why SSH Must Be Allowed Before Enabling UFW

If `sudo ufw enable` is run before `sudo ufw allow ssh`, the default deny incoming policy would immediately block the SSH connection itself, locking the administrator out of the server with no remaining way to reach it remotely to fix the mistake.
