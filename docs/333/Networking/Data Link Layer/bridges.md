---
lang: en
title: Bridges
viewport: width=device-width, initial-scale=1.0
---
Bridges aren't as commonly seen as routers are in our day to day lives, but we
may run into them in larger networks where different LANs are connected like 
a large network at an office. 

Bridges operate at the Data Link layer which is the 2nd level of the OSI stack, 
the Network Interace layer of the TCP/IP stack.

At this layer, communication is completed in frames and the standard that 
defines the frame depends on the media. For example, there is an Ethernet frame
, token ring frame, wireless LAN frame, and more. Communication is addressed
using **MAC addresses**. 

When a host is initially connected to a bridge, they have no information 
about other hosts that may be connected to the bridge, and the bridge has no
information about what is connected to it. As hosts begin to transmit, the 
bridge can learn (and hosts on the same broadcast domain) which hosts are 
located on which broadcast domains. 

## Addresses
Addresses are 12 hexadecimal characters and are 6 bytes long. 
!!! info
    Hexadecimal ranges from 0 -15, and we need 4 bits to encode each character. 
    4 bits * 12 characters = 48 bits / (8 bits/byte) = 6 bytes

Addresses can be locally unique or globally unique.

You can broadcast by using all 1s: FF:FF:FF:FF:FF:FF. 

Each of the interfaces on a device (ethernet port, wifi port, bluetooth port, 
etc) will have its own addresse, so device may have multiple addresses. 

## Backward Learning Bridges
Bridges broadcast by default at start up. As they receive frames from hosts
they learn which segment that host is on. This is stored in a forwarding table. 
If the destination address is not known, then the frame must be broadcast to
all segments on the bridge.

## Weaknesses
### Silent hosts are not discovered
If a host never transmits, then the bridge will not be able to add them to
the bridges forwarding table, and any inbound traffic to that host will always
broadcasted to all segments/broadcast domains.

### Limited Forwarding Tables
The memory available to store forwarding information is limited, and entries 
will be cleared out according to the eviction policy.

### Broadcast by default
When a bridge is booted up, its forwarding tables are empty, so as it begins
to learn who is on what host it needs to broadcast to all the segments until
the forwarding table is populated. 

## Attacks
### DOS Attack by Overloading Forwarding Table
The attackers aim is to generate a large amount of broadcast traffic over the
bridge network. They can utilize the limited space on the forwarding tables by
sending spoofed source and destination MAC addresses. The spoofed source 
addresses will eventually cause the forwarding table to lose its existing 
entries, and the spoofed destination addresses will mean the frame will need
to be broadcasted to all of the segments.

### Eavesdropping
If you are on the same segment as the host you wish to eavedrop on, then you
only need to set your device to promiscuous mode to receive any traffic, and
if you want to see traffic from other segments, then you can also do a similar
attack to the above to flush the forwarding table. 

### Impersonation
You can change your MAC address to pretend to be a different host. 