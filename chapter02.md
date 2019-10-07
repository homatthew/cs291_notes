# cs291_Ch2 notes

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

TCP connection requires 3 trips. Connection reuse is important.

TCP Fast open allows data transfer within the SYN packet. Howeverm there is a data limit within the SYN packet

## TCP congestion Avoidance and Control

If the roundtrip time exceeds the maximum retransmission interval for any  host, that host will begin to introduce more and more copies of the same datagrams

- Stable condition. Once the saturation point is reached, the algorithm will continue to operate in a degraded condition

## Flow Control

Mechanism to prevent sender from overwhleming the receiver with data it  may not be able to process.

1. Each side of the TCP connection advertises its own receive window, which communicates buffer space to hold the incoming data
2. Each packet dynamically adjusts the data flow by piggybacking the latest rwnd value in each ACK packet

## Slow-Start

Flow control doesn't prevent the sender from overwhelming the underlying  network.

The server initializes a new congestion window per TCP connection and sets its initial value to a conservative system-specific value

- Congestion Window Size (cwnd) : Sender-side  limit on t he amount of data the sender can have in flight before receiving an ack from the client. The cwnd variable is stored on the server (Not client or receiver). **Note: We cannot use the full capacity immediately**

1. Start with small congestion window and double for every round trip.
2.  Time  = RTT x (Log_2(1 + n/initcwnd))
this is an issue for http connections which are short

TCP  also resets the congestion widnwo after it has been idle for a defined  period  of time
**Avoid this by reusing TCP connection**

## Congestion Avoidance

TCP uses packet loss as a feedback mechanism. This means that it's a matter of when not if there is packet loss.

## Bandwidth Delay Product

The optimal sender and receiver window sizes must vary based on the roundtrip time and target data rate between them.


