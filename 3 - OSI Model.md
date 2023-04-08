## OSI Model
<u>**A**</u>ll
<u>**P**</u>eople
<u>**S**</u>eem
<u>**T**</u>o
<u>**N**</u>eed
<u>**D**</u>ata
<u>**P**</u>rocessing

# Flip layer order when done

## L1 - Physical (Bits)
* **Media** - cables (fibre optic, ethernet, coaxial), radio (bluetooth, wifi, nfc)
* **Devices** - hubs, access points, media converters
* **Asynchronous**: start and stop bits sent from sender to receiver
* **Synchronous**: take turns using a reference clock from sender and receiver
* **Bandwidth**:
    * Broadband - divide into separate channels, like tv channels
    * Baseband - use all frequencies on the cable all the time, like a phone call

#### Multiplexing (all for baseband) - TDM, StatTDM, FDM
* **Time-Division Multiplexing**: take turns using allocated time slots
* **Statistical TDM**: dynamically allocate time slots to devices who need bandwitdth
* **Frequency-Division Multiplexing**: split into channels like broadband, each person gets an amount of portions

## L2 - Data Link (Frames)
* **Media Access Control**: physically identify device, first half is vendor code, second half is unique value
* **Logical Link Control (LLC)**: flow control (limit messages if needed), error control (checksum), acknowledge receipt (received right message)
* **Isochronous**: agreed on reference clock, create time slots for transmission
* **Synchronous**: limited to agreed clock for frame start and end, use control characters
* **Asynchronous**: devices reference own clock cycles and own start and stop bits.
* **Devices**: NICs, switches, bridges

## L3 - Network (Packets)
* **Logical addressing**: ipv4 (172.16.254.1), ipv6 (fe80::7d25:7e1a:b79d:67e4 - 0's are omitted)
* **Switching (routing data)**:
    * Packet - data is divided into packets and forwarded based on IP address
    * Circuit - dedicated link between two devices, data is sent over a path of circuits to the destination
    * Message - data is divided into messages and are stored and forwarded, like email.
* **Route discovery and selection**: routers can route statically (use same path) or dynamically (figure out best path). Protocols used are RIP, OSPF, EIGRP
* **Connection services**: improve reliability L2 services - flow control (send more or send less), packet reordering (packets are numbered, if in wrong order then put them in right order)
* **Internet Control Message Protocol (ICMP)**: send messages and operational info to an IP dest - ping, tracert
* **Devices**: Routers, multi-level-switches (L2 switch and L3 router)

## L4 - Transport (TCP - Segments, UDP - Datagrams)
* **TCP** is more overhead but is reliable, **UDP** has less overhead and is unreliable
| TCP | UDP |
| --- | --- |
| Reliable | Unreliable |
| Connection-oriented | Connectionless |
| Windowing and segment retransmission | No windowing or retransmission |
| Segment sequencing | No sequencing |
| Acknowledges segments | No acknowledgement | 

* **Three-way-handshake**:
<p align="center">
    <img src="images/3WH.png" width="250px" alt="three way handshake">
</p>

* **Windowing**: allows clients to adjust the amount of data in each segment, more retransmissions = decrease window, no retransmissions = increase window, this is used to get the maximum throughput of the network.

* **Buffering**: memory allocated on devices to store segments if bandwidth isn't available, 'clearing the buffer' is going through the stored segments in the buffer.

* **Devices**: WAN accelerators, load balancers and firewalls

## L5 - Session (Data)
## L6 - Presentation (Data)
## L7 - Application (Data)