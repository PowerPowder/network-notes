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
| FTP | 20/21 | Insecure file transfers - no encryption |
| SSH | 22 | Secure remote control using a command shell |
| SFTP | 22 | Secure file transfers - uses SSH |
| Telnet | 23 | Insecure remote control using a command shell - no encryption |
| SMTP | 25 | Allows to send emails |
| DNS | 53 | Converts domain names to IP addresses and vice versa |
| DHCP | 67/68 | Automatically assign IP addresses, subnet mask, default gateway, DNS server |
| TFTP | 69 | Lightweight FTP for sending config files and network booting of an OS |
| HTTP | 80 | Insecure web browsing |
| POP3 | 110 | Receive incoming emails, stores and forward communication |
| NTP | 123 | Keep accurate time for clients on a network |
| NetBIOS | 139 | Allows applications on separate device to share files/printers on LAN |
| IMAP | 143 | Retreive emails over a TCP connection, keeps emails synced on all devices |
| SNMP | 161/162 | Collect info on network devices (routers, switches, etc) and monitor status |
| LDAP | 389 | Insecure directory service on network |
| HTTPS | 443 | Secure web browsing, uses TLS/SSL tunnel |
| SMB | 445 | Windows file and printer sharing services, uses NetBIOS to auth |
| Syslog | 514 | Send system log/event data to a centralised server (Syslog server) |
| SMTP TLS | 587 | Encrypted version of SMTP |
| LDAPS | 636 | Encrypted version of LDAP (SSL) |
| IMAP over SSL | 993 | Encrypted version of IMAP |
| POP3 over SSL | 995 | Encrypted version of POP3 |
| SQL Protocol | 1433 | Allows client to communicate to Microsoft database engine | 
| SQLnet Protocol | 1521 | Allows client to communicate to Oracle database engine |
| MySQL | 3306 | Allows client to communicate to the MySQL database engine |
| RDP | 3389 | Control Windows client/server remotely with a full GUI |
| SIP | 5060/5061 | Singalling/controlling media communication sessions (VOIP, video calls, instant messaging) |

## IP Protocol Types
* **TCP**: conducts a three-way-handshake between client and server, then establishes connection
* **UDP**: detects corrupt packets when received by a client using a checksum
* **ICMP**: communicate info about network connectivity issues back to sender
* **Generic Routing Encapsulation (GRE)**: create a GRE tunnel over a public network, encapsulates the data, is a virtual point-to-point link.
* **Internet Protocol Security (IPSec)**: secure protocols at networking/packet processing layer used to protect data flows between peers. Two protocols used in IPSec: 
    * Authentication header (AH) - provides integrity and authentication
    * Encapsulating Security Payload (ESP) - provides encryption and integrity for data packets sent over IPSec