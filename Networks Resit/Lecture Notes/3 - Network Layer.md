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

Flood Routing

- Every message has a unique ID
- When you get a new message, send a copy to every neighbour
- Very robust, and correct, but not very fair or efficient

Link State Routing (OSPF)

- Everybody floods out who they are, and what links they have
- After a while, every node will have a complete network map 
- Every node computers minimum spanning tree, make their routing paths based on their own view
- You can end up with endless loops if everything falls out of step
