````markdown
# Networking Fundamentals

> Practical networking fundamentals and command-line verification for cybersecurity labs.

---

## 🎯 Objective

Understand the networking concepts, protocols, and command-line utilities commonly used in cybersecurity.

---

## 1. Core Networking Concepts

### IP Address

An **IP address** identifies a network interface on an IP network.

**Example:**

```text
192.168.1.10
````

### MAC Address

A **MAC address** identifies a network interface at the Data Link layer.

**Example:**

```text
00:11:22:33:44:55
```

### Subnet

A **subnet** divides an IP network into smaller logical networks.

**Example:**

```text
192.168.1.0/24
```

### Default Gateway

The **default gateway** is the device used to forward traffic from the local network to other networks.

### DNS

**DNS (Domain Name System)** translates domain names into IP addresses.

**Example:**

```text
example.com → IP address
```

---

## 2. Common Network Protocols

| Protocol  | Purpose                                    |
| --------- | ------------------------------------------ |
| **TCP**   | Reliable, connection-oriented transport    |
| **UDP**   | Connectionless transport with low overhead |
| **HTTP**  | Web communication                          |
| **HTTPS** | HTTP secured using TLS                     |
| **DNS**   | Domain-name resolution                     |
| **SSH**   | Secure remote administration               |

---

## 3. Network Commands

### `ip addr`

Displays network interfaces and assigned IP addresses.

```bash
ip addr
```

**Practical verification:** Verified on the Kali Linux workstation.

---

### `ping`

Tests basic network connectivity.

```bash
ping -c 4 127.0.0.1
```

**Result:** 4 packets transmitted, 4 received, 0% packet loss.

---

### `ss`

Displays network sockets and listening ports.

```bash
ss -tuln
```

**Practical verification:** Command executed successfully on Kali Linux.

---

### `traceroute`

Displays the network path to a destination.

```bash
traceroute 8.8.8.8
```

**Practical verification:** Command executed successfully.

---

### `nslookup`

Queries DNS information for a domain.

```bash
nslookup example.com
```

**Practical verification:** DNS resolution verified successfully.

---

### `ifconfig`

Displays network interface configuration.

```bash
ifconfig
```

> **Note:** `ifconfig` is a legacy utility. The modern alternative is `ip`.

---

## 4. Networking in Cybersecurity

Networking knowledge is essential for:

* Network reconnaissance
* Attack-surface identification
* Traffic analysis
* Service discovery
* Incident investigation
* Security troubleshooting

---

## 5. Practical Evidence

The following screenshots document the commands executed on the **Kali Linux workstation**.

| Evidence            | Command                |
| ------------------- | ---------------------- |
| `01-ip-addr.png`    | `ip addr`              |
| `02-ping.png`       | `ping -c 4 127.0.0.1`  |
| `03-ss.png`         | `ss -tuln`             |
| `04-traceroute.png` | `traceroute 8.8.8.8`   |
| `05-nslookup.png`   | `nslookup example.com` |

---

## 6. Verification Status

| Area                 | Status       |
| -------------------- | ------------ |
| Networking concepts  | ✅ Completed  |
| Network protocols    | ✅ Documented |
| Network commands     | ✅ Verified   |
| Practical testing    | ✅ Completed  |
| Evidence screenshots | ✅ Captured   |
| Documentation        | ✅ Completed  |

---

## Conclusion

The fundamental networking concepts and commonly used network utilities were documented and practically verified in the Kali Linux environment.

````

**Important:** Isko paste karne ke baad save/exit karo. Phir:

```bash
git diff -- Task-1-Foundations/notes/networking.md
````
