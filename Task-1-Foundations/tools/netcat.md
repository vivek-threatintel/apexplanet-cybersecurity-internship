# Netcat

> Command-line networking utility used for TCP/UDP connection testing, network debugging, and simple client/server communication.

---

## Objective

Understand the basic use of Netcat for network connectivity testing and client/server communication in an authorized cybersecurity lab.

---

## 1. What is Netcat?

Netcat (`nc`) is a command-line networking utility that can establish TCP or UDP connections between systems.

It can be used for:

- TCP connection testing
- UDP connection testing
- Port connectivity testing
- Network debugging
- Simple client/server communication

---

## 2. Basic Client/Server Workflow

### Listener

Start a TCP listener:

    nc -lvnp 4444

### Client

Connect to the listener:

    nc 127.0.0.1 4444

Data entered on one side can then be transmitted to the other side.

---

## 3. Practical Lab

The Netcat exercise was performed locally on the Kali Linux workstation.

Listener:

    nc -lvnp 4444

Client:

    nc 127.0.0.1 4444

A test message was sent through the established TCP connection.

---

## 4. Practical Verification

The listener was started on TCP port `4444`.

The client connected to:

    127.0.0.1:4444

The following test message was transmitted:

    Netcat connectivity test

Successful transmission verified basic TCP client/server communication.

---

## 5. Practical Evidence

Screenshot:

    screenshots/16-Netcat-connectivity.png

The screenshot provides evidence of the successful Netcat client/server connection and message exchange.

---

## Security Relevance

Netcat is useful for:

- Network connectivity testing
- Port troubleshooting
- Service debugging
- TCP/UDP communication testing
- Security lab exercises

Netcat can also be used in security testing, so it should only be used against systems and networks where testing is authorized.

---

## Verification Status

| Area | Status |
|---|---|
| Netcat availability | Completed |
| TCP listener | Completed |
| TCP client connection | Completed |
| Data transmission | Completed |
| Practical evidence | Completed |

---

## Conclusion

Netcat was used to establish a local TCP client/server connection and verify basic network communication on the Kali Linux workstation.
