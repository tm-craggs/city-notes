
## Unix system calls:

**fork()**
- When called, creates a copy of the process that makes a call
- The process ID of the "child" process is different from that of the parent
- By default, the two processes have different process images
- Both processes continue to execute from the point in the code after the call was made
- fork() returns the ID of the child process to the parent process, and returns 0 to the child process. 

**execv()**
- When called, replaces the calling process with a new process, executing a possibly new program. 
- The process ID remains unchanged. 

**wait()**
- Default behaviour, when called, is to suspend the calling process, until all child processes terminate, before continuing execution. 

## CPU Scheduling

- Aim is to assign processes to be executed by the CPU in a way that meets system objectives. 
- 3 separate scheduling decisions
	- Long term scheduling (relatively infrequent compared to medium)
	- Medium term scheduling
	- Short term scheduling (relatively frequent, compared to medium)

Long-term scheduling - The decision to add to the pool of processes to be executed
Medium-term scheduling - The decision to add to the number of processes that are partially or fully in main memory
Short-term scheduling - The decision as to which available process will be executed by the processor. 
I/O scheduling - The decision as to which processes pending I/O request shall be handled by an available I/O device. 


![[Pasted image 20250221213229.png]]
![[Pasted image 20250221213432.png]]

## CPU Scheduling Queues

![[Pasted image 20250221213656.png]]
## Long-term Scheduler

- Determines which programs are admitted to the system for processing
- Controls the degree of "multi-programming"
	- The more processes are admitted, the smaller the percentage of time for each process to run
	- Scheduler may limit the number of processes to provide satisfactory service to the current set of processes. 

![[Pasted image 20250221213948.png]]

## Medium-term Scheduler

- Part of the OSes swapping function, moving processes out of main memory to secondary storage or vice-versa. 
- "Swapping in/out" decisions are based on the need to manage the degree of multiprogramming (i.e. the mix of CPU bound and I/O bound processes)
	- CPU bound processes would go much faster if the CPU was faster
	- I/O bound processes would go significantly faster if I/O access was faster
	- Considers the memory requirements of the swapped-in processes. This information is stored in each processes PCB

## Short-term Scheduler

- Decides which processes are assigned to the CPU by the dispatcher. 
- Executes most frequently. 
- Makes the fine-grained decisions of which process to execute next.
- Invoked when an event occurs that could result in the CPU being assigned to another process (interrupts, traps or system calls)

## Short-term Scheduling Criteria

- Main objective is to allocate processor time in order to optimise certain aspects of system behaviour. 

User oriented criteria
- Relate to the behaviour of the system as perceived by the individual user
- Important for all systems

System-oriented criteria
- Focus is on effective and efficient utilisation of the CPU
- Generally of minor important


**Priority Queues**

- In Unix systems, priorities range from -20 to 19.
- The lower the value, the higher the priority. 
- These can be changed by the user if needed. 
- There are multiple queues for ready processes. 

Issues
- This can be a problem for low priority processes
- There may be a constant stream of higher priority processes that the CPU is assigned to, leaving lower priority processes unserved. 
- These processes are said to be experience "starvation"
- Priority can be made to change with age or execution history to prevent this. 


## Scheduling Policies

- The scheduler obeys a scheduling policy with two parts
- **Selection function**
	- Determines which of the ready processes should run on the CPU. 
	- May be based on priority, resource requirements or the execution characteristics of the process.
	- If based on execution characteristics, this can include:
		- Time spent waiting so far
		- Time spent running on the CPU so far
		- The processes estimated total service time. 
- **Decision Mode**
	- Specifies the instant in time at which the selection function is invoked. 
	- Two-categories
		- Non-preemptive: running processes will continue unless they block themselves
		- Preemptive: running provesses may be interrupted and moved to the ready state by the OS

## First Come First-Served

- Also known as first-in-first-out (FIFO) or a strict queuing scheme
- Selection function: The steps involved are, 
	- As each process becomes ready, it joins the ready queue. 
	- When the currently running process terminates, the process that has been in the ready queue the longest is selected to run on the CPU 
- Decision mode: non-preemptive, so no timer interrupts
- On it's on, not idea for time sharing-systems
	- In a mix of long and short processes, it tends to impact short processes more
	- Tends to benefit CPU bound processes, if there are many more I/O bound processes
	- Tends to impact I/O bound processes, if there are many more CPU bound processes
	- Can be very inefficent, leaving resources idle. 

## Round Robin

- Decision mode, so interrupts allowed
- Preemption based on hardware clock. 
- Also known as time slicing, each process in given a "slice" of time
- Selection function - upong preempting a processes that has used up its time slice, the next process will be the one waiting the longest. 
- A principle design issue is the length of time quantum (slice)to be used. 
- Very effective for time-sharing or transaction systems
- However, tends to impact I/O bound processes that spend a lot of time in blocked state.

## Why the length of the time quantum matters

- If a length of a time quantum is much larger than the total service time for most processes, then round robin degenrates to FCFS
- If the length of time is much smaller than the total service time s for most processes, then round robin tends to impact average throughput and service time, even though response time is relatively high. 

## Shortest process next

- Decision mode: non-preemptive policy
- Selection function - the process in the ready queue with the shortest expected processing time is selected next. Use FCFS to break ties. 
- A short process will jump to the head of the queue, possibiliity of starvation for longer processes
- A difficulty is knowing or estimating the expected time of processes. 
- Programmers can give estimates, but if this turns out be be substantially smaller than the actual running time, the OS may abort the job. 

## Shortest Remaining Time (SRT)

- Decision mode - preemptive version of SPN, can preempt running process
- Selection Function - When a process terminates, blocks or joins the ready queue, the short term scheduler chooses the process that has the shortest expected remaining processing time. 
- Use FCFS to break ties
- Risk of starvation for longer processes
- Similar to SPN, SRT requires an estimate of the remaining time. 
- Differs from other policies
	- Tends to give better throughput from SPN, since shorter jobs never have to wait for longer ones. 
	- Does no have the bias FCFS does to long processes. 
	- Tends to give better throughput and better overhead than round robin
	- Better overhead due to no timer interrupts and scheduler only needs to compare newly arrived processes, other ready processes don't need to be compared. 