Design goals of Network Layer

- Independent of technology
- Independent of topology
- Uniform addressing regardless of topology

There are 2 different cultures in Networking

Datagram - which is derived from Telephone Networks. 
- High reliability and centralisation


## Static Routing

Static routing connects nodes together in a tree or graph. 

You different routes can have a "cost" number, which takes in a number of factors like throughput, latency, etc. 

Then optimal paths can be worked out using shortest path, building a routing table


## Dynamic Routing

What if there is a new link, a node fails, etc.

Dynamic routing is where the routing table updates on the fly, one of the big benefits of datagram

