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


The last few  miles is where a significant amount  of  latency is introduced

**Latency not bandwidth is the performance bottleneck for most websites**

The available bandiwdth at the core network is greater than at the Network Edge. Even  if a speedtest  says that you have a high-bandwidth link, the network could be congested at any intermediate node due to high demand etc.

##  Make distance shorter
As a result, to improve performance of our applications, we need to architect and optimize our protocols and networking code with explicit awareness of the limitations of available bandwidth and the speed of light: we need to reduce round trips, move the data closer to the client, and build applications that can hide the latency through caching, pre-fetching,


