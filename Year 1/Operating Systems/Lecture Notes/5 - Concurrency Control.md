## The Challenges with Concurrent Execution

- **Race Condition** - Where the order in which processes access and alter a shared resource could affect the remainder and outcome of their execution. 
- In these situations, there may be a need for:
	- **Mutual exclusion** - Where the processes/threads are made to access the resource one at a time. 
	- Enforcing a **precedence** - The processes/threads must execute parts of their code in a certain order. 
- **Resource starvation** - A process waits an unaccptably long time to gain access to a shared resource, due 