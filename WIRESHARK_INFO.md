## Wireshark Overview

Wireshark is a powerful open-source network protocol analyzer used to capture, inspect, and analyze network traffic in real time. It enables network administrators, security analysts, and researchers to monitor communication between devices, troubleshoot network issues, and investigate security incidents.

---

## Wireshark Packet Panes

Wireshark organizes captured packets into three primary panes that assist in packet analysis.

| Pane | Description |
|--------|-------------|
| Packet List Pane | Displays a summary of all captured packets including source, destination, protocol, length, and packet information. |
| Packet Details Pane | Provides a hierarchical breakdown of the selected packet and its protocol layers. |
| Packet Bytes Pane | Displays the raw packet contents in hexadecimal and ASCII format. |

### Packet Pane Layout

```text
+-----------------------------------------------------------+
|                    Packet List Pane                       |
|-----------------------------------------------------------|
| No | Time | Source | Destination | Protocol | Info       |
+-----------------------------------------------------------+

+-----------------------------------------------------------+
|                  Packet Details Pane                      |
|-----------------------------------------------------------|
| Frame                                                    |
| Ethernet II                                              |
| Internet Protocol (IPv4)                                 |
| TCP / UDP / ICMP / DNS                                   |
+-----------------------------------------------------------+

+-----------------------------------------------------------+
|                   Packet Bytes Pane                       |
|-----------------------------------------------------------|
| Hexadecimal and ASCII Representation of Packet Data      |
+-----------------------------------------------------------+
```

### Purpose of Each Pane

#### Packet List Pane
- Displays all captured packets.
- Shows source and destination addresses.
- Displays protocol information.
- Helps identify suspicious or interesting traffic.

#### Packet Details Pane
- Shows protocol header information.
- Displays packet fields and values.
- Helps analyze network communication at different protocol layers.

#### Packet Bytes Pane
- Displays the raw packet data.
- Shows hexadecimal and ASCII representations.
- Useful for deep packet inspection.

---

## Wireshark Filtering Mechanisms

Wireshark provides two filtering mechanisms to help analysts focus on relevant traffic.

| Filter Type | Description |
|------------|-------------|
| Capture Filter | Filters packets before they are captured and saved. |
| Display Filter | Filters packets after capture without removing any captured data. |

---

### 1. Capture Filters

Capture filters are applied before packet collection begins. They reduce the amount of traffic captured and improve performance.

#### Common Capture Filters

| Filter | Explanation |
|----------|------------|
| `icmp` | Capture only ICMP traffic such as ping requests and replies. |
| `host 192.168.1.10` | Capture traffic to or from a specific host. |
| `port 80` | Capture HTTP traffic on port 80. |
| `port 53` | Capture DNS traffic. |
| `tcp` | Capture all TCP traffic. |
| `udp` | Capture all UDP traffic. |

#### Example

```text
icmp
```

Captures only ICMP packets.

#### Advantages

- Reduces storage usage.
- Improves capture performance.
- Captures only relevant traffic.

---

### 2. Display Filters

Display filters are applied after packets have been captured. They allow analysts to focus on specific traffic while preserving all captured packets.

#### Common Display Filters

| Filter | Explanation |
|----------|------------|
| `icmp` | Display ICMP packets only. |
| `arp` | Display ARP packets only. |
| `dns` | Display DNS packets only. |
| `http.request` | Display HTTP request packets. |
| `tcp.flags.syn == 1` | Display TCP SYN packets. |
| `ip.addr == 192.168.1.10` | Display packets involving a specific IP address. |
| `tcp.port == 80` | Display traffic using TCP port 80. |
| `udp.port == 53` | Display DNS traffic over UDP port 53. |

#### Example

```wireshark
tcp.flags.syn == 1
```

Displays packets containing the TCP SYN flag, commonly observed during TCP connection establishment and SYN scanning.

#### Advantages

- No captured packets are lost.
- Supports advanced filtering expressions.
- Makes packet analysis easier and more efficient.

---

## Packet Analysis Workflow

1. Select the network interface.
2. Configure a capture filter (optional).
3. Start packet capture.
4. Generate or monitor network traffic.
5. Stop the capture.
6. Apply display filters.
7. Analyze packets using the Packet Details Pane.
8. Inspect raw packet contents using the Packet Bytes Pane.
9. Document findings using screenshots, packet captures, and reports.
