
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

User oriented criteria
- Relate to the behavior of the system as perceieved by the indivudal user
- Important for all systems

System-oritented criteria
- Focus is on effective and efficient utilisation of the 

