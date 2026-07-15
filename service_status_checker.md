## Purpose

Check if a service status is active or not and specify if the argument was used.  

## Bash Script:

```bash
#!/bin/bash
# Service Status Checker

service=$1

if [ -z "$service" ]
then echo "./service_check.sh <service_name>"
exit
fi


if systemctl -q is-active $service
then echo "Service is Active"
        exit 0
else echo "Service is Inactive"
        exit 1
fi

```

## Details

- used [ -z service ] to check the argument condition

## Results:

<img width="668" height="113" alt="image" src="https://github.com/user-attachments/assets/167b46ed-5504-43d8-b8fc-a53a59104749" />

