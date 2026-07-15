## Purpose

Check if a log file exists, the size of it and the amount of lines registered  

## Bash Script:

```bash
#!/bin/bash
# Log File Checker

logfile=$1

if [ -z "$logfile" ]
then echo "Please add log path and use the command as follows: ./log_check.sh <log_path>"
exit
fi

if [ -f "$logfile" ]
then echo "Log File exists"
        size=$(ls -l $logfile)
        echo "$size"
        lines=$(wc -l $logfile)
        echo "$lines"
        exit 0
else echo "File doesn't exist"
        exit 1
fi

```

## Details

- Used [ -f "logfile" ] to check if the log exists

- Used ls and wc commands for size and lines variables, and echo to display the results


## Results:

<img width="742" height="114" alt="image" src="https://github.com/user-attachments/assets/b74d50f9-320a-4646-94dd-d7b4de456fd8" />
