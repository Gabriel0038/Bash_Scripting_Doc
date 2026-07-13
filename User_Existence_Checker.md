## Purpose

Check whether a specified Linux user exists on the system.

## Bash Script:

```bash
#!/bin/bash
# Checks if a specified Linux user exists.
#
username=$1
if grep "$username" /etc/passwd
then
        echo "User is present."
        exit 0
else
        echo "User is not present."
        exit 1
fi
```

## Explenation

- Created a variable username and attached an argument to it. 
- Used grep to check the username in /etc/passwd
- If-Then-Else statement to echo results massage with exit status attached 

## Results:

<img width="591" height="174" alt="image" src="https://github.com/user-attachments/assets/fe7f153a-2d8d-4286-82d0-7e6fc6807213" />

