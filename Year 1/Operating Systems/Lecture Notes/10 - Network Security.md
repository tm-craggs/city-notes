## Introduction to Networks

##### Networks and distributed systems

- Computers are inter-networked and must communicate and cooperate
- Networks allow the exchange of information between hosts through a series of applications that are ruled by a series of protocols
- The information exchanged by the hosts together with other control messages are transmitted through a large variety of access media that interconnect many intermediate devices. 

##### The internet

- Devices = hosts. They are a series of very different devices connected to "the internet"
- Each device (hosts/end systems) needs to connect through some media
- One physically connected, a route between devices is established through a series of links and packet switches (it is not always fixed)
- The information is transported through packets, and a series of protocols (HTTP, FTP, SMTP, TCP...) make the transmission possible.
- Alternatively, the internet is an infrastructure that provides services to applications 
- In the end, all that matter is the exchange of information, but the information is embedded with a lot of other information in a complex way. 

##### Layers, Services, Interfaces, Entities, Protocols and Models

- A set of protocols is called a network architecture. The definition of layers form a model.
- Rules or agreements between layers are called protocols. 
- The conceptual network is divided into layers to reduce design complexity. 
- A layer (n) provides a service to the layer above it (n+1) and an interface defines the services and operations between them. 
- An active element (either software process of a hardware element) in a layer is called an entity. 

##### HTTP request and reply

- HTTP request sent into TCP socket
- IP datagram containing HTTP request routed to ``www.google.com`` 
- Web server responses with HTTP reply (containing web page)
- IP datagram containing HTTP reply routed back to client. 

## Network Security

- Physical Layer: Using encapsulating transmission lines or using fibre optics
- Data Link Later: Encrypting packages from point to point
- Network Layer: IPsec, firewalls
- Transport Layer: Entire connections being encrypted
- Intermediate layers: Secure Socket Layer

##### IP Security

- Where to put the security?
	- Authentication Header (AH) - Provides integrity and anti-replay security but not secrecy
	- 

## Encryption

## Further Topics

## Wrap Up

