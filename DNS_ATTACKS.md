# DNS Tunneling

## Overview

DNS tunneling is a cyberattack technique that routes non-DNS protocol traffic (such as HTTP, SSH, or malware commands) through the Domain Name System (DNS). Because network firewalls must leave DNS traffic open over UDP Port 53 to allow normal web browsing, attackers abuse this trusted protocol to create a covert communication channel that bypasses standard security defenses.

---

## How DNS Tunneling Works (dnscat2)

DNS tunneling works by abusing the DNS protocol to transfer data instead of just resolving domain names.  

The attack exploits the standard hierarchical nature of the internet's phonebook to relay hidden information back and forth.  

1. Infrastructure Setup: The attacker registers a seemingly benign domain (e.g., badsite.com) and configures a server they control to act as the authoritative nameserver for that specific domain.
2. Infection & Encoding: A device inside the target network is compromised with malware. When the malware wants to send data out, it breaks the information into small pieces, encodes it (often using Base64), and appends it as a subdomain string to a DNS query (e.g., ://badsite.com).
3. The Relay Process: The compromised machine sends the request to the organization's local internal DNS resolver. The local resolver, unable to resolve the unknown subdomain, forwards the request through the global DNS chain until it lands on the attacker's authoritative nameserver.
4. Execution: The attacker’s server extracts the subdomain string, decodes the data, and processes the secret message. If the attacker wants to send a command back, they embed the response inside standard DNS resource records (like TXT, A, or CNAME fields), which flow cleanly back to the victim's machine.

### Working Flow

```text id="dnsflow"
Attacker (Kali - Server)
        ^
        | DNS Responses (Commands / Output)
        |
Target (Parrot - Client)
        |
        | DNS Queries (Encoded Data)
        v
Attacker (Kali - Server)
```

Step-by-Step Process:  

1. A dnscat2 server is started on the attacker machine (Kali Linux).
2. The victim machine (Parrot OS) runs the dnscat2 client.
3. The client connects to the attacker using DNS requests on port 53.
4. Commands are encoded into DNS queries.
5. The attacker sends commands through the dnscat2 console.
6. The victim executes the commands locally.
7. Output is sent back inside DNS responses.
8. Continuous DNS traffic maintains a hidden remote shell.

