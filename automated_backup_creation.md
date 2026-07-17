## Purpose

Project that creates automated daily backups of the /etc directory.

## Tasks

- Script created
- Manually tested
- Cron configuration

## Bash Script:

```bash

#!/bin/bash
#
# Scripts that creates daily automated backups for /etc directory

# Variables

backupdir="$HOME/backups/daily_etc_backups"
date=$(date +%Y%m%d)
newbackupname="etc_backup_${date}.tar.gz"

# Backup Directory check

if [ -e "$backupdir" ]
        then echo "Directory Exists"
        else
                mkdir "$backupdir"
                echo "Backup directory created"
fi

# Backup Creation

if [ -e "$backupdir" ]
        then tar -czf "$backupdir/$newbackupname" /etc
                echo "Archive created"
                exit 0
        else echo "Archive was not created"
                exit 1
fi

```

## Tested Scenarios

Manually tested the script:

<img width="772" height="122" alt="image" src="https://github.com/user-attachments/assets/7545890c-5f8a-4318-84f3-00b206ac078d" />
<img width="742" height="72" alt="image" src="https://github.com/user-attachments/assets/797e0853-f82c-4b87-b40e-565a6112d30e" />



## CRON

- sudo crontba -e -> edit and add "0 14 * * * /home/gabi/scripting_project/daily_etc_backup.sh" 
- check with sudo crontab -l 

<img width="940" height="624" alt="image" src="https://github.com/user-attachments/assets/0b2f72c2-0a48-4976-ae93-f73b0d073aeb" />

