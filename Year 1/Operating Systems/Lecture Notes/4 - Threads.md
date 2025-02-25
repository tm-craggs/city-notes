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
	- One thread could manage the display of menus and read use input, while another executes user commands and updates the spreadsheet.
- Asynchrounus processing
	- Among the threads in a word processor, one thread could periodcally autosave work. 
- Speed of execution
	- Computing with one batch of data, one thread, while reading the next batch, different thread.
- Modular program structure
	- Programs that incolce a variety of activities, sources and destinations of input and output, may be implemented as threads. (video games)

# Thread execution state

- The states of a thread are ready, waiting, and blocked. 
- Operations associated with thread state-changes include:
	- spawn (creating a thread)
	- block (making an I/O request)
	- unblock (completion of I/O)
	- finish (completion of execution)

# Scheduling and thread states

- In an OS that supports threads, scheduling and dispatching is done on a thread basis. 
- Most of the thread's state information is maintained in thread-level data structures. 
- The state of a process can impact the state of all of its threads.
	- Suspending a process involves suspending all threads
	- Termination of a process terminations all threads of the same process. 

# Examples of threads improving throughput

![[Pasted image 20250225185355.png]]
![[Pasted image 20250225185426.png]]

# Types of threads

**User-Level Thread (ULT)**
- All thread management is done by the application
- The kernel is not aware of the existence of the threads.

**Kernel-Level Thread (KLT)**
- Thread management is done by the kernel. 
- No thread management code at application level, simply an API to the OS and kernel thread facility. 
- The kernel maintains context information for the process as a whole, and for the threads thereof; 

![[Pasted image 20250225190113.png]]


**Advantages of ULT**
- Thread switching does not require kernel mode privilages
- Scheduling can be application specific
- ULTs can run on any OS

**Disadvantages of ULT**
- In a typical OS, many system calls result in blocking and incure overhead
	- When a ULT makes a system call, all threads within a process become blocked. 
- In pure ULT, a multithreaded application cannot take advantage of multiproccessing (using multiple CPU cores) for speed improvements
- Some strategies for overcoming these disadvantages:
	- "Jacketing" - A method for converting a blocking system call into a non-blocking system call. 
	- Writing an applications as multiple processes rather than a single process. (Makes programming more complicated and incrases overhead)

**Advantages of KLT**
- Multiprocessing - The kernel can simultaneously schedule multiple threads from the same process on multiple processors.
- If one thread in a process is blocked, the kernel can schedule another thread of the same process.
- Kernel routines themselves can be multithreadded. 

**Disadvantages of KLT**
- Transfer of control from one thread to another within the same process, requires mode switches. 
![[Pasted image 20250225190456.png]]

# Combined Approaches

- Thread creation is done completely in the user space, as well as most of the scheduling and synchronization
- However, multiple ULTs from a single application are mapped into a smaller number of KLTs
- This allows for multiprocessing

![[Pasted image 20250225190648.png]]

# Thread-Process Relationships

![[Pasted image 20250225190734.png]]

# Why