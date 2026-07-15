## Purpose

Check whether a specified Linux user exists on the system

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

## Usage

```bash
./user_check.sh gabi
./user_check.sh root
./user_check.sh alex
```

## Details

- Stores the username passed as a command-line argument
- Uses `grep` to search `/etc/passwd`
- Uses an `if-then-else` statement
- Returns `0` if the user exists, `1` otherwise

## Results:

<img width="591" height="174" alt="image" src="https://github.com/user-attachments/assets/fe7f153a-2d8d-4286-82d0-7e6fc6807213" />

