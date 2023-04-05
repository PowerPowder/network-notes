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

#### Multiplexing - TDM, StatTDM, FDM
* **Time-Division Multiplexing**: take turns using a time slot
* **Statistical TDM**: dynamically allocate time slots to devices who need bandwitdth
* **Frequency-Division Multiplexing**: split into channels like broadband, each person gets an amount of portions

## L2 - Data Link (Frames)
* **Media Access Control**: physically identify device, first half is vendor code, second half is unique value
* **Logical Link Control (LLC)**: flow control (limit messages if needed), error control (checksum), acknowledge receipt (received right message)
* **Isochronous**: common reference clock, create time slots for transmission
* **Synchronous**: limited to agreed clock for frame start and end, use control characters
* **Asynchronous**: devices reference own clock cycles and own start and stop bits.
* **Devices**: NICs, switches, bridges

## L3 - Network (Packets)
## L4 - Transport (Segments)
## L5 - Session (Data)
## L6 - Presentation (Data)
## L7 - Application (Data)