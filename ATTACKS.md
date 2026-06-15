## 1. ICMP Host Discovery

### Objective

An ICMP (Internet Control Message Protocol) host discovery, often called a ping sweep, is a network reconnaissance technique used to identify active IP addresses. It systematically sends ICMP Echo Request packets to a range of IP addresses and waits for Echo Reply responses to confirm that hosts are live and reachable.

### Attack Tool

**Nmap**

### Command Used

```bash id="tt1g0v"
sudo nmap -sn -PE 192.168.29.0/24
```

### Command Explanation

| Option           | Description                                                                     |
| ---------------- | --------------------------------------------------------------------------------|
| `sudo`            | Runs Nmap with administrative privileges, allowing it to send raw ICMP packets.|
| `-sn`             | Performs host discovery only (Ping Scan); skips port scanning.                 |
| `-PE`             | Uses ICMP Echo Requests (Ping) to discover active hosts.                       |
| `192.168.29.0/24` | Network range being scanned.                                                   |

### Working  
  
1. Nmap sends an ICMP Echo Request (Type 8) to each target IP.  
2. Active hosts respond with an ICMP Echo Reply (Type 0).  
3. Nmap marks responding hosts as Up.  
4. Hosts that do not respond may be offline or filtering ICMP traffic.

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

## 2. ARP Host Discovery

### Objective

ARP (Address Resolution Protocol) host discovery is the process of locating active devices on a local network (subnet) by sending Address Resolution Protocol (ARP) requests to IP addresses. It is the most reliable and fastest method for local host discovery, as ARP packets operate at Layer 2 (Data Link layer) and cannot be blocked by standard host firewalls.

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

