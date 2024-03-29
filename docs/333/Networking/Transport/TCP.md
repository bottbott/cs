---
lang: en
title: TCP
viewport: width=device-width, initial-scale=1.0
---
TCP is an IP communication protocol to send data to another host. The TCP 
protocol takes place on the Transport layer of the OSI model, and the TCP/IP 
layer of the TCP/IP model. After hosts and routers have figured out via ARP
how to communicate with other hosts on the segment, and routers know how to 
route IP traffic, then we can set up a connection between two hosts with their
IP addresses and ports. Ports are typically mapped to a process. 

## TCP Handshake
To begin a connection with another host:
1. the client sends a SYN (synchronize), and CSEQ (client sequence number).
2. the destination responds with a SYN, ACK (acknowledgement), CSEQ+1, and SSEQ.
3. the client sends ACK, SSEQ+1, and CSEQ+1 (and optionally data).

```mermaid
sequenceDiagram
    participant Client
    participant Server

    Client->>+Server: SYN, CSEQ
    Note right of Server: Server allocates memory to preserve state.
    Server-->>-Client: SYN, ACK, CSEQ+1, SSEQ
    Client->>Server: ACK, SSEQ+1, CSEQ+1
    Note left of Client: Client could send data here.
    Note right of Server: After session is made, SEQ is only incremented with data being sent.
    Note right of Server: SEQ will eventually wrap around.
```

## SYN Cookie
In the weaknesses listed below, we mention that the server must allocate space 
during the handshake process and that this exposes an attack vector for a large 
number of attacks to deplete the space on the server. 

SYN Cookies are an approach to make the connection stateless so that the server 
can not be exhausted. The server encodes state information when it responds to 
the clients SYN request. 

```mermaid
sequenceDiagram
    participant C as Client
    participant S as Server

    Note over C,S: TCP Three-Way Handshake with SYN Cookies

    C->>S: SYN, CSEQ (Client initiates connection)
    Note over S: Server calculates SYN cookie: time, max segment size,<br/>and hash of (client's IP, port, server IP, port, and a timestamp)
    S->>C: SYN, ACK, CSEQ+1, SSEQ<br/>(Server responds with SYN cookie as sequence number)
    Note right of S: Server does not store any<br/>connection state.

    Note over C: Client increments the SSEQ number.
    C->>S: ACK, SSEQ+1, CSEQ+1 (Client acknowledges, includes SYN cookie)
    Note over S: Server verifies SYN cookie.
    Note right of S: If valid, server reconstructs<br/>connection state and proceeds.

    Note over S,C: Connection Established
```

When the server does receive the packet, it can inspect the time embedded in 
the cookie to see if the cookie has expired, and it can recompute the hash of 
the IPs/ports/time. 


## Weaknesses
### Handshake allocates state space at destination
Whenever the TCP handshake is initiated the destination will set aside some 
space to store state information. Under great load this may deplete the space
available at the destination device.    

### Port probing
Requests can be sent to any port address to determine if those services are 
available/online, and then an attack could be tailored to the service at the
port. 

### Sequence Number Predictability
If an attacker can determine the sequence numbers, they can impersonate the 
client and send information. 

## Attacks
### SYN Flood
Since we have servers that will allocate space from clients initiating 
connections, we can rotate in a large load of connection requests from spoofed 
IPs and deplete the space that is allocated for connections.

### Session Hijacking via Initial Sequence Number Impersonation
If these numbers can be guessed then an attacker can impersonate the host and
send traffic to the destination. The attack begins as one way as the attacker
tries to send malicous data that will allow them to gain further control such 
as trying to overwrite the targets login details. 

```mermaid
sequenceDiagram
    participant C as Client
    participant S as Server
    participant A as Attacker

    A->>+S: Make handshake connections to determine<br/>SSEQ generation algorithm at server
    A->>+S: SYN[Src=C, Dst=S, CSEQ=X]
    Note over S, A: Attacker impersonates C.
    S-->>-C: SYN/ACK [Src=S, Dst=C, CSEQ=X+1, SSEQ=Y]
    A->>+C: Bogus SYN DDOS attack to have client miss the server<br/>SYN/ACK backscatter and prevent Client from issuing RST
    Note over S, A: Attacker attempts to guess SSEQ
    A->>S: ACK [Src=C, Dst=S, CSEQ=X+1, SSEQ=Y+1] w/malicious data payload
    Note over C, A: Attacker continues to send to<br/>server until payload is successful and continues DDOSing client to prevent the connection from closing.
```