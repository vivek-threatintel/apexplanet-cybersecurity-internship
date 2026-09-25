# Nmap Scan Report

## Objective

The objective of this exercise was to perform network discovery, TCP port scanning, service/version detection, and operating system identification against the intentionally vulnerable Metasploitable 2 virtual machine inside the authorized `cyberlab` lab environment.

## Target Information

| Parameter | Value |
|---|---|
| Target | Metasploitable 2 |
| Target IP | `192.168.100.20` |
| Network | `cyberlab` |
| Network Range | `192.168.100.0/24` |
| Scanner | Kali Linux |
| Scanner IP | `192.168.100.10` |
| Tool | Nmap 7.99 |
| Network Distance | 1 hop |

## Network Discovery

Before scanning the target, host discovery was performed against the private lab network:

```bash
nmap -sn 192.168.100.0/24
```

The scan identified three active hosts:

- `192.168.100.1` — cyberlab gateway
- `192.168.100.10` — Kali Linux
- `192.168.100.20` — Metasploitable 2

This confirmed that the Metasploitable 2 VM was reachable from the Kali Linux testing workstation through the `cyberlab` network.

## Detailed Nmap Scan

The following command was used:

```bash
sudo nmap -sS -sV -O 192.168.100.20
```

### Scan Options

- `-sS` — TCP SYN scan
- `-sV` — Service and version detection
- `-O` — Operating system detection
- `sudo` — Required for privileged scanning operations

## Scan Result

The target was reachable and Nmap identified **23 open TCP services**.

A total of **977 TCP ports were reported closed**.

| Port | Service | Version / Information |
|---:|---|---|
| 21/tcp | FTP | vsftpd 2.3.4 |
| 22/tcp | SSH | OpenSSH 4.7p1 Debian 8ubuntu1 |
| 23/tcp | Telnet | Linux telnetd |
| 25/tcp | SMTP | Postfix smtpd |
| 53/tcp | DNS | ISC BIND 9.4.2 |
| 80/tcp | HTTP | Apache httpd 2.2.8 |
| 111/tcp | RPC | rpcbind 2 |
| 139/tcp | NetBIOS | Samba 3.X - 4.X |
| 445/tcp | SMB | Samba 3.X - 4.X |
| 512/tcp | Rexec | netkit-rsh rexecd |
| 513/tcp | Rlogin | OpenBSD/Solaris rlogind |
| 514/tcp | Rsh | Netkit rshd |
| 1099/tcp | Java RMI | GNU Classpath grmiregistry |
| 1524/tcp | Bindshell | Metasploitable root shell |
| 2049/tcp | NFS | NFS v2-4 |
| 2121/tcp | FTP | ProFTPD 1.3.1 |
| 3306/tcp | MySQL | MySQL 5.0.51a-3ubuntu5 |
| 5432/tcp | PostgreSQL | PostgreSQL 8.3.0 - 8.3.7 |
| 5900/tcp | VNC | VNC protocol 3.3 |
| 6000/tcp | X11 | X11 |
| 6667/tcp | IRC | UnrealIRCd |
| 8009/tcp | AJP13 | Apache Jserv |
| 8180/tcp | HTTP | Apache Tomcat/Coyote JSP engine 1.1 |

## Operating System Detection

Nmap identified the target as a general-purpose Linux system.

Detected information:

```text
Device type: General purpose
Running: Linux 2.6.X
OS details: Linux 2.6.9 - 2.6.33
Network Distance: 1 hop
```

The target MAC address was identified as:

```text
52:54:00:6C:41:AF
```

The vendor information indicates a QEMU virtual NIC, consistent with the Metasploitable 2 VM running in the QEMU/KVM lab environment.

## Key Observations

### 1. Large Exposed Service Surface

The target exposes numerous network services across different ports, including:

- FTP
- SSH
- Telnet
- SMTP
- DNS
- HTTP
- SMB
- RPC
- NFS
- Database services
- VNC
- IRC
- Java RMI
- Apache AJP/Tomcat

This creates a large service attack surface compared with a minimally exposed server.

### 2. Legacy Services

Several detected services report older software versions, including:

- vsftpd 2.3.4
- OpenSSH 4.7p1
- Apache 2.2.8
- MySQL 5.0.51a
- PostgreSQL 8.3.x
- UnrealIRCd
- ProFTPD 1.3.1

These versions should be treated as legacy software requiring further vulnerability assessment rather than automatically classified as exploitable based only on version detection.

### 3. Insecure/Legacy Network Services

The scan identified services such as:

- Telnet on port 23
- Rlogin on port 513
- Rsh on port 514
- Rexec on port 512

These protocols are generally associated with legacy remote-access architectures and should receive additional security review in a real environment.

### 4. Database Exposure

The following database services were externally reachable from the lab scanner:

- MySQL — `3306/tcp`
- PostgreSQL — `5432/tcp`

Database exposure should normally be restricted to systems and networks that require access.

### 5. Web Services

Multiple web-related services were identified:

- HTTP — `80/tcp`
- AJP13 — `8009/tcp`
- Apache Tomcat — `8180/tcp`

These services will be considered for further vulnerability assessment in the vulnerability-scanning phase.

## Security Assessment

The Nmap results demonstrate that the intentionally vulnerable Metasploitable 2 system has a broad network attack surface.

The scan itself does not prove that every detected service is vulnerable. Version information provides a basis for the next stage of assessment, where vulnerability scanners and targeted validation can be used.

## Evidence

Screenshots documenting the Nmap activity are stored in:

```text
Task-2-Network-Security/screenshots/
```

Relevant evidence includes:

- Network discovery
- TCP scanning
- Service/version detection
- OS detection
- Detailed Nmap scan

## Conclusion

The Nmap assessment successfully identified the active Metasploitable 2 host, its exposed TCP services, detected software versions, and probable operating system family.

The results provide the service inventory required for the next phase of Task 2: vulnerability scanning and vulnerability report analysis.
