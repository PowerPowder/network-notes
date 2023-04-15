## Ethernet Fundamentals
* Ethernet uses contention-based (chaotic) network access
* **CSMA/CD**: devices listen and wait for turn to transmit, if two devices transmit at the same time then set a random backoff timer for both devices to transmit again.
* **Collision Domains**: all devices on a shared ethernet segment (on same cable/hub), all devices are suspectible to colliding with each other, more collision domains = less collisions.
* **Ethernet standards**:
    * Copper - Cat 3, 5, 5e, 6, 7, 8 (all are up to 100m except for Cat 8 which is 30m)
    * Fibre - MMF (200-500m), SMF (40km)

### Infrastructure Devices
* **Hub**: repeats signals from a port to all other ports
    * Passive hub - repeat signal with no amplification
    * Active hub - repeats signal with amplication (reset CAT X length)
    * Smart hub - active hub with features like SNMP
* **Bridge**: analyses source MAC addresses, generates MAC address table and makes forwarding decisions based on destination MAC addresses
* **Switch**: connects network segments, each port is pretty much a bridge, generates routing table from previous routes
* **Broadcast Domain**: collection of devices that have an ARP packet sent to each device to figure out who's who
* **Router**: connects networks together, makes routing decisions, each port is a different collision/broadcast domain
* **L3 Swtich**: makes routing decisions and connects networks (router), not just network segments (like a L2 switch)