## The Challenges with Concurrent Execution

- **Race Condition** - Where the order in which processes access and alter a shared resource could affect the remainder and outcome of their execution. 
- In these situations, there may be a need for:
	- **Mutual exclusion** - Where the processes/threads are made to access the resource one at a time. 
	- Enforcing a **precedence** - The processes/threads must execute parts of their code in a certain order. 
- **Resource starvation** - A process waits an unacceptably long time to gain access to a shared resource, due to other processes having priority. 
- **Deadlock** - Processes wait indefinitely for each other, unable to proceed with their respective executions. 

## Awareness between processes

![[Pasted image 20250327195854.png]]

