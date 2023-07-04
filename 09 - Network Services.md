# Network Services

## Dynamic Host Configuration Protocol (DHCP)
* Automatically assigns devices with IP addresses, provides them a subnet mask, default gateway and DNS server
* Provides IP to every machine on network, eliminates configuration errors
* **Scope**: IPs available for assignment/lease to a client/endpoint device on a subnet
* **DHCP Reservation**: exclude some IPs being assigned/leased unless they meet a condition
* DORA Process
    * Discover - I need an IP
    * Offer - does this one look good?
    * Request - yes, I request to use it
    * Acknowledge - ok that's your IP
* DHCP requires IP address, subnet mask, default gateway IP, DNS server IP
* **DHCP Relay**: forward DHCP packets between clients/servers, used when client and DHCP are not on the same subnet/network

## Dynamic Name System (DNS)
* Converts domain names to IP addresses - phone book for the internet
* **Zone Transfer**: send DNS records from primary nameserver to secondary nameserver, uses TCP
* **Fully-Qualified Domain Name (FQDN)**: the full address eg www.google.com
* **Uniform Resource Locator (URL)**: method of access and FQDN - https://www.google.com
* **Forward Lookup**: use DNS to get IP for a domain name
* **Reverse Lookup**: use DNS to get domain name for an IP

### DNS Hierarchy Tree
| Domain | Example |
| :-: | :-: |
| Root | Answers requests in the root zone<br>(contains global list of top-level domains) |
| Top-Level Domain | .com, .au<br>(organisational, geographical)|
| Second-Level Domain | google.com |
| Subdomain | www.google.com<br>translate.google.com |
| Host | Refers to a specific machine |

### DNS Records
| DNS Record | Description | Function |
| :-: | :-: | :-: |
| A | Address | Link hostname to IPv4 address |
| AAAA | Address | Link hostname to IPv6 address |
| CNAME | Canonical Name | Point to another domain/subdomain |
| MX | Mail Exchange | Indicates how email messages are routed with SMTP |
| SOA | Start of Authority | Store info about a domain/zone (last updated, wait time for a zone transfer)
| PTR | Pointer | Correlates IP with a domain name |
| TXT | Text | Adds text into the DNS, store machine-readable data |
| SRV | Service | Specifies a host and port for a specific service |
| NS | Nameserver | Indicate which DNS nameserver is authoritative for a domain (CloudFlare) | 

* Internal/External DNS: they have a TTL - tells DNS resolver how long to cache query before requesting a new one
    * **Internal DNS**: allows cloud instances (on same local network) to access each other using internal DNS names
    * **External DNS**: records created around domain names from central authority and used on the internet
* **DNS Resolver/Cache**: temporary database that remembers results from DNS server
    * Recursive lookup - DNS server hunts and reports to resolver, ISP -> go down DNS hierarchy tree
    * Iterative lookup - DNS resolve queries DNS servers until it finds the right IP for the domain

## Network Time Protocol (NTP)
* Synchronise clocks between systems on a packet-switched, variable latency network
* How it works:
    * Stratum - hierarchy of reference clocks (starts at stratum 1, max is 15), more delay is added for each stratum
    * Clients
    * Servers