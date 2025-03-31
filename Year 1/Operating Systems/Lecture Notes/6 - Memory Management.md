
## Background and Introduction

- Memory wish list:
	- Private
	- Infinitely large
	- Infinitely fast
	- Non-volatile (holds data when turned off)
	- Inexpensive
- This is obviously not possible, but gives an idea about what we try to achieve with Computer Memory
- This is why memory hierarchy exists, as different types of memory are good at achieving different things. For example:
	- **Cache Memory** - Fast, but small and expensive
	- **Solid State** - Slow, but large, cheap and non-volatile
	- **Main Memory** - Middle ground, decent speed and price, but is volatile 

**Memory Hierarchy**
- Program must be brought from disk into memory and placed within a process for it to run. 
- Main memory and registers are only storage CPU can access directly. 
- Register access in one or less CPU clock
- Main memory can takes many cycles to access, causing a CPU stall
- Cache sits between main memory and CPU registers. 

**Principle of locality**
- The principle of locality states that programs access a relatively small portion of their address space at any instant of time
- There are 2 types of locality
	- **Temporal Locality** (locality in time) - If an item is referenced, it will tend to be referenced again soon. 
	- **Spatial locality** (locality in space) - If an item is referenced, items whose addresses are close by will tend to be referenced soon. Imagine books on the same shelf. 

**Taking advantage of locality** 
- Store everything somewhere where it is cheap, although slow to access. 
- Copy recently accessed and nearby items from disk to smaller DRAM memory (main memory)
- Copy more recently accessed (and nearby) items from DRAM to smaller SRAM memory (Cache memory)

**Memory Manager**

- The memory manager must manage all the memory resources, which parts are in use, and allocate and free memory as necessary. 
- To improve CPU performance and speed, we must keep several processes in memory. 
## Memory Abstraction

- To better understand a complex process, we can simplify and remove as many unnecessary details and keep only the most important attributes. 
- For example: "bits" in memory are actually flip-flop logic gate circuits, but this detail is not crucial, we can simply represent them as 1s or 0s. 
- 

## Address Space

## Memory Management Unit

## Larger Processes: Virtual Memory, Swapping

## Paging

## Page Replacement
