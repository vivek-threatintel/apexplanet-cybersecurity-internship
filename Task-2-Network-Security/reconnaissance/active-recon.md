````
# Active Reconnaissance Report

## Objective

The objective of this exercise was to perform active reconnaissance against the intentionally vulnerable Metasploitable 2 virtual machine inside the authorized `cyberlab` lab environment.

The assessment focused on identifying reachable network services, open TCP ports, service versions, and the exposed attack surface using Nmap.

---

## Lab Environment

| Parameter | Value |
|---|---|
| Target | Metasploitable 2 |
| Target IP | `192.168.100.20` |
| Network | `cyberlab` |
| Network Range | `192.168.100.0/24` |
| Scanner | Kali Linux |
| Scanner IP | `192.168.100.10` |
| Tool | Nmap 7.99 |
| Network Type | Private isolated lab |

The target and scanner were connected through the `cyberlab` virtual network.

---

## 1. Host Connectivity Verification

Before performing active reconnaissance, connectivity to the target was verified from Kali Linux:

```
ping -c 3 192.168.100.20
````

The target responded successfully:

```
3 packets transmitted, 3 received, 0% packet loss
```

This confirmed that the Metasploitable 2 system was reachable from the Kali testing workstation.

---

## 2. Service Enumeration

The first active reconnaissance scan used TCP SYN scanning together with service and version detection:

```
sudo nmap -sS -sV 192.168.100.20
```

### Scan Options

* `-sS` — TCP SYN scan
* `-sV` — Service and version detection
* `sudo` — Allows Nmap to perform privileged scanning operations

The scan identified the target as active and reported multiple exposed TCP services.

### Discovered Services

|     Port | Service    | Detected Version / Information      |
| -------: | ---------- | ----------------------------------- |
|   21/tcp | FTP        | vsftpd 2.3.4                        |
|   22/tcp | SSH        | OpenSSH 4.7p1 Debian 8ubuntu1       |
|   23/tcp | Telnet     | Linux telnetd                       |
|   25/tcp | SMTP       | Postfix smtpd                       |
|   53/tcp | DNS        | ISC BIND 9.4.2                      |
|   80/tcp | HTTP       | Apache httpd 2.2.8                  |
|  111/tcp | RPC        | rpcbind 2                           |
|  139/tcp | NetBIOS    | Samba 3.X - 4.X                     |
|  445/tcp | SMB        | Samba 3.X - 4.X                     |
|  512/tcp | Rexec      | netkit-rsh rexecd                   |
|  513/tcp | Rlogin     | OpenBSD or Solaris rlogind          |
|  514/tcp | Rsh        | Netkit rshd                         |
| 1099/tcp | Java RMI   | GNU Classpath grmiregistry          |
| 1524/tcp | Bindshell  | Metasploitable root shell           |
| 2049/tcp | NFS        | NFS 2-4                             |
| 2121/tcp | FTP        | ProFTPD 1.3.1                       |
| 3306/tcp | MySQL      | MySQL 5.0.51a-3ubuntu5              |
| 5432/tcp | PostgreSQL | PostgreSQL 8.3.0 - 8.3.7            |
| 5900/tcp | VNC        | VNC protocol 3.3                    |
| 6000/tcp | X11        | X11                                 |
| 6667/tcp | IRC        | UnrealIRCd                          |
| 8009/tcp | AJP13      | Apache Jserv                        |
| 8180/tcp | HTTP       | Apache Tomcat/Coyote JSP engine 1.1 |

The scan reported 977 closed TCP ports.

---

## 3. Targeted Service Enumeration

A second scan was performed against the identified service ports:

```
sudo nmap -p 21,22,23,25,53,80,139,445,3306,5432,5900,6667,8180 -sV 192.168.100.20
```

This targeted scan focused on commonly relevant network, remote-access, database, web, and application services identified during the initial enumeration.

The results confirmed the services and versions discovered during the broader service scan.

---

## 4. Key Observations

### Broad Service Exposure

The target exposes a large number of network services across multiple protocols, including:

* FTP
* SSH
* Telnet
* SMTP
* DNS
* HTTP
* SMB
* RPC
* NFS
* MySQL
* PostgreSQL
* VNC
* IRC
* Java RMI
* AJP
* Apache Tomcat

This represents a broad network-facing service surface.

### Legacy Services

Several services reported older software versions, including:

* vsftpd 2.3.4
* OpenSSH 4.7p1
* Apache httpd 2.2.8
* MySQL 5.0.51a
* PostgreSQL 8.3.x
* ProFTPD 1.3.1

These version findings provide useful input for the subsequent vulnerability-scanning phase.

### Legacy Remote Access Protocols

The scan identified:

* Telnet — `23/tcp`
* Rexec — `512/tcp`
* Rlogin — `513/tcp`
* Rsh — `514/tcp`

These services represent legacy remote-access protocols and require security review in a real production environment.

### Database Services

Two database services were directly reachable from the scanner:

* MySQL — `3306/tcp`
* PostgreSQL — `5432/tcp`

Database services should generally be restricted to systems and networks that require access.

### Web and Application Services

The target exposes several web/application-related services:

* HTTP — `80/tcp`
* AJP13 — `8009/tcp`
* Apache Tomcat — `8180/tcp`

These services provide targets for subsequent vulnerability assessment.

---

## 5. Security Relevance

Active reconnaissance provides information about the externally reachable attack surface of a system.

The discovered ports and service versions can be used to:

1. Build a service inventory.
2. Identify legacy or unnecessary services.
3. Select appropriate vulnerability checks.
4. Prioritize further security assessment.
5. Correlate exposed services with known vulnerabilities.

The reconnaissance results alone do not establish that every identified service is vulnerable or exploitable.

---

## 6. Evidence

The following evidence was collected during the assessment:

```
Task-2-Network-Security/screenshots/21-active-recon.png
Task-2-Network-Security/screenshots/22-active-recon-targeted.png
Task-2-Network-Security/reports/active-recon-services.txt
```

### Screenshot 21

`21-active-recon.png`

Contains the primary active reconnaissance/service enumeration results.

### Screenshot 22

`22-active-recon-targeted.png`

Contains the targeted enumeration results for selected service ports.

### Raw Scan Output

`active-recon-services.txt`

Contains the saved Nmap service-enumeration output.

---

## 7. Conclusion

Active reconnaissance of the Metasploitable 2 system was successfully completed within the isolated `cyberlab` environment.

The assessment identified:

* A reachable target at `192.168.100.20`
* 23 exposed TCP services
* Service names and detected versions
* Multiple legacy network services
* Web and application services
* Database services
* Remote-access services

The collected service inventory provides the required foundation for further vulnerability assessment and security analysis.
