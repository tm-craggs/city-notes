
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
