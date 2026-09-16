LINUX FUNDAMENTALS

Objective

Develop basic Linux command-line skills required for cybersecurity labs, system administration, and security testing.


1. FILE SYSTEM NAVIGATION

pwd

Purpose:
Displays the current working directory.

Example:
pwd


ls

Purpose:
Lists files and directories in the current directory.

Examples:
ls
ls -la


cd

Purpose:
Changes the current working directory.

Examples:
cd /tmp
cd ..
cd ~


2. FILE PERMISSIONS AND OWNERSHIP

chmod

Purpose:
Changes file or directory permissions.

Examples:
chmod 644 example.txt
chmod +x script.sh


chown

Purpose:
Changes the owner and/or group of a file.

Example:
sudo chown user:group example.txt


3. PACKAGE MANAGEMENT

apt

Purpose:
Used to install, update, remove, and manage packages on Debian-based Linux systems.

Examples:
sudo apt update
sudo apt install nmap
sudo apt remove nmap


dpkg

Purpose:
A low-level Debian package management tool.

Examples:
dpkg -l
dpkg -i package.deb


4. NETWORK COMMANDS

ifconfig

Purpose:
Displays network interface configuration.

Example:
ifconfig

Note:
ifconfig is a legacy command. The modern alternative is the ip command.


ping

Purpose:
Tests network connectivity between systems.

Example:
ping -c 4 127.0.0.1


netstat

Purpose:
Displays network connections, listening ports, routing information, and network statistics.

Example:
netstat -tuln

Note:
netstat is a legacy utility. The modern alternative is ss.


traceroute

Purpose:
Shows the network hops between the local system and a destination.

Example:
traceroute 8.8.8.8


5. COMMAND SUMMARY

pwd        - Display current working directory
ls         - List files and directories
cd         - Change directory
chmod      - Modify file permissions
chown      - Change file ownership
apt        - Manage packages
dpkg       - Manage Debian packages
ifconfig   - Display network interfaces
ping       - Test network connectivity
netstat    - Display network connections and ports
traceroute - Trace the network path to a destination


6. PRACTICAL VERIFICATION

The above commands will be tested on the Kali Linux security workstation.

Practical verification will cover:

- File system navigation
- File permissions
- File ownership
- Package management
- Network interface information
- Network connectivity
- Listening ports and connections
- Network path tracing


STATUS

Documentation prepared.

Practical verification completed:

- pwd — verified current working directory
- ls -la — verified directory contents and hidden files
- cd — verified directory navigation
- chmod 600 — verified file permission changes
- chmod +x — verified execute permission
- chown root:root — verified file ownership change
- sudo apt update — verified package list update
- dpkg -l — verified installed Debian packages
- ip addr — verified network interfaces
- ping -c 4 127.0.0.1 — verified network connectivity
- ss -tuln — verified listening TCP/UDP sockets
- traceroute 8.8.8.8 — verified network path
- ifconfig — verified network interface configuration

All listed Linux fundamentals were practically verified on the Kali Linux workstation.
