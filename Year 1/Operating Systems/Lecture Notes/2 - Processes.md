Today's questions

- What happens when a program's execution is interrupted
- How does the OS interleace the execution of multiple programs
- How does the OS ensure new processes are not waiting while the CPU is idle? 
- How can limited RAM be shared among interleaved processes. 
- What does a process look like to an OS
- What does an OS do when creating a process. 
- Is the OS a process?

## "Interrupting" processes

Interrupt
- Cause: External to the execution of the current instruction. 
- Use: Reaction to an asynchronous external event. 

Trap
- Cause: Associated with the execution of the current instruction
- Use: Handling of an error or an exception condition

Supervisor call
- Cause: Explicit request
- Call to an operating system function


# Definition of a Process

A process is:

- A program in execution
- An instance of a program running on a computer
- The entity that can be assigned to, and executed on a processor
- An executing set of related machine instructions. 
- A unit of activity characterised by a single sequential thread of execution, a current state and an associated set of system resources. 

It can be useful to think of programs as being passive, and processes being active.


# "Passive" vs "Active"

- Sheet music would be passive, while the music produced by an orchestra playing the sheet music is active. 
- A cooking recipe is passive, while cooking with the recipe is active. 
- In essence, the work done by following "passive" instructions is regarded as active.


## Management of Program Execution: Processes

- Processes were first used by designers of Multics OS in the 60s
- They are the **most important abstraction** provided by all modern OSes
- The OS uses processes to ensure
	- Resource are made available to multiple applications
	- The CPU is switched among multiple applications. 
	- The CPU and I/O devices can be used efficiently, securely, and reliably. 


## Process Uses Program Elements

Two essential program elements used by a process are
- Program Code: Which may be shared with other processes that are executing the same program
- A set of data associated with that code. 

## Interleaving Processes

Trace
- The behaviour of an individual process can be viewed as a sequence of instruction that execute for that process. 
- The CPU can, itself, be viewed as interleaved traces of the various processes.

Dispatcher
- A small program that switches the CPU from one process to another 
- More on the dispatcher in [[3 - CPU scheduling]]

![[Pasted image 20250221151107.png]]


## Two-State process model

- Simplest model:
	- Process is created
	- Process is always either running or not running
	- Process terminates. 

Created processes are put into the "not running" state by a long-term scheduler
A short-term scheduler choose a not running process for the dispatcher to assign to run on the CPU
A process can be interpreted for many reasons, such as a timer interrupt or an I/O interrupt.

**Reasons for new process creation:**
- New batch job
- User logon
- OS services
- Spawned by existing process

**Reasons for process termination**
- Normal completion
- Time limit
- Insufficient computer resource available
- Significant errors
	- I/O
	- Division by 0
	- Arithmetic
- Parent process request or termination 
- User termination
- Privileged instruction

## Response Time

- The time taken for a process from entering the queue, to being executed. 
- However, a new process joining the queue may be ready to run, but blocked by others that are waiting for I/O results. 

## Five-State Process Model

- OS may limit the number of admitted processes
- Now, new processes are placed in a **ready** state, separate from blocked processes that are waiting the results of I/O requests

![[Pasted image 20250221154024.png]]

![[Pasted image 20250221154324.png]]


**How is the limited amount of main memory shared among many interleaved processes?**

- CPUs are very fast, so queues can grow very quickly
- With limited main memory, this can be a challenge. 
- Why isn't having more main memory a good solution for this?
	- Main memory comes with extra cost. 
	- In any case, new programs tend to require more and more main memory, so eventually the same problem will arise.
- The OS may limit the number of admitted processes, which may mean smaller queues, but the CPU will still spend a lot of time being idle, when all processes are waiting for I/O

## Six-State Process Model

- Move suspended process to ready queue when I/O request has been completed. 
- Move part or all of some blocked processes to the hard disk. 

![[Pasted image 20250221165608.png]]

Weaknesses

- What happens if the ready queue becomes full? (if the OS reaches its limits on the number of ready processes under high load)

Reasons for entering suspend state
- Swapping - The OS needs to release sufficent main memory to being in a process that is ready to execute. 
- Other OS reasons - The OS may suspend a background or utility process or a process that is suspectedly causing a problem. 
- Interactive user request - A user may wish to suspend execution of a program for purposes such as debugging or in connection with the use of a resource. 
- Timing - A process may be executed periodicall (system monitoring process) and may be suspended while waiting for the next time interval. 
- Parent process request - A parent process may wish to suspend execution of a descendant to examine or modify the suspended process, or to coordinate the activity of various descendants. 


Qualities of a process in the suspended state

- A suspended process
	- Is not immediately available for execution
	- Is placed in a suspended state by a suspendinf agent
	- May not be waiting for an event
	- May not be removed from this state except by the suspending agent. 

## Seven-State process model

![[Pasted image 20250221173129.png]]

What does a process look like to the OS?

- A process is allocated a portion of main memory called the process image, this includes.
- Sufficent memory to hold the code and program data for the process
- A call stack, used to keep track of a process's procedure calls, and a parmeter passing between procedures.
- Memory for a special data structure called the process control block (PCB) that contains the process's attributes. These attributes are used by the OS for process control. 
- The precise location of the process image (in main memory ) will depend on the memory management scheme used by the OS. 
- The precise location of a process image will depend on the memory management scheme used by the OS. 

![[Pasted image 20250221175153.png]]

## The role of the process control block

- The most important data structure in an OS
	- Contains all of a processes information needed by the OS
	- PCBs are read and modified by virtually every module in the OS
	- The collection of all PCBs defines the OS state
	- Access to PBCs is easy: use process ID
	- Protecting PCBs from being damaged is more challenging. 
	- A bug in a single OS routine could damage a PCB 
	- A design change in the structure or semantics of the PCB could affect a number of modules within the OS. 
- The OS maintains information about a processes attributes in PCB
- It resides in protected parts of memory. 
- Consists of 3 sections. 
	- Process identification
	- Processor state information
	- Process control information

PCB Section: Process Indentification