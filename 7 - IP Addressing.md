## IP Addressing

* Classes of IPs, subnetting is network bits then host bits
| Class | 1st Octet Value | Default Subnet Mask | CIDR Notation | Possible Hosts |
| :-: | :-: | :-: | :-: | :-: |
| A | 1-127 | 255.0.0.0 | /8 | 16.7 million |
| B | 128-191 | 255.255.0.0 | /16 | 65,536 |
| C | 192-223 | 255.255.255.0 | /24 | 256 |
| D | 224-239 | n/a | n/a | n/a |
| E | 240-255 | n/a | n/a | 268 million<br>(reserved)|

* **Multicast Address**: identifier for a group of hosts in a network
* **Classful Mask**: using default subnet mask for address class
* **Subnetting**: use classless subnet mask to create smaller networks with fewer hosts
* **Public IP (Routable)**: can be accessed over the internet, assigned by ISP
* **Private IP (Non-Routable)**: can be used by anyone anywhere in a LAN
| Address<br>Class | Address<br>Range Start | Address<br>Range End | Default<br>Subnet Mask |
| :-: | :-: | :-: | :-: |
| Class A | 10.0.0.0 | 10.255.255.255 | 255.0.0.0 |
| Class B | 172.16.0.0 | 172.31.255.255 | 255.255.0.0 |
| Class C | 192.168.0.0 | 192.168.255.255 | 255.255.255.0 |
* **Specialised IPs**:
    * Loopback/Localhost Address (127.0.0.1) - send data to the host itself, used to test network protocols and troubleshoot
    * Automatic Private IP Addresses (APIPA) - used when a device does not have a static IP or can't reach DHCP server. Ranges from 169.254.0.0 to 169.254.255.255
* **Virtual IP Address (VIP)**: IP address that does link to a NIC, used for NAT, fault-tolerance, virtualisation
* **Subinterfaces**: virtual interface created by dividing up a physical interface

### Data Flows
* **Unicast**: data goes from single device to single device (single)
* **Multicast**: data goes from single device to multiple devices (group)
* **Broadcast**: data goes from single device to all devices on a network (everyone)

### Assigning IP Addresses
* **Static**: manually type in IP, subnet mask, default gateway, DNS server (or WINS - uses NetBIOS to IP address)
* **Dynamic**: dynamically allocate IP addresses, DHCP server does everything automatically
    * Bootstrap Protocol (BOOTP)
    * Dynamic Host Control Protocol - assign IPs based on range of addresses (scope), allows to lease IPs (IPs given expiry date)
    * Automatic Private IP Addressing (APIPA) - used when device doesn't have static IP or cannot reach DHCP server, self assign without DHCP server on LAN, 169.254.0.0/16
    * ZeroConf - updated APIPA, assign IPv4 link-local addresses, resolve computer names to IPs, performs self discovery on network

### Subnetting
* Is taking a large network and splitting into smaller networks, improves efficiency, security, bandwidth control
<p align="center">
    <img src="images/subnets.png" width="300px" alt="Subnet demo">
</p>
* Formula for number of subnets: **2^s**, s is the number of borrowed bits, 192.168.1.0/26, default is /24, 2^2 = 4 subnets
<p align="center">
    <img src="images/subnets2.png" width="400px" alt="Subnet number">
</p>
* Formula for assignable hosts: **2^h - 2**, h is host bits, 2 IPs are needed Network ID (first IP in range, name of network) and Broadcast ID (last IP in range)