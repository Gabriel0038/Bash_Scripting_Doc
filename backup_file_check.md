## Purpose

Script that verify the backup files are existing, empty or not empty (valid)

## Bash Script:

```bash
#! /bin/bash
#
# Backup Check Script
#
backupfile=$1
#

# In case of no file path added
if [ -z "$backupfile" ]
then echo "No path file added, please use the following command: ./backup_check.sh <backup_path>"
        exit 1
fi

# In case of path does not exists

if [ -f "$backupfile" ]
        then echo "File exists."
                if [ -s "$backupfile" ]
                then echo "Backup file valid"
                else echo "Backup file empty"
                fi
        else echo "Backup file not found"
fi

```

## Usage

```bash
sudo ./backup_check.sh ~/backups/empty_backup.tar.gz
sudo ./backup_check.sh ~/backups/etc_backup.tar.gz
sudo ./backup_check.sh ~/backups/back.tar.gz
sudo ./backup_check.sh

```

## Details

- used -z test condition to check if backup path is empty or not
- used -f test condition to check if the file exists and it is a file
- used -s test condition to check if file is empty or not


## Results:

<img width="1163" height="233" alt="image" src="https://github.com/user-attachments/assets/1472e3bb-1de5-444a-a84d-114638db08b5" />

