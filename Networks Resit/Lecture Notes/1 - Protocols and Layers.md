**Computer Network** - 2 or more independent computers communicating with a common technology

## Types of Network

Examples of networks:

-  The internet
-  World Wide Web
-  E-Mail
-  Signal / WhatsApp
-  Telegram
-  Plain Old Telephone System (POTS)
-  Cellular Phone (3G/4G/5G)
-  Cable TV
-  USB
-  Ethernet
-  Bluetooth
-  NFC
-  GPS

Networks can have different attributes

**Scale:** PAN, LAN, MAN, WAN, etc.
**Topology**: star, complete graph, mesh, etc.
**Dynamic** vs **Static**
**Centralised** vs **Federated** 
**Open**?

Take Bluetooth:
Scale: PAN
Topology: Point-to-point, where there are only 2 devices. Bluetooth can also be used as a Star, where one master connects to numerous children, or as a mesh where every device is connected to every other device. 
Bluetooth uses a dynamic topology, as it automatically works out best paths for data using routing protocols, rather than manually configured or fixed routes.
Bluetooth is typically centralised
Bluetooth is not open


What is **Scale**?

- On the smallest scale, you have PAN (Personal Area Network) mostly designed for connecting personal devices that are on your person
- A step up is LAN (Local Area Network), connecting all the devices within a reasonable distance, mostly a room or a building such as houses. 
- Another step up is a MAN (Metropolitan Area Network) designed to connect devices across a City, such as ADSL which was a phone network across cities.
- Finally, the largest scale is a WAN (Wide Area Network) designed to operate at global scale. Examples are the Internet or E-Mail. 

What is **Topology**?

-  A topology is the layout of how a network is formed. 
- Graph Theory is used to describe how networks look, by modelling Computers as nodes and edges as connections. Edges are typically directed and allow 2 way connections, but there can be one way or directed connections. 
- Star Topology - Central node that acts as a server, all connections run through it
- Mesh Topology - Every computer is connected to every other computer

**Dynamic/Mobile vs Static**

- Can the topology of the network change? Is a good way to distinguish between dynamic or static networks
- With dynamic networks, it is not an error if a node goes offline for example.
- Another difference can be in the type of connection. In cell networks, your phone can move from being in range of one tower to another, and you will not notice. However in static networks that use Ethernet, you cannot unplug something and plug it back in somewhere else. 

**Centralised vs Federated**

- Refers to how much control people have
- The internet was designed as federated, different people in different countries control different parts of it and they were wired up together. 

**Open**

- Different people have different definitions of what open means.
- Is it open source? Is it encrypted? 


**Packet vs Stream**

**Connection-oriented vs Connectionless**

**Broadcast Vs Unicast vs Multi-cast**

**Synchronous vs Asynchronous**

**Reliable vs Unreliable**

**Security: Confidentially / Integrity / Availability**

**Data vs Meta-Data**

## Protocols

**Protocol** - An agreed way of communicating between computers

Protocols govern:

- Formatting of messages
- Fixed meaning or semantics of messages
- Defines the roles that different computers take, such as client/server or peer-to-peer
- Not an algorithm, it does not give you a definite order. It will tell you, here is how the connection starts, here are the actions you can take. 
- It is also not an implementation, protocols are just the rules. The clients are the implementations. 

Factors:

- Resource allocation
- Reliability
- Evolvability
- Security


Protocol Stacks

Because of all the factors we talked about, and all the different considerations that need to be made, it is hard to make 1 protocol that does everything. 

Instead, separate protocols are layered on top of each other that do different things. 

**The TCP/IP Stack**

Application
Transport
Network
Link
Physical

Physical: This is how the Computer can change a bit on another computer
Link: How can you communicate with the next computer you are connected to
Network: How can you connect to other computers that you aren't directly connected to
Transport: How data can be transported across networks
Application: How you can actually do things?
