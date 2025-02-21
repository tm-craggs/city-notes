
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

