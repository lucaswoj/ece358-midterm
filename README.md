### A router is able to process packets at the rate of at most r packets/second. It drops an incoming packet before processing with probability p so that it does not get overwhelmed.

#### How can you represent traffic intensity in terms of r, p, and a where A is the average packet arrival rate.**

Traffic intensity is defined as

$$\frac{\text{Length of a Packet (bits)} \cdot \text{Average Packet Arrival Rate (packets/sec)}}{\text{Throughput (bits/second)}}$$

So, using our givens, the answer is

$$\frac{(1-p)A}{R}$$






### Suppose a file of size $f$ has been split into $m$ equal pieces and scatted across $n$ peers, where $m \geq n$ and each peer has at least one piece

#### Question 1

**Suppose that you can connect to at most $j$ peers, where $j = \frac{n}{2}$, and the maximum link bandwidth between you and a peer is $m$ bits/second. How long does it take to download the whole file?**






### In the lecture, we discussed a scenario in which TCP's 3-way handshake for connection setup is more robust than a 2-way handshake

#### Name all the ways a two-way handshake could fail.

 - In a two way handshake, the server cannot differentiate between a client that doesn't want to send any data right away and one that did not receive the `SYN+ACK` message. Therefore, it may keep a connection open to a client that has terminated.
 - If the client's `SYN` message times out and it retransmits, the server may still receive both `SYN` packets and try to open two connections. It has no way of knowing what connection requests are valid.

#### Draw a sequence diagram of a 3 way handshake occurring between a client and server in which the first `SYN+ACK` packet is lost.






### TCP is a Go-Back-N protocol, in which an ACK is cumulative. That is, if a receiver sends an ACK with ACK #12345, this means that it has also received all bytes up to and including byte number 12344 without error.

 - The server does not buffer packets ever for GBN.
 - If an ACK goes missing but a subsequent ACK is received, the client does not need to resend any data.
 - If a timeout occurs, the sender resends all packets that have been previously sent but that have not yet been acknowledged.
 - The window is moved forward after a segment has been ACKed

#### Draw a sequence diagram of a client sending 5 data packets to a server with a window size of 3 in which the second message from the *server* is lost. You may assume the client and server already have an open connection.

#### Draw a sequence diagram of a client sending 5 data packets to a server with a window size of 3 in which the second message from the *client* is lost. You may assume the client and server already have an open connection.