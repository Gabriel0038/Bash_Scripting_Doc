# Basic script that checks if a user exists on the server or not #

## Bash Script ## 

#!/bin/bash
# User Existence Checker
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

# Explenation #

- Created a variable username and attached an argument to it. 
- Used grep to check the username in /etc/passwd
- If-Then-Else statement to echo results massage with exit status attached 
