# Wireshark

> Network protocol analyzer used to capture, inspect, and analyze network traffic.

---

## Objective

Understand the basic use of Wireshark for packet capture and network traffic analysis in an authorized cybersecurity lab.

---

## 1. What is Wireshark?

Wireshark is a network protocol analyzer that captures network packets and allows their contents and protocol information to be inspected.

It can be used for:

- Packet capture
- Protocol analysis
- Network troubleshooting
- Traffic investigation
- Security monitoring

---

## 2. Basic Workflow

A basic Wireshark workflow is:

1. Select a network interface.
2. Start packet capture.
3. Generate network traffic.
4. Stop the capture.
5. Apply a display filter.
6. Analyze the captured packets.

---

## 3. Practical Lab

The Wireshark exercise was performed on the Kali Linux workstation using the isolated cybersecurity lab network.

Traffic was generated between Kali Linux and the authorized Metasploitable 2 target.

Target:

    192.168.100.20

The ICMP protocol was used to generate and inspect network traffic.

---

## 4. Practical Verification

Traffic was generated using:

    ping -c 4 192.168.100.20

The Wireshark display filter used for analysis was:

    icmp

The capture was used to observe ICMP echo request and echo reply packets.

---

## 5. Practical Evidence

Screenshot:

    screenshots/14-wireshark-icmp.png

The screenshot provides evidence of ICMP traffic captured and inspected using Wireshark.

---

## Security Relevance

Wireshark is useful for:

- Network traffic analysis
- Protocol identification
- Troubleshooting connectivity
- Investigating suspicious traffic
- Incident analysis
- Security monitoring

---

## Verification Status

| Area | Status |
|---|---|
| Interface selection | Completed |
| Packet capture | Completed |
| ICMP traffic generation | Completed |
| ICMP filtering | Completed |
| Packet inspection | Completed |
| Practical evidence | Completed |

---

## Conclusion

Wireshark was used to capture and inspect ICMP traffic generated between the Kali Linux workstation and the authorized Metasploitable 2 lab target.
