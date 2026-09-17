NETWORKING FUNDAMENTALS

Objective

Understand the networking concepts and commands commonly used in cybersecurity.


1. NETWORKING BASICS

IP Address

An IP address identifies a device/interface on an IP network.

IPv4 example:
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

The default gateway is the device used to reach networks outside the local network.


DNS

DNS translates domain names into IP addresses.

Example:
example.com → IP address


2. IMPORTANT NETWORKING PROTOCOLS

TCP

Connection-oriented transport protocol that provides reliable, ordered delivery.

UDP

Connectionless transport protocol with lower overhead and no guarantee of delivery.

HTTP

Application-layer protocol commonly used for web communication.

HTTPS

HTTP protected using TLS encryption.

DNS

Protocol used for domain-name resolution.

SSH

Protocol used for secure remote administration and command-line access.


3. COMMON NETWORKING COMMANDS

ip addr

Displays network interfaces and IP addresses.

Example:
ip addr


ping

Tests basic network connectivity.

Example:
ping -c 4 127.0.0.1


ss

Displays network sockets, connections, and listening ports.

Example:
ss -tuln


traceroute

Shows the network path between the local system and a destination.

Example:
traceroute 8.8.8.8


nslookup

Queries DNS information.

Example:
nslookup example.com


4. NETWORKING AND CYBERSECURITY

Networking knowledge is important for:

- Network reconnaissance
- Traffic analysis
- Identifying exposed services
- Understanding attack surfaces
- Investigating suspicious connections
- Troubleshooting security incidents


5. PRACTICAL VERIFICATION

The networking commands will be verified on the Kali Linux workstation.

Practical verification will cover:

- Network interfaces and IP addresses
- Local connectivity
- Listening network sockets
- Network path discovery
- DNS resolution


STATUS

Documentation prepared.

Practical verification completed:

- ip addr — verified network interfaces and IP addresses
- ping -c 4 127.0.0.1 — verified network connectivity
- ss -tuln — verified TCP/UDP listening sockets
- traceroute 8.8.8.8 — verified network path
- nslookup example.com — verified DNS resolution

Five practical verification screenshots are included in the screenshots directory.
