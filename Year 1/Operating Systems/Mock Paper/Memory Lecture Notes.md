Memory abstraction in simplifying the memory for the memory management unit 

Every square of memory is a bit, and holds flip flops. How do we organise and allocate these squares.

Organise is cells/words/bytes, which could be a certain amount of bits in a row. It depends on how many bits the words hold. 

![[Year 1/Images/image.png|412x220]]

As chips has progressed they have had more bits per word. 

## Address Space

Virtual memory vs Physical Memory. 

Virtual memory does not have a physical location. Swapping them is known as memory mapping. 

Memory Management Unit - A hardware device that at run time, maps virtual to physical addresses there are many methods possible. The user programs deals with logical addresses and never sees the real physical addresses. Logical addresses are bound to physical addresses. 

Logical addresses are what the program sees, and are mapped to physical addresses. This is because if programs were competing for physical addresses, each program would have to know what is free and allocate themselves. Mapping addresses ensures isolation of programs. 

Simple dynamic relocation does not work in reality, as there is no limit to how high the physical addresses can go. It is not memory safe. We have to protect so that it does not go above or below. 

We can add a limit register, which is the maximum for each process. 

The physical address will be checked that it is higher than a base, held in a register. It will then check it is lower than another register holding the base + limit. If either of these are out of range, throw an addressing error. 

What do we do with larger processes that may not fit?

## Larger Processes, Virtual Memory

- If the physical memory is large enough it is ok, if not, then virtual memory may be needed. 
- Swapping - may not be enough physical memory, processes can be swapped out of memory to a backing store, and then brought back into memory for continued execution. 
- The largest part of a swap is disk read and write time. 
- Versions of swapping are on all major OS
- Idle processes are mostly stored on the disk. 

To work out the total swapping time, calculate the rate of transfer, times by 2 for in and out. Times latency by 2 for in and out, then add. 

Sometimes processes run as fast as possible, but not always.

Slowdown factor - Calculates the ratio of the slow case over the fast case.

Slowdown = t slow = with swap / t fast = without swap. 

![[Year 1/Operating Systems/Mock Paper/image-1.png|456x287]]

- Does swapped out memory need to swap back into same place, depends on swapping method. 

Swapping on Mobile Systems typically does not happen. Will ask you to free up processes. 

Contiguous Allocation. 

Memory is limited and we must allocate efficently. 

If the process is fixed, then easy. However some will need to be allocated for growth.
If the process can grow, if there is a hole adjacent, allocate and grow in the hole. 
If there is no memory to grow ,suspend and wait, or kill it. 
Or allocate some space so that the process can grow. 

How to allocate a process. 

First-fit - Allocate the first hole that is big enough. Fast way of solving it, but not very efficient, can leave big holes. 

Best-fit - Allocate the smallest hole that is big enough. Must search entire list, unless ordered by size, and use the smallest hole that is adequate. This stops breaking up a big hole that may be needed later. It also produces very small holes that are completely useless. 

Worst-git - Allocate the largest hole, also search entire. First-fit and best-fit are better in terms of speed and allocation. 

External Fragmentation - When enough space exists to satisfy a request but the available spaces are not contiguous; storage is fragmented into numerous holes. 

Internal Fragmentation - We can give processes fixed allocations with some unused space. For example, just allocate the enitre hole rather than leaving a useless hole of 2 bytes. Holding the record of the hole is larger than the hole itself. 

Simply:

External Fragmentation - Total memory space exists, but is not contiguous. 
Internal Fragmentation - Allocated memory may be slightly larger than requested memory, this size difference is memory internal to a partition. 

First fit analysis shows that we lose a third of memory. 0.5 N blocks lost to fragmentation. 

We can do optimisations such as

Compaction - Shuffle memory contents to place all free memory together in one block. Only possible if relocation is dynamic, and done at execution time. 

However, these take time, and are a trade off in itself. 

## Paging:

Modern OS - Swapping does not happen that often, not that effective. 

Paging - Instead of allocating large chunks of memory, we divide into smaller chunks of memory. Each page of virtual memory is mapped to a same sized frame of contiguous physical memory. Standard Linux page size is 4 kB

