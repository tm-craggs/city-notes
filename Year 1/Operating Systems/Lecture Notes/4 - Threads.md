# Processes and Threads

**Resource Ownership**:
- A process is assigned an address space containing program code, data, stack, heap and PCB. 
- A process is granted access to I/O devices and files. 
- In granting resources to processes, the OS protects processes from interfering with one and other. 

**Scheduling/execution**
- A process is scheduled and dispatched by the OS to run on the CPU. 
- A process follows an execution path that may be interleaved with other processes.
- A process can be in one of 7 or mote states, having varying dispatching priority over the course of its execution. 

- We formalise this distinction with a layer of abstraction - Threads
- The unit of dispatching/execution is a thread or lightweight process. 
- The unit of resource ownership and protection is a process or task. 
- Multithreading - The ability of an OS to support multiple, concurrent paths of execution within a single process. 
- Thread within a process share resources, and have more opportunity to interfere and interact with each other. 
- This makes thread synchronisation nessesary and easier than process syncing. 
- Each thread has:
	- A TCB (Thread Control Block) - This contains information nessesary for being assigned to and execution on the CPU. In contrast, the PCB contains this and more. (**Bold = part of the TCB**)
	- An **execution** state (e.g. running, ready, blocked)
	- A saved **thread context** when not running (saved values of CPU registers)
	- Associated variables such as a **program counter, stack pointer** and **frame pointer**
	- An execution stack
	- Some per-thread static storage for local variables
	- Access to the memory resources of its parent processes, shared with all other threads. 

