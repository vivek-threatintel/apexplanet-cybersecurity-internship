# Nmap

> Network discovery and security auditing tool used for host discovery, port scanning, service enumeration, and version detection.

---

## Objective

Understand the basic use of Nmap for network discovery and service enumeration in an authorized cybersecurity lab.

---

## 1. What is Nmap?

Nmap (Network Mapper) is a network discovery and security auditing tool.

It can be used to identify:

- Live hosts
- Open ports
- Running services
- Service versions
- Operating system information

Nmap should only be used against systems that are owned by you or where you have explicit authorization to test.

---

## 2. Basic Commands

### Nmap Version

Displays the installed Nmap version.

    nmap --version

### Scan a Target

Performs a basic scan against a target.

    nmap <target>

### Service and Version Detection

Attempts to identify services and their versions on open ports.

    nmap -sV <target>

---

## 3. Practical Lab

The Nmap exercises were performed against the authorized Metasploitable 2 lab environment.

Lab network:

    192.168.100.0/24

Target:

    192.168.100.20

The lab uses an isolated virtual network to prevent the vulnerable target from being exposed to the external network.

---

## 4. Practical Verification

### Nmap Version

    nmap --version

Verified that Nmap is installed and available on the Kali Linux workstation.

### Localhost Scan

    nmap 127.0.0.1

Used to perform a basic scan against the local Kali system.

### Service Detection

    nmap -sV 192.168.100.20

Used against the authorized Metasploitable 2 target to identify exposed services and their versions.

---

## 5. Practical Evidence

Screenshots:

- `screenshots/11-nmap-version (1).png`
- `screenshots/12-nmap-localhost.png`
- `screenshots/13-nmap-service-detection.png`

---

## Security Relevance

Nmap is useful for:

- Network discovery
- Attack-surface identification
- Port enumeration
- Service enumeration
- Security assessment
- Lab reconnaissance

---

## Verification Status

| Area | Status |
|---|---|
| Nmap installation/version | Completed |
| Localhost scan | Completed |
| Service/version detection | Completed |
| Practical evidence | Completed |

---

## Conclusion

Nmap was used in an authorized isolated lab environment to verify installation, perform a local scan, and enumerate services on the Metasploitable 2 target.
