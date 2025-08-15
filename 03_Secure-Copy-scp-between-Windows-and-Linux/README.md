# Case 03 – Secure Copy (scp) between Windows and Linux

## Description
## Scenario
You need to securely transfer files between a Windows host and a Linux system over SSH using `scp`.  
This avoids manual copying with USB drives and ensures encrypted transfer.

---

## Pre-reqs
- SSH server running on the **target** machine (Linux by default, or OpenSSH installed on Windows).  
- Network connectivity between both systems.  
- Credentials (username/password or SSH key).

---

## 1) Find your IP address
You must replace the **IP placeholder** in the command with your machine's actual IP.

### On Windows (PowerShell / CMD):
```powershell
ipconfig

IPv4 Address. . . . . . . : 192.168.0.53

ip addr show
# or
hostname -I

192.168.0.53

scp .\Documents\seinfeld-characters.txt youruser@<your-IP-address>:/home/youruser/seinfeld

## Explanation:

scp → secure copy tool

.\Documents\seinfeld-characters.txt → source file on Windows (relative path)

youruser@<your-IP-address> → SSH login: replace youruser with your Linux username, <your-IP-address> with the Linux machine IP

/home/youruser/seinfeld → destination path on Linux

## 3) Reverse direction (Linux → Windows target)

If Windows has OpenSSH server enabled:

scp /home/youruser/seinfeld/final.txt windowsuser@<windows-IP>:/Users/windowsuser/Documents/

## 4) Notes

Default SSH port = 22. If changed, add -P 2222 (capital P).

You can use absolute paths (C:\Users\Raul\Documents) or relative ones (.\Documents).

For multiple files:

scp .\Documents\*.txt youruser@<your-IP-address>:/home/youruser/


## For directories (recursive):

scp -r project/ user@<your-IP>:/home/user/

## Security note

Password auth works, but SSH keys are recommended for automation.

Always check firewall rules (Linux ufw, Windows Defender Firewall).
 
