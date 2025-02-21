Today's questions

- What happens when a program's execution is interrupted
- How does the OS interleace the execution of multiple programs
- How does the OS ensure new processes are not waiting while the CPU is idle? 
- How can limited RAM be shared among interleaved processes. 
- What does a process look like to an OS
- What does an OS do when creating a process. 
- Is the OS a process?

## "Interrupting" processes

Interrupt
- Cause: External to the execution of the current instruction. 
- Use: Reaction to an asynchronous external event. 

Trap
- Cause: Associated with the execution of the current instruction
- Use: Handling of an error or an exception condition

Supervisor call
- Cause: Explicit request
- Call to an operating system function


# Definition of a Process

A process is:

- A program in execution
- An instance of a program running on a computer
- The entity that can be assigned to, and executed on a processor
- An executing set of related machine instructions. 
- A unit of activity characterised by a single sequential thread of execution, a current state and an associated set of system resources. 

It can be useful to think of programs as being passive, and processes being active.


# "Passive" vs "Active"

- Sheet music would be passive, while the music produced by an orchestra playing the sheet music is active. 
- A cooking recipe is passive, while cooking with the recipe is active. 
- In essence, the work done by following "passive" instructions is regarded as active.


## Management of Program Execution: Processes

- Processes were first used by designers of Multics OS in the 60s
- They are the **most important abstraction** provided by all modern OSes
- The OS uses processes to ensure
	- Resource are made available to multiple applications
	- The CPU is switched among multiple applications. 
	- The CPU and I/O devices can be used efficiently, securely, and reliably. 

