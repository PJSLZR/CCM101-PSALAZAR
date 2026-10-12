# Backup Script Guide

## Full Script Code

```bash
#!/bin/bash
# Automated Backup Script for CloudNova Technologies

SOURCE_DIR="app-data"
BACKUP_DIR="backups"
TIMESTAMP=$(date +"%Y%m%d_%H%M%S")

echo "Initiating automated backup..."

# Create the backup directory if it does not exist
mkdir -p $BACKUP_DIR

# Compress the source directory into a tarball (.tar.gz)
tar -czf $BACKUP_DIR/backup_$TIMESTAMP.tar.gz $SOURCE_DIR

echo "Backup completed successfully at $TIMESTAMP!"
```

## What `chmod +x` Did

By default, Linux does not allow a text file to be run as a program, even if it contains valid shell commands, as a safety measure. The `chmod +x backup.sh` command adds the execute permission to the file, which tells the operating system it is now allowed to be run directly as a script with `./backup.sh`, rather than only being readable as plain text.

## Cron Expression Breakdown

The scheduled job used:| Field | Value | Meaning |
|---|---|---|
| Minute | `0` | At minute 0 of the hour |
| Hour | `2` | At 2 AM |
| Day of Month | `*` | Every day of the month |
| Month | `*` | Every month |
| Day of Week | `*` | Every day of the week |

Together, this runs `backup.sh` automatically every single night at exactly 2:00 AM, with no manual action required.
