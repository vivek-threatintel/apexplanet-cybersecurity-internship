# Wireshark Packet Analysis Report

## Objective

The objective of this exercise was to capture and analyze network traffic between the Kali Linux testing workstation and the intentionally vulnerable Metasploitable 2 virtual machine within the authorized `cyberlab` lab environment.

Wireshark was used to inspect ICMP, TCP, and HTTP traffic generated during controlled network activity.

---

## Lab Environment

| Parameter | Value |
|---|---|
| Scanner / Analyzer | Kali Linux |
| Kali IP | `192.168.100.10` |
| Target | Metasploitable 2 |
| Target IP | `192.168.100.20` |
| Network | `cyberlab` |
| Capture Interface | `eth1` |
| Tool | Wireshark |
| Environment | Private isolated lab |

---

## 1. ICMP Packet Analysis

ICMP traffic was generated using:

```
ping -c 4 192.168.100.20
````

The resulting packets were inspected in Wireshark using the display filter:

```
icmp
```

The capture shows ICMP request and response traffic between the Kali Linux workstation and the Metasploitable 2 target.

### Observed Traffic

The communication consisted of:

* ICMP Echo Requests sent from Kali to the target.
* ICMP Echo Replies returned by the target.
* Source and destination IP addresses identifying both systems.
* ICMP packet information visible in the packet details.

This confirms successful network-layer communication between the two lab systems.

### Evidence

```
Task-2-Network-Security/screenshots/23-icmp-wireshark.png
```

---

## 2. TCP Packet Analysis

TCP traffic was generated against the target using:

```
nc -vz 192.168.100.20 22
```

The captured traffic was inspected using the Wireshark filter:

```
tcp
```

### Observed Traffic

The capture provides visibility into TCP communication between the Kali workstation and the target.

Relevant TCP information includes:

* Source and destination IP addresses.
* Source and destination ports.
* TCP flags.
* TCP connection activity.
* Packet sequence information.

The traffic demonstrates how TCP packets can be inspected to understand connection establishment and communication between hosts.

### Evidence

```
Task-2-Network-Security/screenshots/24-tcp-wireshark.png
```

---

## 3. HTTP Packet Analysis

HTTP traffic was generated using:

```
curl http://192.168.100.20
```

The captured traffic was filtered using:

```
http
```

### Observed Traffic

The HTTP capture provides visibility into application-layer web traffic between Kali and the Apache web service running on Metasploitable 2.

The packet analysis allows inspection of:

* HTTP request traffic.
* HTTP response traffic.
* Source and destination addresses.
* TCP ports associated with HTTP communication.
* HTTP protocol information exposed within the captured traffic.

Because HTTP is unencrypted, application-layer information can be visible directly in packet captures.

### Evidence

```
Task-2-Network-Security/screenshots/25-http-wireshark.png
```

---

## 4. Wireshark Filters Used

The following display filters were used during packet analysis:

### ICMP

```
icmp
```

Used to isolate ICMP Echo Request and Echo Reply traffic.

### TCP

```
tcp
```

Used to inspect TCP packets and connection activity.

### HTTP

```
http
```

Used to isolate HTTP application-layer traffic.

---

## 5. Security Observations

### Network Visibility

Packet capture provides visibility into communications between systems at different protocol layers.

The captured traffic demonstrated:

* Network-layer ICMP communication.
* Transport-layer TCP communication.
* Application-layer HTTP communication.

### Unencrypted HTTP

HTTP traffic is transmitted without transport-layer encryption. Consequently, information contained within HTTP communication may be observable to an authorized packet observer with access to the traffic path.

In production environments, sensitive web communications should generally use HTTPS/TLS.

### Protocol-Level Analysis

Wireshark allows individual packet fields to be examined, including:

* Source and destination addresses
* Ports
* Protocols
* TCP flags
* Packet lengths
* Application-layer protocol information

This makes packet analysis useful for troubleshooting, network monitoring, incident investigation, and security analysis.

---

## 6. Evidence

The following screenshots were collected during the packet-analysis exercise:

```
Task-2-Network-Security/screenshots/23-icmp-wireshark.png
Task-2-Network-Security/screenshots/24-tcp-wireshark.png
Task-2-Network-Security/screenshots/25-http-wireshark.png
```

### Screenshot 23

ICMP packet capture showing communication between Kali and Metasploitable 2.

### Screenshot 24

TCP packet capture generated during TCP connectivity testing.

### Screenshot 25

HTTP packet capture generated while accessing the target's Apache web service.

---

## 7. Conclusion

The Wireshark exercise successfully demonstrated packet-level analysis of ICMP, TCP, and HTTP traffic within the isolated `cyberlab` environment.

The captures provided visibility into network communication at multiple protocol layers and demonstrated how Wireshark can be used to inspect packet headers, connection information, and application-layer traffic.
