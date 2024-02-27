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


## Weaknesses

## Attacks
