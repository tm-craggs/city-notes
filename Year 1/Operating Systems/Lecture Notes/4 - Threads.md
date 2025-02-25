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

# One or more threads in a process

![[Pasted image 20250225183941.png]]

# Benefits of multithreading

- Multithreaded native application
	- A small number of highly threaded processes (PC and Console games)
- Multiprocess applications
	- Many single-threaded processes (Oracle DB and SAP)
- Java Applications
	- All applications that use a Java 2 platform, can benefit from multicore technology. 
- Multi-instance applications
	- Multiple of the same instances of the application in parallel. 

![[Pasted image 20250225184218.png]]

# Key benefits of threads

- Takes less time to create a new thread than a new process
	- There is no need to assign a new address space, for example. 
	- Threads can share the same resources allocated to the process
- Less time to terminate a thread than a process
	- Less for the OS to do
- Switching between two threads within the same process takes less time than switching between processes
	- No need for memory management overhead. For example new mapping of address spaces. 
- Threads more easily and quickly communcate, compared with processes
	- Threads belonging to the same process share resources allocated to the process.

# Thread use in a single-user system

- Foreground and background work, e.g. for a spreadsheet program. 
	- One thread could manage the display of menus and read use 