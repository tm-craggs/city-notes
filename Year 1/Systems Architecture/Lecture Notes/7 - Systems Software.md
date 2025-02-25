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

![[Pasted image 20250118195311.png]]

**The Assembler Flow**

1) Programmer writes text
2) Creates a .asm file
3) Calls the assembler to produce a .bin file
	1) First pass assembles and builds the symbol table
	2) Second pass resolves the labels to actual addresses
4) Calls a loader to relocate the program into absolute memory addresses and places it into memory
5) Control is passed to the program
6) The PC is loaded with start address
7) The program runs

# Compilers

**The hierarchy of Programming Languages**
Starting from easiest for humans to understand

- 5th generation languages (natural language or visual tools)
- 4th generation languages (SQL, Python)
- 3rd generation languages (Java, C, C++)
- 2nd generation languages (Assembly Code)
- 1st generation languages (binary machine code)

**Complilers**

- Compilers are for high level languages what assemblers are for low level languages. 
- Compilers bridge the gap between the high level language and the machine's binary code
- Most compilers do this in a six-phase process:
	- Lexical analysis - Exacts tokens (reserved words and variables)
	- Syntax Analysis (parsing) - Checks code grammar and statement construction
	- Semantic Analysis - Checks data types and the validity of operators (e.g. multiplying a string would be a semantic error)
	- Intermediate Code Generation - Creates assembly level code for optimisation and translation
	- Optimisation creates more efficient assembly code
	- Code generation - Creates binary code from optimised assembly code (this may be using the assembler)
- Through this molecularity, compilers can be written for numerous platforms only by rewriting the last 2 phases. This makes HLLs very machine independent. 

# Virtual Machines

- A VM is the virtualisation on emulation of a computer system
- It is managed by the OS kernel of the main system

**Java Virtual Machine**

- The Java Virtual Machine (JVM) is a miniature OS
- It loads programs, links them, starts execution threads, and manages program resources. 
- At execution time, A JVM must be running on the host system. 
- It loads and executes the bytecode class file (the "machine code")
- Steps in the JVM
	- Bytecode verifies: The JVM verifies the integrity of the bytecode. 
	- Class loader: Loads the bytecode of classes in memory and performs a number of runtime checks
	- The loader invokes the bytecode interpreter for execution