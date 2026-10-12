# Research: The Language of Automation

## Bash Script

A Bash script is a plain text file containing a sequence of Linux commands that the shell executes in order, automating tasks that would otherwise require typing each command manually. The `#!/bin/bash` line at the top, called the shebang, tells the operating system which interpreter should run the file — in this case, the Bash shell — so it knows how to execute the script correctly regardless of what shell the user is currently using.

## Variables

Programmers use variables like `$BACKUP_DIR` instead of repeatedly typing an exact folder path because it makes the script easier to read, maintain, and change. If the backup location ever needs to move, only the single variable assignment has to be updated instead of every line in the script that references that path, which also reduces the risk of typos causing the script to fail silently.

## Cron Job

A cron job is a scheduled task in Linux, managed by the cron daemon, that runs a specified command or script automatically at a defined time or interval without any manual action. It is essential for cloud operations because it removes human error and forgetfulness from repetitive maintenance tasks, such as backups, log rotation, or health checks, ensuring they happen reliably even outside of business hours.
