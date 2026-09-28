## Firewall Basics

### Objective

The objective was to create a basic iptables firewall rule and verify that a specific TCP port could be blocked from the Kali testing machine.

### Firewall Rule

The following rule was configured on the Metasploitable 2 system:

```
sudo iptables -A INPUT -p tcp --dport 80 -j DROP
````

This rule drops incoming TCP traffic destined for port 80.

### Rule Verification

The configured rule was verified using:

```
sudo iptables -L -n -v
```

The output showed:

```
0     0 DROP    tcp  --  *  *  0.0.0.0/0  0.0.0.0/0
         tcp dpt:80
```

### Connectivity Test

The firewall rule was tested from Kali Linux using:

```
sudo nmap -p 80 192.168.100.20
```

The result showed:

```
80/tcp filtered http
```

This confirmed that TCP port 80 was being filtered by the firewall rule.

## Evidence

```
Task-2-Network-Security/screenshots/29-iptables-rules.png
Task-2-Network-Security/screenshots/30-firewalls-block-test.png
```

### Screenshot 29

Metasploitable 2 showing the iptables DROP rule for TCP port 80.

### Screenshot 30

Kali Nmap scan showing port 80 as `filtered` after the firewall rule was applied.

## Conclusion

The firewall exercise successfully demonstrated how an iptables rule can be used to block incoming traffic to a specific TCP port and how the effect can be verified remotely using Nmap.

````
