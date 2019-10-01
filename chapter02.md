# cs291_Chapter2

TCP / IP

TCP provides an abstraction of a reliable network

- Retransmission of data loss
- In-order  delivery
- Congestion Control and Avoidance
- Data Integrity

TCP is optimized for accurate delivery and not a timely one

Http doesn't require TCP. But it mostly uses TCP

All TCP  connections have a 3-way  handshake

- Syn: Client  picks a random sequence number x and sends a SYN packet which includes additional TCP flags and options

- Syn Ack: Server increments x by one, picks own random sequence number y, and appends its own set of flags and options
  
- Ack: Client increments both x and y by one and completes the handshake by dispatching the last ack packet in the handshake
