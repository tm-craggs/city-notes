## Data vs Information

Data is the physical bits that are stored on your system, information is what is useful in the file. For example, when files are compressed the data changes but the data stays the same (if it is lossless)

**Information** - the amount of difference from the expected message

It is impossible to compress random data, because the predictability of it is so low

Error Control Codes is the opposite of compression, same information with more data.
We can add a code to the end of a message that can be checked to correct errors. 
## Physical Layer

The point of the physical layer is to get bits from one Computer to another

**Ethernet**
- One of the oldest physical layer technologies
- Used to be ring topology, now is star or tree

**Hubs vs Switches**

- Hubs are essentially just connections on the physical layer
- The most basic way to connect different devices via Ethernet

- Switches look identical but are a newer technology 
- The switch looks at the link layer information, and send them on to the relevant machine.
- Makes routing more efficient and increases capacity, stops everybody talking at once

## Link Layer

Link layer is split into two parts, LLC and MAC

MAC (Media Access Control)
- This is the lower part of the link layer
- It is a protocol that stops everything talking at once
- It regulates how devices share a physical communication channel
- It assigns hardware level addresses to NICs (Network Interface Cards) to ensure packets reach the correct destinations

LLC (Logical Link Control)
- Once you are at a stage where everything is not talking at once, this defines what you are talking about
- Basically tells you what is going on in the link 
- It controls access to the data link level
- Standardised as 

## Security Analysis

Wireshark

An open source tool that is used to monitor network traffic.

On the Wireshark menu, there are a few options
- Ethernet - Monitor ethernet traffic
- Wireless - Monitor wireless traffic
- Any - Monitor all traffic
- Loopback - Use network technologies locally

Filters go at the top bar, in order to make sense of anything you'll need to use them
You will need to filter out RDP traffic. 

Packets will appear on screen, selecting them will make them appear in 2 different forms. Hex digits and ASCII characters

It can highlight which literal bits are part of each Ethernet frame.
- We can see destination, (MAC address), a switch would use the to route
- The source
- Additional field, either type or size. It tells the operating system how to process the bits. 

## MAC: Carrier Sense Multiple Access

- Purpose of the MAC layer is to stop everybody talking at once
- There are a few schemes that depend on the type of physical layer used

CSMA: Carrier Sense Multiple Access
- You listen, is there anybody else transmitting. If so, wait
- Widely applicable for both Ethernet and Wi-Fi

CSMA/CD: CSMA with Collision Detection
- Sender "hears" collisions as they happen so knows when to re-try. 
- Ethernet of half-duplex link can use this
- It cannot be used on Wi-Fi

CSMA/CA: CSMA with Collision Avoidance
- If a link is sensed, wait before trying to send
- Wait time is randomised to avoid "lock step", which are repeated conflicts
- This is used on Wi-Fi
## Conclusion

