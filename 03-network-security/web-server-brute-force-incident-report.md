# Web Server Compromise – Brute Force Attack Incident Report

## Network Protocols Identified

During the investigation, the following network protocols were observed in the packet capture:

- DNS (Domain Name System)
- HTTP (Hypertext Transfer Protocol)

The browser first initiated a DNS request to obtain the IP address of the domain yummyrecipesforme.com. After receiving the correct IP address from the DNS server, the browser initiated an HTTP request to load the webpage.

After the webpage loaded, malicious JavaScript embedded in the source code prompted the user to download an executable file. When the file was executed, the browser initiated another DNS request for greatrecipesforme.com and then sent an HTTP request to the new website hosting malware.

---

## Incident Summary

Multiple customers reported that the website prompted them to download a file in order to access free recipes. After downloading and running the file, customers reported that their browser redirected them to a different website and their computers began performing slowly.

A sandbox environment was created to safely analyze the website behavior. A network protocol analyzer (tcpdump) was used to monitor network traffic during testing.

During the investigation, it was discovered that a former employee conducted a brute force attack against the administrative account of the web host. The attacker repeatedly attempted known default passwords until successfully guessing the correct password.

Once access to the admin panel was obtained, the attacker modified the website’s source code and inserted malicious JavaScript that prompted visitors to download malware. The attacker then changed the administrative password, preventing the website owner from logging into the admin panel.

---

## Recommended Security Control

To prevent similar brute force attacks in the future, the organization should implement **multi-factor authentication (MFA)** for administrative accounts.

Multi-factor authentication requires users to verify their identity using an additional authentication method, such as a one-time code from a mobile authentication application. Even if an attacker successfully guesses a password, they would not be able to access the account without the second authentication factor.

Implementing MFA significantly reduces the risk of unauthorized access and provides an additional layer of protection for administrative accounts.
