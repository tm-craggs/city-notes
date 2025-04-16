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
	- Encapsulating Security Payload (ESP) - Better option can manage security

##### SSL: Secure Sockets Layer

- Widely adopted security protocol
- TLS (transport layer security) is another variation
- Provides:
	- Confidentiality
	- Integrity
	- Authentication

##### SSL Record Protocol

- Record header - content type, version, length
- MAC - Includes sequence number, MAC ket, 
- Fragment - Each SSL fragment is 2<sup>14</sup> bytes

![[image-19.png|352x233]]

##### Network Security - Summary

**Basic Techniques**
- Cryptography (symmetric and public)
- Message integrity
- End-point encryption

**Used in many different security scenatios**
- Secure transport (SSL)
- IP sec
- And more... (firewalls, secure mail)

## Encryption

- Broadest security tool available. 
	- Internal to a given computer, source and destination of messages can be known and protected. 
		- OS creates, manages, protects process IDs, communication ports
	- Source and destination of messages on network cannot be trusted without cryptography.
		- Local network - IP address?
			- Consider unauthorised host added
		- WAN / Internet - how to establish authenticity
			- Not via IP

- Constrains the set of possible receivers of a message. 
- Encryption algorithm consists of
	- Set K of keys
	- Set M of messages
	- Set C of ciphertexts (encrypted messages)
	- A function E : K -> (M -> C) that is, for each k ∈ K, Ek is a function for generating ciphertexts from messages
		- Both E and Ek for any k should be efficiently computable functions. 
	- A function D : K (C -> M) That is, for each k ∈ K, Dk is a function for generating messages from ciphertexts. 
		- Both D and Dk for any k should be efficiently computable functions. 

- An encryption algorithm must provide this essential property
- Given a ciphertext  c ∈ C, a computer can compute m such that Ek(m) = c only if it possess k
	- Thus, a computer holding k can decrypt ciphertexts to the plaintexts used to produce them, but a computer not holding k cannot decrypt ciphertexts.
	- Since ciphertexts are generally exposed, (sent on the network), it is important that it be infeasible to derive k from the ciphertexts

![[image-20.png|371x204]]

- **Symmetric Key** - Bob and Alice share the same key, or one can be derived from the other. 
- Historically, distributing the keys has always been the weakest link in most cryptosystems
- No matter how strong a cryptosystem as, if an intruder could steal the key, the system was worthless. 
- Cryptologists always took for granted that the encryption key and decryption key weer the same

##### Public Key Cryptology

![[image-21.png|341x180]]


##### Simple Encryption Schemees

- Substitution cipher - substitute one letter for another. Very weak, can be broken with statistical analysis. 
- Transposition cipher - keep same characters but change the order. 


##### Complex Schemes

- Product ciphers - combine permutations, substitutions into several steps. 

![[image-22.png|350x103]]

- DES: Data Encryption Standard
	- Break text into 64 bit blocks
	- Process in 19 iterations transpositions and combinations. 

- AES: Advanced Encryption Standard
	- Based on Galois Theory
	- Substitutions, permutations, multiple rounds
	- 128 bit encryption keys 

- Monoaphabetic substitution cipher
	- Despite their huge complexity, DES and AES are basically a monoalphabetic substitution ciphers using big characters. 
	- To make things more difficult, change the way in which data is encrypted by chaining the messages. 

![[image-23.png|425x148]]


##### Cryptography Principles

- Sharing keys is the most difficult and vulnerable part of any encryption process. 
	- One time pads are unbreakable
- Messages must contain some redundancy
	- Random sequences should not correspond to a valid message. 
- Some method is needed to foil replay attacks. 
	- Each message should be fresh to prevent the replay of old messages. 

##### Cryptanalyst's Perspective

• Ciphertext-only problem: no access to plaintext.
• Known plaintext problem: some matched plaintext available.
• Chosen plaintext problem: the Cryptanalyst has the ability to encrypt pieces of plaintext.
• Codes should be unbreakable against encryption of any amount of plaintext.
• Kerckhoff’s principle: Algorithms are public, only keys are secret. Security by obscurity never works

## Further Topics

#### Multiple cores and processors

- The module has dealt with the issues of single CPU systems
- Most modern systems use multiple cores, each core appearing as a separate processor to the OS. 
- The advantages are the speed-up that this provides in computation. 
- But they require more complex process scheduling algorithms, that brings issues about load balancing and data dependencies. 


##### Threads and synchronisation

- Related to the issues of parallelism and multiple cores, is the issue of multithreading. 
- Execution of multiple threads to improve resource sharing and responsiveness.
- However, they also being issues that programmers need to deal with, related to thread synchronisation and scheduling.


##### File systems and storage. 

- Tere are more issues to consider with file systems and storage for delivering relability garuentees to users. We looked at RAID.
- File systems used for cloud storage and large data-stores may have different requirements compared with traditional file systems. 

##### Security

- We started discussing some of the security issues and only breifly difcussed possible countermeasures. 
- There are a lot more threats and possible countermeasures


