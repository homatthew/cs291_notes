# cs291_ch1 Notes
Latency
: The time from the source sending a packet to the destination receiving it
(latency is expensive)

Bandwidth
: Maximum throughput through physical path


latency = Propogation +  transmission + processing + queueing 

1. Propogation Delay is proportional to distance and medium

2. Transmission Delay is dictated by available data rate and has nothing to do with distance

3. Once the packet arrives, the router must examine the packet header to determine the outgoing route and other possible checks.

4. If the packets arrive at a faster rate than the router is capable of processing, the packets are queued inside a buffer.

These delays may happen multiple times for a given packet
