# SYN Flood Attack Analysis – Cybersecurity Incident Report

## Incident Summary

An automated monitoring alert indicated that the company web server was experiencing connectivity issues. Employees attempting to access the travel agency’s website received a **connection timeout error message**.

Upon investigation, network traffic was analyzed using a packet sniffer. The captured packets showed a large number of **TCP SYN requests** originating from an unfamiliar IP address.

This abnormal traffic pattern indicated that the web server was under a **TCP SYN Flood attack**, a type of **Denial-of-Service (DoS) attack**.

---

## Description of the Attack

A SYN flood attack occurs when a malicious actor sends a high volume of TCP SYN packets to a server but does not complete the TCP three-way handshake.

Normally, a TCP connection follows this process:

1. Client sends **SYN**
2. Server replies **SYN-ACK**
3. Client sends **ACK**

During a SYN flood attack, the attacker sends many SYN packets but never sends the final ACK response. This leaves many half-open connections on the server.

As these incomplete connections accumulate, the server’s connection queue becomes full and it can no longer respond to legitimate users.

---

## Impact on Network Performance

The attack overwhelmed the web server with excessive SYN requests. Because the server attempted to respond to each request, it quickly consumed available system resources.

This caused legitimate users to experience **connection timeouts**, preventing employees and customers from accessing the website.

The disruption affected business operations because employees rely on the website to search for travel deals and assist customers with booking vacations.

---

## Response Actions Taken

To restore normal operations, the following actions were taken:

- The web server was temporarily taken offline to recover.
- The firewall was configured to block the IP address sending the malicious SYN traffic.

However, this solution is temporary because attackers can spoof IP addresses and continue the attack.

---

## Recommended Mitigation Strategies

To prevent future SYN flood attacks, the organization should consider implementing the following security measures:

- Enable **SYN cookies** on the server
- Configure **rate limiting** for incoming connections
- Deploy **intrusion detection or intrusion prevention systems (IDS/IPS)**
- Implement **Web Application Firewall (WAF) protections**
- Utilize **DDoS mitigation services**

These measures would help protect the server from being overwhelmed by malicious connection attempts.
