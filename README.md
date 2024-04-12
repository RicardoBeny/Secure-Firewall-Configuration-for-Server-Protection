# Secure-Firewall-Configuration-for-Server-Protection

This project seeks to fortify server security by implementing an iptables firewall configuration that effectively manages incoming and outgoing network traffic. Employing a deny-by-default policy, the firewall selectively permits essential services while thwarting unauthorized access attempts. Key features include support for HTTP versions 1.1, 2, and 3, ensuring secure SSH access with fail2ban protection, leveraging sshttp for SSH/HTTP(S) multiplexing on port 443, and maintaining comprehensive logging of internet-facing traffic. Additionally, flood protection mechanisms will be instituted to counter potential denial-of-service (DoS) attacks, thereby ensuring server stability and reliability during peak traffic conditions.

### Deny-by-Default Policy:
- Configure the iptables firewall to deny all incoming and outgoing traffic by default.

### Server Services Allowed (IN):
- Permit HTTP versions 1.1, 2, and 3.
- Enable SSH with fail2ban protection and asymmetric key login.
- Configure sshttp for SSH/HTTP(S) multiplexing on port 443.
- Allow ICMP ping.

### Client Services Allowed (OUT):
- Allow DNS and DNS over TLS.
- Permit ICMP ping.
- Allow SSH, git, docker, whois, HTTP, and HTTPS.

### Additional Requirements:
#### Logging:
- Ensure logging of all traffic related to internet-exposed services (IN).
- Log and reject all invalid packets (IN and OUT).

#### Flood Protection:
- Implement flood protection for incoming connections (IN).
- Restrict ICMP packet flood to 5 per second.
- Limit UDP packet flood to 10 per second, with a tolerance of 50.
- Cap TCP packet flood to 50 per second, with a tolerance of 100.
- Exclude SSH service from TCP flood protection.
