# Task 2 — Network Security & Scanning

## Objective

Learn reconnaissance, network scanning, vulnerability assessment, packet analysis, and basic firewall configuration in an authorized cybersecurity lab environment.

---

## Task Scope

### 1. Reconnaissance

#### Passive Reconnaissance
- WHOIS
- Nslookup
- Google Dorking
- Shodan

#### Active Reconnaissance
- Ping sweep
- Banner grabbing

### 2. Port & Service Scanning

- Nmap TCP scanning
- Nmap UDP scanning
- Service and version detection
- Operating system detection
- Scan report and analysis

### 3. Vulnerability Scanning

- Vulnerability scanner setup
- Metasploitable 2 vulnerability assessment
- Vulnerability analysis by severity:
  - Critical
  - High
  - Medium
  - Low

### 4. Packet Analysis with Wireshark

- HTTP traffic capture
- FTP traffic capture
- DNS traffic capture
- Analysis of credentials in unencrypted FTP traffic
- SYN flood traffic analysis using an authorized lab simulation

### 5. Firewall Basics

- Basic iptables rules
- Allow/deny specific ports
- Demonstration of blocking a port scan

---

## Lab Environment

The practical exercises will be performed in an isolated and authorized cybersecurity laboratory.

Planned lab components:

- Kali Linux — Security testing workstation
- Metasploitable 2 — Vulnerable target system
- QEMU/KVM — Virtualization platform
- `cyberlab` — Isolated private lab network
- Nmap — Network scanning
- Wireshark — Packet analysis
- Nessus/OpenVAS — Vulnerability assessment
- iptables — Firewall configuration

---

## Repository Structure

```text
Task-2-Network-Security/
├── README.md
├── reconnaissance/
│   ├── passive-recon.md
│   └── active-recon.md
├── nmap/
│   └── scan-report.md
├── vulnerability-scanning/
│   └── vulnerability-report.md
├── wireshark/
│   └── packet-analysis.md
├── firewall/
│   └── iptables.md
├── screenshots/
└── reports/
