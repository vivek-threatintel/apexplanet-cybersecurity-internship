# Tool Familiarization

> Introduction to common cybersecurity tools used for network analysis, reconnaissance, web application testing, and network debugging.

---

## Objective

Understand the basic purpose and usage of common cybersecurity tools used in security testing and network analysis.

The tools covered are:

- Wireshark
- Nmap
- Burp Suite
- Netcat

---

## 1. Wireshark

Wireshark is a network protocol analyzer used to capture and inspect network traffic.

### Common Uses

- Packet capture
- Protocol analysis
- Network troubleshooting
- Traffic investigation
- Security monitoring

### Basic Workflow

1. Select a network interface.
2. Start packet capture.
3. Generate network traffic.
4. Stop the capture.
5. Analyze the captured packets.

### Practical Verification

Wireshark will be used to capture network traffic on the Kali Linux workstation.

---

## 2. Nmap

Nmap is a network discovery and security auditing tool.

### Common Uses

- Host discovery
- Port scanning
- Service enumeration
- Service version detection
- Operating system detection

### Basic Command

    nmap <target>

### Version Detection

    nmap -sV <target>

### Practical Verification

Nmap will be used against an authorized local or lab target.

---

## 3. Burp Suite

Burp Suite is a web application security testing platform that acts as an intercepting proxy.

### Common Uses

- Intercepting HTTP/HTTPS requests
- Inspecting web traffic
- Modifying requests
- Testing web application behavior
- Repeater-based request testing

### Basic Workflow

1. Start Burp Suite.
2. Configure the browser proxy.
3. Browse an authorized web application.
4. Intercept the request.
5. Inspect or modify the request.

### Practical Verification

Burp Suite will be used with an authorized local or lab web application.

---

## 4. Netcat

Netcat is a command-line networking utility used for network connections and debugging.

### Common Uses

- TCP/UDP connection testing
- Port connectivity testing
- Network debugging
- Simple client/server communication

### Basic Examples

Listener:

    nc -lvnp 4444

Client:

    nc 127.0.0.1 4444

### Practical Verification

Netcat will be used for local client/server communication on the Kali Linux workstation.

---

## 5. Security Relevance

These tools support different areas of cybersecurity work:

| Tool | Primary Use |
|---|---|
| Wireshark | Traffic Analysis |
| Nmap | Network Discovery and Enumeration |
| Burp Suite | Web Application Testing |
| Netcat | Network Debugging |

---

## Verification Status

| Tool | Documentation | Practical Verification |
|---|---|---|
| Wireshark | Completed | Completed |
| Nmap | Completed | Completed |
| Burp Suite | Completed | Completed |
| Netcat | Completed | Completed |

---

## Practical Evidence

The following practical exercises were completed on the Kali Linux cybersecurity lab environment:

- Nmap version and network/service scanning
- Wireshark ICMP packet capture and analysis
- Burp Suite HTTP request interception
- Netcat local TCP client/server communication

Screenshots are stored in the `screenshots/` directory.

---

## Conclusion

Wireshark, Nmap, Burp Suite, and Netcat are commonly used cybersecurity tools with different purposes across network analysis, reconnaissance, web application testing, and network debugging.
