# Wide Area Networks

## Wired WAN Connections
* **Dedicated Leased Line**: unshared dedicated connection through service provider's facility
* **Circuit-Switched**: connection brought up when needed, like a phone call
* **Packet-Switched**: always on dedicated lease line but with multiple customers
    * **Service Level Agreement (SLA)**: guarantee certain quality (5mbps, at least 80% of the time)
* **WAN Physical Media**: copper wires (UTP, STP, Coaxial), fibre-optic, electric power lines

## Wireless WAN Connections
* **Cellular (Phones and Hot Spots)**:
    * 1G, 2G, 3G, 4G, 5G (low/mid/high bands, higher = less coverage but faster)
    * **Global System for Mobile Communications (GSM)**: converts voice to digital during a call, uses SIM card
    * **Code-Division Multiple Access (CDMA)**: splits up channel with code division, calls encoded with unique key
* **Microwave**: beam of radio waves transmitted between two fixed locations, antennas require line of sight
    * WiMax - antenna installed on roof, faster than 2G, 3G, 3.5G
    * Satellite - slow, expensive, high latency connection, used for remote areas, flights and ships
    * High-Frequency Radio - very slow connection, used in disaster relief and military scenarios

## WAN Technologies
* **Dedicated Leased Line**: bandwitdth available at all times, Channel/Data Service Unit (CSU/DSU) terminates signal at demarc point, digital signal circuits - T1 (1.5Mbps), T3 (45Mbps), E1 (2.0Mbps)
* **Metro Ethernet**: ethernet interface offered by service provider, technology used is hidden from customer
* **Point-to-Point Protocol (PPP)**: L2 protocol on dedicated lease lines to transmit L3 protocols
    * Each layer 3 control protocol runs an instance of PPP's Link Control Protocol (LCP)
        * Multilink interface - bind multiple connections for higher bandwidth
        * Looped link detection - detect and prevent L2 loops
        * Error detection - detect and discard frames containing errors
        * Authentication - device on the other end can auth the link
            * PAP - one-way auth between client/server in cleartext
            * CHAP - one-way auth using three-way handshake, creds are hashed
            * MS-CHAP - two-way CHAP
* **PPP over Ethernet (PPPoE)**: turn PPP frames into ethernet frames, DSL modems use this
* **Digital Subscriber Line (DSL)**: 
    | DSL Type | Max DSLAM<br>Distance | Down | Up |
    | --- | --- | --- | --- |
    | **A**symmetric **DSL** | 5.5 km | 8 Mbps | 1.5 Mbps |
    | **S**ymmetric **DSL** | 3.5 km | 1.15 Mbps | 1.15 Mbps |
    | **V**ery High Bit-Rate **DSL** | 1.2 km | 52 Mbps | 12 Mbps |
* **Cable Modem**: uses cable TV infrastructure (HFC - coax and fibre in cable)
* **Satellite Modem**: for remote/rural/disconnected locations, at least 250ms delay, weather affects service
* **Plain Old Telephone Service (POTS)**: public switched telephone network, worldwide, analogue
* **Integrated Services Digital Network (ISDN)**: combines multiple 64 kpbs Bearer channels
* **Frame Relay**: create virtual circuits (VCs) to connect remote LANs to WAN
* **Synchronous Optical Network (SONET)**: fibre media, 155 Mbps to 10 Gbps+, 20km-250km, ring/bus top (FDDI ring)
* **Asynchronous Transfer Mode (ATM)**: uses Permanent VCs and Switched VCs frames are 53 byte fixed-length cells (5B header, 48B payload)
    * VCs - User-Network Interface (UNI - connect ATM switches and endpoints) and Network-Node Interface (NNI - connect ATM switches)
* **Multiprotocol Label Switching (MPLS)**: backbone for service providers, supports frame relay and MPLS, faster than L3 IP routing
* **Dynamic Multipoint VPN (CMVPN)**: Internet used as WAN connection for secure site-to-site communication

| WAN<br>Technology | Bandwidth | Media |
| --- | --- | --- |
| Frame Relay | 56 kbps - 1.5 Mbps | ? |
| T1 | 1.5 Mbps | ? |
| T3 | 45 Mbps | ? |
| E1 | 2 Mbps | ? |
| E3 | 35 Mbps | ? |
| ATM | 155 Mbps - 622 Mbps | Fibre |
| SONET | 52 Mbps - 160 Gbps | Fibre |

## Other WAN Technologies
* **Software-defined WAN (SDWAN)**: virtual WAN arch that allows enterprises to combine any WAN technologies (abstract hardware into software), centralised control function is used to securely/intelligently redirect across WAN
* **Multipoint generic routing encapsulation (mGRE)**: point-to-multipoint network, create tunnels from one node to many nodes with DMVPN