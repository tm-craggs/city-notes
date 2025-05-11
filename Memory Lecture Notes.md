Memory abstraction in simplifying the memory for the memory management unit 

Every square of memory is a bit, and holds flip flops. How do we organise and allocate these squares.

Organise is cells/words/bytes, which could be a certain amount of bits in a row. It depends on how many bits the words hold. 

![[image.png|412x220]]

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

![[image-1.png|456x287]]

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



