# Case 02 – ifconfig (Network Interfaces) on CentOS 9

## Description
Use `ifconfig` (from **net-tools**) to inspect and toggle network interfaces. Shows IP, MAC, MTU, and RX/TX stats.


## Steps
1. Show active interfaces
   ```bash
   ifconfig

2. Show all interfaces (including down)
  ```bash
ifconfig -a

3. Show a specific interface (example: eth0)
  ```bash
ifconfig eth0

4. Bring an interface up or down (requires sudo)
  ```bash
sudo ifconfig eth0 up
  ```bash
sudo ifconfig eth0 down

** On CentOS 9, ifconfig is part of the net-tools package.

The modern replacement is the ip command (ip a, ip link).
