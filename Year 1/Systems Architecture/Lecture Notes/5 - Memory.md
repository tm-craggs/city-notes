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
- 