# Case 01 - Reset Linux Password

## Scenario
A user forgot their password on a CentOS 7 system. They cannot access the system and require immediate recovery.

## Solution
1. Log in as root or a user with `sudo` privileges.
2. Reset the password:
```bash
sudo passwd username