Divide physical memory into fixed-sized blocks called frames.
Size is power of 2, between 512 bytes and 16 mega bytes. 

How many frames can be pointed to with a page of 4 bytes? How much physical memory would that compromise if each frame would be 4 kB. 

To run a program of size n pages, need to find n free frames. 

- Keep track of all free frames. 
- Set up a page table to translate logical to physical addresses. 
- External fragmentation - no. Internal fragmentation - yes. 
- Small page sizes seem desirable. However, overhead is involved in each page-table entry. And this overhead is reduce as the size of the pages increase. 


**Example Question**

Page size - 2,048
Process size - 72,766

How many pages are required?
What is the internal fragmentation?
What is the best/worst case?


##### Address Translation Scheme

- Address generated by CPU is divided into:
	- Page number - used as an index into a page table, which contains base address of each page in physical memory. 
	- Page offset - Combined with base address to define the physical memory address that is sent to the memory. 

Page number - tells you which page you need. (imagine a book)
Page offset - tells you how far down you need to go (reading down a page in a book)

![[image-32.png|581x327]]

One page table for each process that is running on the CPU. 

Pages do not have to be stored contiguously in physical memory, all that matters is that we are able to translate from the location in logical memory to the location in physical memory. The OS has to track which frames are in use and which ones are not, so that free frames can be allocated. 

The virtual memory address space for a process can be bigger than the total amount of physical memory. This is possible because the memory is dynamic, not all of it is stored on RAM, some is stored on disk. 

Scenario 1: Process never actually uses all of the virtual memory it owns. 
Scenario 2: Process uses different parts of its virtual memory address space at different times. The OS can "page out" (copy to disk) frames not currently in use and remap new pages to those frames. 

**Demand Paging**

- Bring a page into memory only when it is needed. 
	- Page is needed -> process tries to access an address in that page. 
	- Illegal reference (virtual address not allocated to process) -> abort
	- not-in-memory (page fault) -> bring to memory

- A pager is a lazy swapper, never swaps a page into memory unless the page is used. 


Some pages do not correspond to a physical memory address. These are called virtual pages. Tag each page table entry with a present (1) absent (0) or invalid (-1) bit.

Initially, is set to 0 on all entries. 
If an absent page is requested, it creates a page fault. 


Structure of a page table entry. 

- Present/absent (valid/invalid) if 1 can be accessed, if - is not avaliable. 
- Protection: Kind of access permitted (read, write, read/write)
- Modified, Referenced, keep track of the page usage, when modified is called "dirty"
- Caching, sometimes it is important to recall from devices I/O and not just a cached value. 


Page fault - Occurs if the requested entry in the page tabled is marked 0, or invalid. 

OS will check page number

- If illegal (outside process address space) abort
- Otherwise (legal but not currently in memory)
	- Get empty frame
	- Swap page into frame
	- Change validation bit from i to v
	- Restart the instruction that caused the page fault. 

Performance of Demand Paging

- Page-Fault rate 0 < p 1.0
	- If p = 0 there are no page faults. 
	- If p = 1, every memory reference causes a page fault. 
- Effective Access Time (EAT)
	- The average time taken to service a memory reference. 
	- If there were never any page faults, this would just be the base hardware memory access time. 
- When a page fault happens, the following extra time is spent. 
	- Time taken to execute page-fault trap + time taken to swap pages in and out of the disk + time taken to return from the trap and restart the process which made the memory reference.
- This combined extra time is called the page-fault service time.

Example Question:

Base memory access time = 100ns
Average page-fault service time = 1ms

Suppose one memory reference in every 1000 causes a page-fault. 

Estimate EAT
What is the slowdown factor?


EAT = a + Ps

Where:
**a** = Hardware memory **a**ccess time
**p** = **P**age fault rate
**S** = Page fault **s**ervice time

If we have more RAM, p decreases (less swaps)
Adding processes increases p (more loaded)
Increasing disk speed decreases S


