# Operating Systems as Abstraction

- Operating Systems are the layer of abstraction of a computer system that sits in-between programs and hardware components. 
- Everything above the operating system is known as application software. 
- Applications do not interface directly with the hardware. They interface with the operating system. The operating system will interface with the hardware. 

![[Pasted image 20250117185508.png]]

**Overview of key functions**

- It provides a platform for all computer programs to execute on a computer system. 
- Controls the hardware for the software applications
- Manages hardware resources for applications
- Manages files and processes
- Controls inputs and outputs

**Evolution**

- Operating Systems have paralleled the evolution of computers.
- As hardware has become more powerful, newer operating systems allowed people to more easily manage the power. 
- In the early days, all OS could do was load, execute and terminate a program. 

**Operating Systems in the Personal Computer Era**

- PC operating systems are designed for ease of use
- The idea that revolutionised small computer OS was the BIOS (Basic Input Output System)
- BIOS takes care of details in handling peripheral devices and gets the OS started using a boot loader. 
- The boot loader starts automatically and loads the rest of the OS

**The OS kernel**

- The kernel is at the core of an OS
- It performs fundamental functions
	- Deciding which process gets the CPU and when
	- Ensuring that programs don't overwrite each other
	- Handles virtual memory
	- Arbitrating shared resources. 
	- Dealing with events outside simple flow. 
	- Only allowing legal access (security)

![[Pasted image 20250117190213.png]]

**Scheduling**

- The OS schedules process execution
- The OS determines which process will be granted to the CPU (long term scheduling)
- For a number of active processes, the OS determines which process have access to the CPU at a particular time (short-term scheduling)
- Context Switches - Occur when the process using the CPU is halted and the CPU is switched to another process
- The state of the process is preserved during a context switch. 
- Some simple approaches to CPU scheduling are
	- First Come First Served - Where jobs are serviced in arrival sequence and run to completion
	- Shortest job first - Short job in duration gets scheduled first
	- Round robin - Scheduling where each job is allotted an amount of CPU time and a context switch occurs when this time expires. 
	- Priority scheduling - Delays a job with lower priority when a higher priority job needs the CPU

**Assemblers**

- Simplest of all programming tools
- Translates mnemonic instructions to machine code
- They created an object program file from mnemonic source code
- They do so in 2 passes of the source code
- First pass:
	- The assembler assembles as much of the program as it can
	- It builds a symbol table that contains memory references for all symbols in the program
- Second pass:
	- The assembler completes instructions using the values from the symbol table


**Assemblers visualised**

- It creates a symbol table storing translations of memory address labels to actual addresses 

