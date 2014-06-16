## Propmt 1

**A router is able to process packets at the rate of at most r packets/second. It drops an incoming packet before processing with probability p so that it does not get overwhelmed.**

### Question 1

**How can you represent traffic intesnity in terms of r, p, and a where a is the average packet arrival rate.**

Traffic intensity is defined as

$$\frac{\text{Length of a packet (bits)} \text{Average packet arrival rate (packets/sec)}}{\text{throughput (bits/second)}}$$

$$\frac{(1-p)A}{R}$$

### Question 2

## Prompt 2

**Suppose a file of size $f$ has been split into $m$ equal pieces and scatterd across n peers, where $m \geq n$ and each peer has at least one piece**

## Prompt 3

**In the lecture, we discssed a scnario in which TCP's 3-way handshake for connection setup is more robust than a 2-way handshake**

### Question 1

**Name all the ways a two-way handshake could fail.**

 - In a two way handshake, the server cannot differentiate between a client that doesn't want to send any data right away and one that did not receive the `SYN+ACK` message.
 - If the client's `SYN` message times out and it retransmits, the server may still receive both `SYN` packets and try to open two connections. It has no way of knowing what connection requests are valid.

### Question 2

**Draw a sequence diagram of a 3 way handshake occururing between a client and server in which the first `SYN+ACK` packet is lost.**

## Prompt 4

**TCP is a Go-Back-N protocol, in which an ACK is cummlative. That is, if a receiver sends an ACK with ACK #12345, this means that it has also recieved all bytes up to and including byte number 12344 without error.**

 - The server does not buffer packets ever for GBN.
 - If an ACK goes missing but a subsequent ACK is received, the client does not need to resend any data.
 - If a timeout occurs, the sender resends all packets that have been previously sent but that have not yet been acknowledged.
 - The window is moved forward after a segment has been ACKed

### Question 1

**Draw a sequence diagram of a client sending 5 data packets to a server with a window size of 3 in wich the second message from the *server* is lost. You may assume the client and server already have an open connection.**

### Question 2

**Draw a sequence diagram of a client sending 5 data packets to a server with a window size of 3 in wich the second message from the *client* is lost. You may assume the client and server already have an open connection.**