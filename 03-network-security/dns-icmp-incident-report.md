# DNS and ICMP Traffic Analysis – Cybersecurity Incident Report

## Incident Summary

Customers reported that they were unable to access the website **www.yummyrecipesforme.com** and received the error message **"destination port unreachable."**

After reproducing the issue, network traffic was analyzed using the tcpdump network protocol analyzer.

The captured traffic showed that the browser attempted to send DNS queries using the **UDP protocol** to port **53**, which is the standard port used for DNS services.

Instead of receiving a DNS response, the system received **ICMP error messages** stating:

udp port 53 unreachable

This indicates that the DNS server could not deliver the UDP packet to port 53 because no service was listening on that port.

---

## Protocols Identified

The following network protocols were observed in the tcpdump log:

**UDP (User Datagram Protocol)**  
Used to send DNS queries from the client to the DNS server.

**DNS (Domain Name System)**  
Used to translate the domain name **www.yummyrecipesforme.com** into an IP address.

**ICMP (Internet Control Message Protocol)**  
Used by the DNS server to return error messages indicating that the requested UDP port was unreachable.

---

## Log Analysis

The log shows repeated attempts to send UDP packets from the client IP address **192.51.100.15** to the DNS server **203.0.113.2**.

Each attempt resulted in an ICMP error response stating that **UDP port 53 was unreachable**.

Because DNS requests could not be processed, the browser was unable to resolve the domain name to an IP address. As a result, the website could not be accessed.

---

## Suspected Root Cause

The most likely cause of the incident is that the **DNS service on the DNS server was unavailable** or **UDP port 53 was blocked or misconfigured**.

Possible causes include:

- DNS service stopped or crashed
- Firewall blocking DNS traffic
- Misconfigured DNS server
- Network service failure on port 53

---

## Recommended Next Steps

To resolve the issue, the following troubleshooting steps should be performed:

- Verify that the DNS server is running
- Confirm the DNS service is listening on UDP port 53
- Review firewall rules to ensure DNS traffic is allowed
- Restart DNS services if necessary
- Perform additional DNS resolution tests

Once DNS functionality is restored, users should be able to access the website normally.
