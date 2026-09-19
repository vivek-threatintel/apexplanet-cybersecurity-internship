# Linux Fundamentals

> Essential Linux command-line skills for cybersecurity labs, system administration, and security testing.

---

## Objective

Develop basic Linux command-line skills required for cybersecurity labs, system administration, and security testing.

---

## 1. File System Navigation

### pwd

Displays the current working directory.

Example:

    pwd

### ls

Lists files and directories in the current directory.

Examples:

    ls
    ls -la

`ls -la` also displays hidden files and detailed file information.

### cd

Changes the current working directory.

Examples:

    cd /tmp
    cd ..
    cd ~

---

## 2. File Permissions and Ownership

Linux uses file permissions to control access to files and directories.

### chmod

Changes file or directory permissions.

Examples:

    chmod 644 example.txt
    chmod +x script.sh

`chmod +x` adds execute permission to a file.

### chown

Changes the owner and/or group of a file.

Example:

    sudo chown user:group example.txt

Example used during practical verification:

    sudo chown root:root example.txt

---

## 3. Package Management

### apt

`apt` is used to install, update, remove, and manage packages on Debian-based Linux systems.

Examples:

    sudo apt update
    sudo apt install nmap
    sudo apt remove nmap

### dpkg

`dpkg` is a low-level Debian package management tool.

Examples:

    dpkg -l
    dpkg -i package.deb

`dpkg -l` can be used to list installed packages.

---

## 4. Network Commands

### ifconfig

Displays network interface configuration.

Example:

    ifconfig

Note:

`ifconfig` is a legacy utility. The modern alternative is `ip`.

### ping

Tests basic network connectivity between systems.

Example:

    ping -c 4 127.0.0.1

### netstat

Displays network connections, listening ports, routing information, and network statistics.

Example:

    netstat -tuln

Note:

`netstat` is a legacy utility. The modern alternative is `ss`.

### traceroute

Shows the network hops between the local system and a destination.

Example:

    traceroute 8.8.8.8

---

## 5. Cybersecurity Relevance

Linux command-line skills are important for:

- Security lab environments
- System administration
- Network troubleshooting
- File and permission analysis
- Package management
- Process and service investigation
- Network reconnaissance
- Security testing

---

## 6. Command Summary

| Command | Purpose |
|---|---|
| `pwd` | Display current working directory |
| `ls` | List files and directories |
| `cd` | Change directory |
| `chmod` | Modify file permissions |
| `chown` | Change file ownership |
| `apt` | Manage packages |
| `dpkg` | Manage Debian packages |
| `ifconfig` | Display network interfaces |
| `ping` | Test network connectivity |
| `netstat` | Display network connections and ports |
| `ss` | Display network sockets |
| `traceroute` | Trace the network path |

---

## 7. Practical Verification

The Linux commands were tested on the Kali Linux security workstation.

Practical verification covered:

- File system navigation
- File permissions
- File ownership
- Package management
- Network interface information
- Network connectivity
- Listening ports and connections
- Network path tracing

### Verified Commands

| Command | Verification |
|---|---|
| `pwd` | Current working directory verified |
| `ls -la` | Directory contents and hidden files verified |
| `cd` | Directory navigation verified |
| `chmod 600` | File permission changes verified |
| `chmod +x` | Execute permission verified |
| `chown root:root` | File ownership change verified |
| `sudo apt update` | Package list update verified |
| `dpkg -l` | Installed Debian packages verified |
| `ip addr` | Network interfaces verified |
| `ping -c 4 127.0.0.1` | Network connectivity verified |
| `ss -tuln` | Listening TCP/UDP sockets verified |
| `traceroute 8.8.8.8` | Network path verified |
| `ifconfig` | Network interface configuration verified |

---

## 8. Practical Evidence

Screenshots documenting the Linux practical exercises are stored in:

    Task-1-Foundations/screenshots/

The evidence includes practical verification of Linux navigation, permissions, ownership, package management, and networking commands.

---

## Verification Status

| Area | Status |
|---|---|
| File system navigation | Completed |
| File permissions | Completed |
| File ownership | Completed |
| Package management | Completed |
| Network commands | Completed |
| Practical verification | Completed |
| Screenshot evidence | Completed |

---

## Conclusion

The Linux fundamentals required for the cybersecurity lab environment were documented and practically verified on Kali Linux.

The exercises covered file system navigation, permissions and ownership, Debian package management, network configuration, connectivity testing, socket inspection, and network path tracing.
