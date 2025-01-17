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



**Cache Memory**

- Cache memory is a small piece of SRAM located near the CPU. 
- Cache memory holds commonly used instructions, so they can be accessed quicker. 
- Deciding how much cache to use is a trade off. Larger cache increases the hit rate, meaning more different instructions can be held and executed from cache, meaning main memory must be accessed less. 
- However, increasing the size of cache to increase the hit rate makes the cache slower.
- Therefore, cache is split into levels. L1 cache is is smallest and quickest, some processors go down to L3, which would be the largest and slowest. 
- The CPU will check registers first, then L1 cache, L2 cache, and then L3 if applicable before then sending the request to main memory. 

**Communication between levels**

- There are clear protocols on how different levels interact 
- Within each level, the units of information transfer is called a block. 

**Steps to locate and fetch data**

- To access a particular piece of data, the CPU sends a request to its nearest memory level. 
- If the data is not in main memory, this is a miss. 
- The request then goes to secondary memory (the disk)
- Once the data is located, it is moved into main memory. 

**Hit and miss**

- Hit - Data is locally available and has no penalty to access
- Miss - Data is on a lower level - penalty from 1-30 clock cycles to access
- Hit rate - The percentage of time data is found at a given memory level
- Miss rate - The percentage of time it is not. 
- Miss rate - 1 - hit rate
- Hit time - The time required to access data at a given memory level. 
- Miss penalty - The time required to process a miss, including the time it takes to move a block of memory plus the time is takes to deliver the data to the processor. 

**What information goes in cache?**

- Things that you expect to use often, or soon. 
- You predict which ones by looking at access patterns
- The principles of locality of reference observation are used. 

**Memory Access Times**

- Read from register - 1 clock cycle, 2 ns
- Read from L1 - 1 to 2 cycles (2-4 ns)
- Read from L2 - 4 to 5 cycles (8-10 ns)
- Read from main memory - 8 to 30 cycles (16-60 ns)

**How does the CPU access cache data?**

- First the CPU requests data
	- The CPU generates a main memory address
	- If the data is in cache, then we need a way to convert the main memory address into a cache location
- This is called cache mapping

**Cache mapping methods**

- There are three basic methods used for mapping information fetched from the main memory to the cache memory
- Direct mapping
- Associative mapping
- Set-associative mapping 
- This module will focus on direct mapping

**Direct Mapped Cache**

![[Pasted image 20250117164040.png]]

- In this example:
	- Block = 1 word
	- 8 block locations in main memory
	- Memory block address = 3 bits
	- Cache with 4 blocks
	- Cache block access = 2 bits
	- Lower 2 bits of memory block address is modulo 4 for the cache address

![[Pasted image 20250117164915.png]]

**Partitioning of memory blocks**

- Usually block size - multiple words
- To perform direct mapping, the binary main memory address in partitioned into feilds
- Block field - Selects a unique group of blocks of cache
- Tag field - Selects the exact block in the group
- Offset field - Uniquely identifies an address within a specific block. 
- The sizes of these fields are determined by characteristics of both memory and cache. 

**Cache and Bits**

- Consider a byte-addressable main memory consisting of 4 blocks, a cache with 2 blocks, and each block is 4 bytes.
- This means block 0 and 2 of main memory map to block 0 of cache. 
- Block 1 and 3 map to block 1 of cache. 
- Using the tag block and offset fields we can see how main memory maps to cache. 

**Working out tag, block and offset**

- First, we must determine the address format for mapping. 
- Each block is 4 bytes and is byte-addressable, so offset field must contain 2 bits. 
- There are 2 blocks in cache, so the block field must contain 1 bit. (0 for first, 1 for second)
- The memory address requires 4 bits as there are a total of 16 words. (4 blocks x 4 words each and 16 = 2^4)
- Tag is 1 bit (physical address bits - (block + offset))

**Example**

![[Pasted image 20250117170723.png]]

- Suppose we need to access main memory address 0x0011 using the address format from figure a
- We partition 0x0011 and get figure b 
- This, the main memory address 0x0011 maps to cache block 0
- Figure c shows this mapping, along with the tag that is also stored with the data. 

**Direct mapped cache**

- Memory addresses are mapped to unique cache positions
- Cache location - Block Address modulo of number of cache blocks
- We can have a situation where two blocks map to the same cache location, this is why there are tag bits. 
- Valid bit - indicates whether cache value = memory value

**A more realistic cache**

- Cache organisation
	- Data width - 32 bits
	- Address width - 32 bits
	- Cache size - 1024 blocks
	- Cache index - 10 bits (1024 = 2^10)
	- Block size - 1 word (4 bytes)
	- Byte offset - 2 bits
	- Tag size - 32 - 10, 20 bits
	- Valid bit
- Data Access
	- Find cache index with address bits 11..2
	- Compare cache tag with address bits 31.12
	- Check valid bit to ensure data is loaded
	- Signal a hit to the CPU
	- Transfer data

# Cache efficiency

- Cache memory size - 1024 x 32 bits = 32k bits
- Tag memory size = 1024 x 20 = 20K
- Valid bit 1024 x 01 bit = 1K bits
- Efficiency: 32 / 53 = 60.4%

**Handling Data Cache Misses**

- If the wanted data is not in the cache:
- Perform a cache miss process
	- Stall the processor
	- Freeze contents of registers
	- Activate memory controller
	- Separate controller handles memory fetch
	- Request data item from next lower level of hierarchy
	- Load data item into cache
	- Write data, store upper bits as tag, set valid bit. 
	- Resume processor

Effective Access Time (EAT)

- The performance of a memory hierarchy is measured by its effective access time
- EAT is a weighted average that takes into account the hit ratio and relative access times of successive levels of memory
- The EAT for a two-level memory is given by:
	- EAT = H x Access c+ (1-H) x Access mm
	- Where H is the cache hit rate and access c and access mm are the access times for cache and main memory respectively

**Split vs Combined Caches**

- Split caches for data and instructions (Harvard architecture)
- Higher miss rate due to smaller size
- Higher bandwidth due to separate data paths
- Data and instructions can be cached simultaneously

- Combined caches
- Lower miss rate due to larger size
- Lower bandwidth due to sharing of datapaths
- Data and instructions cannot be cached simultaneously

**Cache Write Policies**

