## Purpose

Project that creates automated daily backups of the /etc directory.

## Tasks

- Bash backup script created
- Script manually tested
- Daily cron job configured
  
## Bash Script:

```bash

#!/bin/bash
#
# Script that creates daily automated backups of the /etc directory

# Variables

backupdir="home/gabi/backups/daily_etc_backups"
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

<img width="1140" height="259" alt="image" src="https://github.com/user-attachments/assets/9619684a-3ba6-4fc4-bea3-a5b07147c48a" />




## CRON

- sudo crontba -e -> edit and add "0 14 * * * /home/gabi/scripting_project/daily_etc_backup.sh" 
- check with sudo crontab -l 

<img width="852" height="596" alt="image" src="https://github.com/user-attachments/assets/15356bd8-f234-4245-9bf0-d60bd672e84e" />


