## The Challenges with Concurrent Execution

- **Race Condition** - Where the order in which processes access and alter a shared resource could affect the remainder and outcome of their execution. 
- In these situations, there may be a need for:
	- **Mutual exclusion** - Where the processes/threads are made to access the resource one at a time. 
	- Enforcing a **precedence** - The processes/threads must execute parts of their code in a certain order. 
- **Resource starvation** - A process waits an unacceptably long time to gain access to a shared resource, due to other processes having priority. 
- **Deadlock** - Processes wait indefinitely for each other, unable to proceed with their respective executions. 

## Awareness between processes

![[Pasted image 20250327195854.png]]

## Mutual Exclusion: Software Approaches

- In 1965, Edsger Dijkstra reported an algorithm for mutual exclusion of two processes. Designed by Theodorus Dekker
- By developing Dekker's algorithm in stages, we can illustrate a number of the bugs encountered in developing concurrent programs. 
- In 1981, Gary Peterson found an alternative method similar to Dekkers. 

## Mutual Exclusion Requirements

- Only one process at a time is allowed access to a critical section. 
- A process that halts in its non-critical section must not precent other processes from accessing their critical sections. 
- A process that requires access to its critical section must **not** be be delayed indefinitely so no deadlock or starvation is allowed. 
- When no process is requesting access to a critical section, any subsequent process that requests access should be granted access without delay. 
- No assumptions about relative process speeds, or number of processes are made.
- A process remains inside it's critical section only for a finite amount of time. 

# Semaphores

- A semaphore is an integer value used for signalling among processes, together with 3 atomic operations: initialise, decrement, and increment. 
- These operations are the only way to inspect or manipulate semaphores.
- Semaphores allow two or more processes to cooperate by means of simple signals. 
- This is done by calling `semSingal()` or `semWait()` methods, related to the increment and decrement semaphore operations. 
	- Semaphore "s" is initialised to a non-negative integer value. 
	
	- When called, the `semWait(s)` operation decrements "s" by 1. 
	- If s becomes negative, the process execution `semWait` is blocked.
	- Otherwise the process continues execution. 

	- When called, the `semSingals(s)` operation increments "s" by 1. 
	- If the resulting values of "s" is less than or equal to zero, then a process block by a `semWait` operation is unblocked. 


![[Pasted image 20250327203226.png]]

![[Pasted image 20250327203245.png]]

## Producer/Consumer problem

General statement:
- One or more producers are generating data and placing these in a buffer.
- A single consumer is taking items out of the buffer one at a time. 
- Only one producer or consumer may access the buffer at one time. 

The challenge:
- Ensure that the producer won't try to add data into the buffer if it is full. And, that the consumer won't try and read from an empty buffer. 

The solution:
- Use an infinite buffer
- Use a finite circular buffer. 