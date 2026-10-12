# Laboratory 9: The Cloud Automation Engineer

## Mission Overview

As part of the Cloud Automation and DevOps Team at CloudNova Technologies, I eliminated a recurring human error — forgotten weekly backups — by writing a Bash script that automatically compresses a client's application data into a timestamped archive. I made the script executable, tested it manually, and scheduled it with cron to run automatically every night at 2:00 AM with no human intervention required.

## Objectives

- Understand the fundamental syntax of a Bash shell script, including variables and basic commands.
- Use a command-line text editor (nano) to write and save executable scripts.
- Modify Linux file permissions using the chmod command.
- Understand task scheduling and the syntax of a Linux crontab.
- Document automation code and Cron job configurations using Markdown.
- Complete the final chapter of a professional GitHub Cloud Computing Portfolio.

## Commands Executed

| Command | Purpose | Evidence |
|---|---|---|
| `mkdir app-data` | Create the dummy application data directory | - |
| `echo "This is critical client data." > app-data/data.txt` | Add a test file representing client data | - |
| `nano backup.sh` | Write the automated backup Bash script | - |
| `./backup.sh` (before chmod) | Confirm the script cannot run without execute permission | script-execution.png |
| `chmod +x backup.sh` | Grant execute permission to the script | script-execution.png |
| `./backup.sh` (after chmod) | Run the script and generate a compressed backup | script-execution.png |
| `ls -l backups/` | Verify the .tar.gz backup file was created | script-execution.png |
| `crontab -l` | Check existing cron jobs before scheduling | - |
| `env EDITOR=nano crontab -e` | Open the crontab editor to add the scheduled job | - |
| `0 2 * * * /root/work/automation-lab/backup.sh` | Schedule the backup script to run every night at 2:00 AM | cron-schedule.png |
| `crontab -l` (after scheduling) | Confirm the cron job was installed successfully | cron-schedule.png |

## Skills Learned

- Writing a Bash script with variables, comments, and shell commands
- Using `tar` to compress directories into timestamped archive files
- Understanding and applying Linux file permissions with chmod
- Scheduling recurring, unattended tasks using cron and crontab syntax
- Documenting automation code and scheduling logic clearly for a technical audience
- Completing an end-to-end GitHub Cloud Computing Portfolio spanning infrastructure, storage, deployment, operations, security, and automation

## Files

- [automation-research.md](automation-research.md)
- [backup-script-guide.md](backup-script-guide.md)
- [reflection.md](reflection.md)
- [screenshots/](screenshots/)
