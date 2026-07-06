# Vulnerability Scanning with Nikto
**Author:** Vanraj Vaghela
**Track:** Cyber Security
**Task:** 7 - Vulnerability Scanning with Nikto

## What is Nikto?
Nikto is an open-source web server scanner that performs comprehensive tests against web servers for multiple items, including thousands of potentially dangerous files, outdated server versions, and server configuration issues.

## Nikto's Limitations: A "Noisy" Scanner
Nikto is widely known as a highly "noisy" scanner. This means it makes no attempt to be stealthy; it aggressively sends thousands of rapid requests to the target web server. 
* **The Implication:** In a real-world production environment, an Intrusion Detection System (IDS) or Web Application Firewall (WAF) will immediately detect, flag, and block a Nikto scan. It is not designed for covert reconnaissance, but rather for authorized, internal security auditing.

## Nikto vs. Nmap
While both are essential security tools, they operate at different layers:
* **Nmap (Network Mapper):** Operates primarily at the network layer. It maps out the entire network infrastructure, identifying active hosts, open ports, and the overarching services running on them.
* **Nikto:** Operates entirely at the application layer. It focuses specifically on interrogating web servers (usually ports 80/8080 and 443) to find web-specific misconfigurations and vulnerabilities.