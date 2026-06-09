# wireshark-network-analysis

Analyzing various network activities and security events using Wireshark within a Wireless Local Area Network (WLAN).

## Overview

This project demonstrates network traffic analysis and security monitoring using Wireshark in a controlled Wireless Local Area Network (WLAN) environment. The primary objective is to capture, inspect, and analyze network packets exchanged between systems to understand network behavior and identify indicators of suspicious activity.

A Kali Linux system was used to generate controlled network activity and security testing scenarios, while a Parrot OS system with Wireshark installed was used to capture and analyze the resulting network traffic. Both virtual machines were configured using a Bridged Network Adapter, enabling them to obtain IP addresses from the same network and communicate as if they were separate physical devices on the local network. This setup allowed realistic packet capture and protocol analysis during various network security experiments.  

This project utilizes Wireshark for network traffic capture and analysis. To better understand the Wireshark interface, packet analysis process, packet panes, and filtering mechanisms used throughout this project, refer to the detailed documentation is found in [WIRESHARK_INFO.md](WIRESHARK_INFO.md).

---    

## Network Topology

```text
+-------------------+       WLAN(Wi-Fi)       +---------------------+
|    Kali Linux     | <---------------------> |     Parrot OS       |
|     Attacker      |                         |(Wireshark Installed)|
+-------------------+                         +---------------------+
          |                                            |
          +-----------Bridged Network Adapter----------+
```

---

## Setup Description

- The Kali Linux machine acts as the attacker system and is used to generate controlled network activity and security testing scenarios.
- The Parrot OS machine hosts Wireshark and serves as the target and analysis system.
- Both virtual machines are configured with a Bridged Network Adapter.
- The bridged configuration allows each machine to appear as an independent host on the local network.
- Both systems receive network connectivity through the same WLAN and can communicate directly with one another.
- Network packets exchanged between the Kali Linux attacker and the Parrot OS target are captured and analyzed using Wireshark.
- Packet captures are examined to study protocol behavior, communication patterns, and indicators of suspicious activity.
---

## Environment Configuration

| Component | Configuration |
|------------|--------------|
| Host Machine Network | WLAN (Wi-Fi) |
| Virtualization Platform | VirtualBox / VMware |
| Network Mode | Bridged Adapter |
| Attacker Machine | Kali Linux |
| Target Machine | Parrot OS |
| Packet Analysis Tool | Wireshark |
| Communication Type | WLAN through Bridged Networking |
| Traffic Generation | Performed from Kali Linux |
| Traffic Analysis | Performed on Parrot OS using Wireshark |
| IP Assignment | Obtained from the same network via Bridged Adapter |

---
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
| Kali Linux | Attack simulation and traffic generation |
| Parrot OS | Target system and analysis platform |
| VirtualBox / VMware | Virtual machine management |
| Wireless Local Area Network (WLAN/Wi-Fi) | Wireless communication environment |
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

## Attack Documentation

Detailed attack scenarios, Wireshark analysis, filters, screenshots, and observations can be found in [ATTACKS.md](ATTACKS.md).

## Author

This project was developed as part of a practical network security and traffic analysis study using Wireshark in a controlled WLAN environment.  

Vamshi Krishna GK  
Cybersecurity Enthusiast
