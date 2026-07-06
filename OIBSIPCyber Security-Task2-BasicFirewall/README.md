# Basic Firewall Configuration with UFW
**Author:** Vanraj Vaghela
**Track:** Cyber Security
**Task:** 2 - Basic Firewall Configuration with UFW

## What is a Firewall?
[cite_start]A firewall is a fundamental network security system that monitors and controls incoming and outgoing network traffic based on predetermined security rules[cite: 172]. It acts as a protective barrier between a trusted internal network and untrusted external networks (such as the internet), effectively mitigating unauthorized access while permitting legitimate communications.

## Configuration Scripts
[cite_start]This repository contains `ufw_configuration.sh`[cite: 183], an automated bash script designed to reset, apply, and enable specific network traffic rules using the Uncomplicated Firewall (UFW) utility on a Linux system.

## Rule Rationale & Objectives
The following rules were implemented to establish a secure baseline for the server:

1. **`sudo ufw allow ssh` (Port 22)**
   * **What it achieves:** Permits incoming Secure Shell connections.
   * **Why it was chosen:** Essential for maintaining secure, encrypted remote administration access to the server. Without this rule, enabling the firewall would lock administrators out of the system.

2. **`sudo ufw deny http` (Port 80)**
   * **What it achieves:** Explicitly blocks incoming HTTP traffic.
   * **Why it was chosen:** HTTP transmits data in plain text. Blocking it forces all web communication to use encrypted channels (HTTPS), preventing Man-in-the-Middle (MITM) attacks and packet sniffing.

3. **`sudo ufw allow https` (Port 443)** *(Custom Rule 1)*
   * **What it achieves:** Permits incoming encrypted web traffic.
   * **Why it was chosen:** Allows secure web services to operate correctly while maintaining data confidentiality and integrity during transit.

4. **`sudo ufw deny from 192.168.1.100`** *(Custom Rule 2)*
   * **What it achieves:** Drops all traffic originating from this specific IP address.
   * **Why it was chosen:** Demonstrates how to block a known malicious, abusive, or unauthorized host from interacting with the server in any capacity.

## Testing and Verification
[cite_start]After executing the configuration script, the rules were verified using `sudo ufw status verbose`[cite: 181]. [cite_start]To test the `deny http` rule, a local connection request (`curl -I http://localhost`) was executed, which resulted in a connection timeout/refusal[cite: 182], confirming that unencrypted web traffic is successfully blocked by the firewall.