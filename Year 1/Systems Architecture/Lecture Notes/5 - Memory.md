# Types of memory 

- When designing a memory system for computers, you want a system that is fast, large and cheap
- The problem with this is that typically, large memory is slow and fast memory is small and expensive. 
- For this reason, we must organise memory in a way that optimises the "average case"
- This is called **memory hierarchy**

The main types of memory are
- Cache memory
- Main memory
- Secondary memory
- Virtual memory

![[Pasted image 20250117150046.png]]

**Main memory**

- There are two kinds of main memory:
	- Random Access Memory (RAM)
		- Dynamic RAM (DRAM)
		- Static RAM (SRAM)
	- Read Only Memory (ROM)

**Dynamic RAM**

- A bit is stored in a capacitor
- If it is charged, it is one. If it is not charge it is 0.
- DRAM consists of capacitors that slowly leak their charge over time
- This means they must be refreshed every few milliseconds to prevent data loss
- DRAM is used as main memory
- Advantages:
	- Low power consumption
	- Small area
	- Low costs
	- Each bit only needs one capacitor 

**Static RAM**

- A bit is stored by 6 transistors working as a D flip-flop
- It is very fast and used to build cache memory
- Advantages
	- Fast access
	- Does not need to be refreshed
- Disadvantages
	- High power consumption
	- Large area
	- Each bit needs 6 transistors

**Read only memory**

- Data stored in chips which are non volatile (hold their data after power loss)
- ROM is used to store permanent data while the system is turned off
- E.g boot instructions
- Data stored in these chips are either unchangeable or require special operations to change
- ROM is programmed as part of a manufacturing process
- They are often used in embedded systems

**Types of ROM**

- Programmable ROM (PROM)
	- Lines connected by diode and fuses, blowing the fuses makes them 0 instead of ROM. 
	- Can be written once, and read many times. But cannot be re-written.
- Erasable PROM (EPROM)
	- Can use ultraviolet light to erase the data and re-write
	- Ultra violet light has a limited number of uses
- Electronically Erasable Programmable ROM (EEPROM)
	- Can electronically erase data using the local electric field
	- Does not need to be removed to be re written. Can change specific portions and bytes without wiping the whole thing. 
- FLASH
	- Modern version of EEPROM
	- Two types, based on NAND gates or NOR gates. 

**Virtual Memory**

- Virtual memory is a section of volatile memory temporarily created on the storage drive.
- It is created when the computer is running many processes and RAM is running low. 
- The operating system makes part of the storage drive available to use as RAM. 
- Virtual memory is much slower than main memory, as processing power is being taken up by moving data around, rather than just executing instructions. 

# The Memory Hierarchy

- Memory Hierarchy - A way of organising memory in a computer such that it meets speed, capacity and cost requirements. 
- Memory hierarchy is needed as we cannot afford, both in money and power, to use as much of the highest performance memory as we would like. 
- We construct a memory hierarchy by using a variety of devices, such as registers, SRAM, DRAM and disks. 

**The memory hierarchy as a pyramid**

![[Pasted image 20250117154652.png]]



