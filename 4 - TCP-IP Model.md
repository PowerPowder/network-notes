# TCP/IP Model

## Overview
### Network Interface
* Physical, Data Link layers
* Describes how to transmit bits, determine how interface uses network medium, cables, network topology

### Internet
* Network layer
* Pack data into IP datagrams, forwarded to different hosts, pushed through routing by using routers, internal (intranet) to external (internet)
* IP, ICMP, ARP, Reverse ARP

### Transport
* Transport layer
* Level of service and status of connection used by TCP (connection full), UDP (connectionless), RTP (real-time)

### Application
* Session, Presentation, Application layers
* Programs interface with transport layer by session managment, users interact with network through programs
* HTTP, Telnet, FTP, SSH, SNMP, DNS, SMTP, SSL/TLS

## Data Transfer Over Networks
* **Port**: logical opening on a system representing a service/application that's listening and waiting for traffic, 0-65535
    * well-known/reserved: 0-1023
    * ephemeral (temporary): 1024-65535
* **IPv4 packet**: source address, destination address, IP flags (packet fragmentation, etc), protocol (TCP/UDP)

<p align="center">
    <img src="images/data transfer.png" width="350px" alt="data transfer">
</p>

## Ports and Protocols

| Protocol | Port Number | Usage |
| --- | --- | --- |
| FTP | 20, 21 | Insecure file transfers - no encryption |
| SSH | 22 | Secure remote control using a command shell |
| SFTP | 22 | Secure file transfers - uses SSH |
| Telnet | 23 | Insecure remote control using a command shell - no encryption |
| SMTP | 25 | Allows to send emails |
| DNS | 53 | Converts domain names to IP addresses and vice versa |
| DHCP | 67, 68 | Automatically assign IP addresses, subnet mask, default gateway, DNS server |
| TFTP | 69 | Lightweight FTP for sending config files and network booting of an OS |
| HTTP | 80 | Insecure web browsing |
| POP3 | 110 | Receive incoming emails, stores and forward communication |
| NTP | 123 | Keep accurate time for clients on a network |
| NetBIOS | 139 | Allows applications on separate device to share files/printers on LAN |
| IMAP | 143 | Retreive emails over a TCP connection, keeps emails synced on all devices |
| SNMP | 161, 162 | Collect info on network devices (routers, switches, etc) and monitor status |
| LDAP | 389 | Directory service on network |
| HTTPS | 443 | Secure web browsing, uses TLS/SSL tunnel |