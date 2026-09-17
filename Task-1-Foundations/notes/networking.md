NETWORKING FUNDAMENTALS

Objective

Understand the networking concepts, protocols, and command-line utilities commonly used in cybersecurity.


1. CORE NETWORKING CONCEPTS

IP Address

An IP address identifies a network interface on an IP network.

Example:
192.168.1.10


MAC Address

A MAC address identifies a network interface at the Data Link layer.

Example:
00:11:22:33:44:55


Subnet

A subnet divides an IP network into smaller logical networks.

Example:
192.168.1.0/24


Default Gateway

The default gateway is the device used to forward traffic from the local network to other networks.


DNS

DNS (Domain Name System) translates domain names into IP addresses.

Example:
example.com → IP address


2. COMMON NETWORK PROTOCOLS

TCP
Purpose: Reliable, connection-oriented transport.

UDP
Purpose: Connectionless transport with low overhead.

HTTP
Purpose: Web communication.

HTTPS
Purpose: HTTP secured using TLS.

DNS
Purpose: Domain-name resolution.

SSH
Purpose: Secure remote administration.


3. NETWORK COMMANDS

ip addr

Purpose:
Displays network interfaces and assigned IP addresses.

Command:
ip addr

Practical verification:
Verified on the Kali Linux workstation.


ping

Purpose:
Tests basic network connectivity.

Command:
ping -c 4 127.0.0.1

Result:
4 packets transmitted, 4 received, 0% packet loss.


ss

Purpose:
Displays network sockets and listening ports.

Command:
ss -tuln

Practical verification:
Command executed successfully on Kali Linux.


traceroute

Purpose:
Displays the network path to a destination.

Command:
traceroute 8.8.8.8

Practical verification:
Command executed successfully.


nslookup

Purpose:
Queries DNS information for a domain.

Command:
nslookup example.com

Practical verification:
DNS resolution verified successfully.


ifconfig

Purpose:
Displays network interface configuration.

Command:
ifconfig

Note:
ifconfig is a legacy utility. The modern alternative is ip.


4. NETWORKING IN CYBERSECURITY

Networking knowledge is essential for:

- Network reconnaissance
- Attack-surface identification
- Traffic analysis
- Service discovery
- Incident investigation
- Security troubleshooting


5. PRACTICAL EVIDENCE

The following screenshots document the commands executed on the Kali Linux workstation:

01-ip-addr.png
Command: ip addr

02-ping.png
Command: ping -c 4 127.0.0.1

03-ss.png
Command: ss -tuln

04-traceroute.png
Command: traceroute 8.8.8.8

05-nslookup.png
Command: nslookup example.com


STATUS

Completed

- Networking fundamentals documented
- Network commands practically verified
- Practical evidence captured
- Screenshots added to the repository
