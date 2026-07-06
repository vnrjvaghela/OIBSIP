# Basic Network Scanning with Nmap
**Author:** Vanraj Vaghela
**Track:** Cyber Security
**Task:** 1 - Basic Network Scanning with Nmap

## What is Nmap?
Nmap (Network Mapper) is a powerful, open-source diagnostic tool used for network discovery and security auditing. It operates by sending specifically crafted packets to target hosts and analyzing the responses. This allows security professionals to determine what devices are active on a network, what services (application name and version) those devices are running, and what operating systems are in use.

## Why Network Scanning Matters
Network scanning is the foundational step in understanding and securing any IT infrastructure. By mapping the network and identifying open ports and active services, administrators can:
* **Visualize the Attack Surface:** See exactly what a potential attacker would see from the outside.
* **Identify Vulnerabilities:** Discover outdated software versions or unnecessary services that could be exploited.
* **Verify Security Controls:** Ensure that firewalls and access controls are actively blocking traffic they are configured to drop.

## Ethical Use Guidelines
The capabilities of Nmap make it a dual-use tool; it is essential for defensive security but is also the primary reconnaissance tool used by malicious actors. Therefore, ethical scanning requires strict adherence to the following rules:
1.  **Explicit Authorization:** Never scan a network, machine, or IP address without explicit, written permission from the owner. 
2.  **No Production Disruption:** Aggressive scans can inadvertently crash fragile services or legacy devices. Scans should be tuned to avoid disrupting business operations.
3.  **Local Testing:** For the purpose of this task and general learning, Nmap must only be run against a locally owned Virtual Machine (VM) or a purposely built private lab environment where the user has full administrative control.