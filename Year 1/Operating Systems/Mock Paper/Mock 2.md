![[image-29.png|504x376]]

a)

Interrupts can occur in the following scenarios. 

- IO Interrupt

b)


c)

i) Base 8 as it can represent all values inclusive of 0-7
ii) 8<sup>3</sup> = 512

![[image-30.png|526x660]]

i) Three processes, fork is called twice from the main process, meaning there are three.
ii) fork is called twice by the same process, so there is only one parent process.
iii) There are two children, each one created by a fork() call. 
iv) The parent process and first child process all increment their copy of c, once. The second child increments it twice. 
v) The second child has value 2. 
vi) The parent process has value 1. 
vii) fork() is an API method that only the OS kernel can execute. Each time G calls fork() it causes an interrupt. 

b) Memory hierarchy are the different levels of memory pieces of data can be stored on a system. The top of the hierarchy is the fastest and usually has smallest capacity (L1 cache). The bottom of the hierarchy is the largest and usually slowest (HDD). Each type of memory has a trade off, so combining them attempts to create a well rounded system with speed, and capacity. For example, faster modules such as cache and registers are very fast, but significantly more expensive than slower modules such as RAM and hard disk, which are cheap. 

c) The principle of spatial locality is a phenomenon that when an instruction from memory is fetched, nearby instructions are also likely to be executed soon. 

d) The CPU spends a lot of time idle, waiting for instructions to be fetched from RAM. If the CPU were to get these items from cache, this time would be far lower. However, due to the cost of cache memory, it is impossible to have it large enough to store everything. As a compromise, we can benefit from spatial locality. When an instruction is executed, nearby instructions are buffered into cache memory just in case, as these instructions are naturally likely to be needed soon. This can help increase the CPUs hit rate, and thus speed, as more instructions it needs can be fetched from higher up in the memory hierarchy. 

![[image-31.png|506x480]]

a) 8.2 MB / 108.4 MB/s = 
