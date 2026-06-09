# wireshark-network-analysis

Analyzing various network activities and security events using Wireshark within a Local Area Network (LAN).

## Overview

This project demonstrates network traffic analysis and security monitoring using Wireshark in a controlled Local Area Network (LAN) environment. The primary objective is to capture, inspect, and analyze network packets exchanged between systems to understand network behavior and identify indicators of suspicious activity.

Wireshark was installed on the analysis machine, which was connected to the same LAN as the target system. Traffic generated during various network security scenarios was captured and examined to study protocol behavior, packet structures, and potential security events.

---

## Network Topology

```text
+-----------------------+       LAN Network       +----------------+
| Attacker / Analyzer   | <---------------------> | Target System  |
| (Wireshark Installed) |                         |                |
+-----------------------+                         +----------------+
```

---

## Setup Description

- The **Attacker/Analyzer** machine is used to generate controlled network activity.
- **Wireshark** is installed on the same machine to capture and analyze network traffic.
- The **Target System** receives and responds to network requests.
- Both systems are connected to the same **LAN network** for packet capture and analysis.

---

## Project Objectives

- Capture and analyze network traffic using Wireshark.
- Understand TCP/IP communication and protocol behavior.
- Investigate common network security events.
- Apply packet filtering and protocol analysis techniques.
- Document findings using packet captures and screenshots.
- Develop practical network monitoring and troubleshooting skills.

---

## Tools Used

| Tool | Purpose |
|--------|---------|
| Wireshark | Packet capture and traffic analysis |
| Linux Environment | Network testing and analysis |
| Local Area Network (LAN) | Controlled communication environment |
| Git & GitHub | Version control, project documentation, and hosting |
| Network Utilities | Traffic generation and testing |

---

## Key Learning Outcomes

- Network packet inspection and analysis
- Protocol identification and troubleshooting
- TCP/IP communication understanding
- Packet filtering and traffic monitoring
- Security event investigation
- Hands-on experience with Wireshark

---

## Author

This project was developed as part of a practical network security and traffic analysis study using Wireshark in a controlled LAN environment.
