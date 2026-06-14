## 1. ICMP Ping Scan (Host Discovery)

### Objective

Identify active hosts on the network by sending ICMP Echo Requests and analyzing the corresponding responses.

### Attack Tool

**fping**

### Command Used

```bash id="tt1g0v"
fping -aqg 192.168.1.0/24
```

### Command Explanation

| Option           | Description                                           |
| ---------------- | ----------------------------------------------------- |
| `-a`             | Show only alive hosts.                                |
| `-q`             | Run in quiet mode.                                    |
| `-g`             | Generate target IPs from the specified network range. |
| `192.168.1.0/24` | Network range being scanned.                          |

### Attack Execution Screenshot

[Attacker Screenshot](screenshots/attacker/icmp_ping_scan_attack.png)


### Wireshark Display Filter

```wireshark id="epx1h5"
icmp
```

### Filter Explanation

Displays only ICMP packets, including:

* Echo Request
* Echo Reply

### Wireshark Analysis Screenshot

[Analyzer Screenshot](screenshots/wireshark/icmp_ping_scan_capture.png)

### Packet Capture

[Wireshark Pcap file](pcaps/icmp_ping_scan.pcap)

### Observations

* ICMP Echo Requests were sent from the Kali Linux attacker.
* Active hosts responded with ICMP Echo Replies.
* Source and destination IP addresses were successfully identified.
* Round-trip communication was observed.

### Security Significance

ICMP ping scanning is commonly used during the reconnaissance phase to discover live hosts before further enumeration.

### Findings

The scan successfully identified active hosts on the WLAN network and demonstrated how ICMP traffic appears in Wireshark.

---

## 2. ARP Scan (Local Network Host Discovery)

### Objective

Identify active devices on the local network using ARP requests and responses.

### Attack Tool

**Nmap**

### Command Used

```bash id="p6z1pr"
nmap -sn 192.168.1.0/24
```

### Command Explanation

| Option           | Description                                        |
| ---------------- | -------------------------------------------------- |
| `-sn`            | Ping Scan (Host Discovery only, no port scanning). |
| `192.168.1.0/24` | Target network range.                              |

### Attack Execution Screenshot

[Attacker Screenshot](screenshots/attacker/arp_scan_attack.png)

### Wireshark Display Filter

```wireshark id="84mngz"
arp
```

### Filter Explanation

Displays only ARP packets, including:

* ARP Requests
* ARP Replies

### Wireshark Analysis Screenshot

[Analyzer screenshot](screenshots/wireshark/arp_scan_capture.png)

### Packet Capture

[Wireshark Pcap file](pcaps/arp_scan.pcap)

### Observations

* ARP Requests were broadcast to discover devices on the local network.
* Active devices responded with ARP Replies.
* MAC addresses associated with IP addresses were identified.
* Layer 2 communication behavior was successfully analyzed.

### Security Significance

ARP scanning is commonly used during network reconnaissance to enumerate hosts and map IP-to-MAC address relationships within a local network.

### Findings

The scan successfully identified active devices on the network and demonstrated how ARP traffic can be analyzed using Wireshark to understand local network communications.
