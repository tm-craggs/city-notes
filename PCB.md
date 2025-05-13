The OS maintains information about a processes attributes in PCB
It resides in protected parts of memory

**3 sections**
- Process identification
- Processor state information
- Process control information


- Process ID is a unique number identifying the process
- Part of a mapping the OS uses to locate process information in control tables


Contains process control information

- Process state
- Priority
- Scheduling related information
- ID of event they may be waiting for. 
- Links/pointers to other
- Process privileges

Processor Table
- Used to keep track of processes

![[image-35.png]]

Interrupts - reaction to an external event. For example, I/O interrupts. Traps. 

User mode
- CPU executes in user mode for user programs
- Certain areas of memory are off limits
- Certain instructions cannot be run

Kernel mode
- CPU executes in kernel mode for OS
- Protected areas of memory may be accessed.
- Priviliedged instructions may be run
- Switches to kernel mode when an interrupt occurs, so it can be handled