Page tables are too large to be implemented in registers so we have to store them in main memory. 
This adds an extra memory lookup to each memory access.
To reduce this overhead, MMU uses a page table cache called the Translation Look-Aside Buffer (TLB)

Memory structures for paging can get huge using straight-forward methods. 
- Consider a 32 bit logical address space on modern computers
- Page size of 4kB
- Page table would have 1 million entries.
- If each entry is 4 bytes, 4 MB of physical address space for page table alone. 
- That amount of memory used to cost a lot. Don't want to allocated that contiguously in main memory. 

There are 
- Hierarchical paging
- Hashed page tables
- Inverted page tables. 

- Break up the logical address space into multiple page tables.
- A simple technique is a two-level page table. 
- Like having chapters and pages. 

## Page replacement

- Suppose we need to bring a page into memory but there is no free frame. 
- **Page Replacement** - Find some page which is in memory, but not currently being used, and swap it out. 
- Page replacement algorithms decide which memory pages to swap out when a page of memory needs to be allocated. 
- We can speed up the process by using the dirty bit. (tells you if it has been modified)
- If it has been modified, it has to go back to the disk. If it has not been modified it is exactly the same, so can be discarded. Saves you one transfer. 


**Basic Page Replacement**

- Find the location of the desired page on disk. 
- Find a free frame:
	- If there is a free frame, use it. 
	- If there is no free frame, use a page replacement algorithm to select a victim frame. 
	- Write the victim frame to disk if dirty, (has been modified)
- Bring the desired page into the newly freed frame; update the page and frame tables.
- Continue the process by restarting the instruction that caused the trap. 
- Note, this is now 2 page transfers for page fault, increasing EAT. 

Frame-allocation algorithm determines:
- How many frames to give each process. 
- Which frames to replace

Page-replacement algorithm
- Want lowest page-fault rate on both first access and re-access

Algorithms can be evaluated by running it on a particular string of memory references, and computing the number of page faults on that string. String is just page numbers that are being requested. Repeated access to the same page does not cause a page fault. Results also depend on the number of available frames. 


#### Page replacement Algorithms

**First in First Out**

- The page which was first brought into memory, is the first page to be removed. 

![[image-33.png|158x163]]

- In this scenario, when all frames became full. 7 was taken off first, as it was the first in, had been there the longest. 
- If there is a page in the string that is already in memory, skip it. 
- This algorithm has no prediction. You may be removing a page that is next to be requested, in which case removing something else would have been a better choice. 

Belady's Anomaly - In not all cases it is better to have more frames. Sometimes having 4 can be worse than 3. But then 5 6 and 7 are better and mostly flat. 

![[image-34.png|353x240]]

**Second Chance Algorithm**

- FIFO does not discriminate if a page is useful or not, and the oldest may still be useful. 
- Use status bits R (read/write), M (modified)
- R = 0 unused, R = 1, recently used. 
- All frames are given a second chance before they are removed. 
- Among unused frames, FIFO applies. 
- Not very efficient, as there is constant moving of pages to give every page a second chance. 

**Clock Page Replacement Algorithm**

- Arrange the pages in a clock format.
- When a page fault occurs, the page the hand is pointing to is inspected.
- The action taken depends upon the R bit. 
	- 0, evict the page. 
	- 1, clear R and advance hand. 

**Optimal Algorithm**

- Replace page that will not be used for longest period of time
- How do you know this? Can't read future.
- This is used for measuring how well a given algorithm performed. 
- It is theoretical 

**Least Recently Used Algorithm**

- Use past knowledge rather than future
- Replace page that has not been used in the most amount of time. 
- Associate time of last use with each page. 
- Better than FIFO, worse than optimal (but that is impossible)
- Generally good, frequently used. 
- Difficult to implement, have to keep a record of which pages have been used. 
- Needs special hardware


Each process needs minimum number of pages, two major allocation schemes. 

Thrashing - If a process does not have enough pages, the page-fault rate is very high. Trashing means a process is busy swapping pages in and out. 


Page fault frequency - We establish an acceptable page fault frequency for each process to decide what gets frames. If the rate is too high, the process is given more frames. If it is too low, they get less. 