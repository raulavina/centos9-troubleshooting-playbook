# Case 06 – User Context Basics (`whoami`, `pwd`, `su -`, `su - <user>`)

## Scenario
While troubleshooting on CentOS 9, you need to confirm which user you are, where you are located in the filesystem, and then switch to another user (commonly root or a service account) with the proper login environment.

## Description
- `whoami`: Displays the **effective username** of the current shell session.  
- `pwd`: Prints the **current working directory**.  
- `su -`: Switches to another user with a **full login shell** (loads environment, PATH, HOME). Defaults to **root** if no user is specified.  
- `su - <user>`: Same as above, but explicitly changes to `<user>` (e.g., `su - raulavina`).

These commands are typically used together to verify identity, location, and correct environment when escalating privileges or moving between accounts.

## Steps

1. Confirm current user:

```bash
whoami

2. Confirm current directory:

pwd

3. Switch to root with login shell:

su -
# enter root password

4. Switch to a specific user (example: raulavina):

su - raulavina
# enter raulavina's password

5. Verify after switching:

whoami
# should now show root or raulavina
pwd      
# should change to that user’s HOME (e.g., /root or /home/raulavina)

6. Exit back to previous user:

exit
