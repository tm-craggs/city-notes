**The overview of a simple computer**

Three main components
1) CPU
2) Main Memory
3) I/O Subsystem

The main operations of the CPU
- Processes instructions on data. 
- Reads from the input and writes the output. 
- Reads from and stores to memory. 
- Keeps track of what to do next

**CPU Basics**

- The two principle parts of the CPU are the Datapath and the Control Unit
- The Datapath consists of an ALU storage units (registers)
	- The ALU carries out logical and arithemetic operations as directed by the control unit
	- Registers hold data that can be readily accessed by the CPU. They can be implemented using D flip-flops. A 32-bit register requires 32 D-flipflops
- Various CPU components perform sequenced operations according to signals provided but its control unit. The control unit determines which actions to carry out according to the values in a program counter register. 

**Clocks**

- Every computer contains at least one clock that synchronises the activities of its components.
- A fixed number of clock cycles are required to carry out each data movement or computational operation. 
- The clock frequency measured in megahertz, or gigahertz, determines the speed with all operations are carried out. 
- Clock time is the reciprocal of clock frequency. 


**Clocks vs CPU Time**

- Clock speed should not be confused with CPU performance
- The CPU time required to run a program is given by the general performance equation. 

![[Pasted image 20250120150206.png]]

CPU throughput can be improved by reducing
- The number of instructions in a program
- The number of cycles per instruction
- The number of nanoseconds per clock cycle


MARIE Architecture

- AC: Accumulator - General purpose register holds the data the CPU works with
- MAR: Memory Address Register - Holds the address of the data being referenced from memory
- MBR: Memory Buffer Register - Data read from or to be written to memory. 
- PC: Program Counter - Holds the address of the next instruction to be executed. 
- IR - Instruction Register - Holds the next instruction to be executed. 
- InREG - Holds data received from the input device
- OutREG - Holds the data to be sent to the output device

**Busses**

- A bus is a set of wires used to connect multiple subsystems within the computer. At any time, only one component can use the bus. 

**Datapath in MARIE**

- MARIE has a 16 bit datapath which is a network of registers and arithemetic and logic units connect by bus

# Instruction Set Architecture

- The instruction set architecture of a computer specifies the instruction that a computer can perform
- It is the principle interface between the software and hardware. 
- Some ISAs include hundreds of different instructions, MARIE is only 13. 
- ISA describes the format of the instructions, giving the operation an opcode and operand

![[Pasted image 20250120152417.png]]

**Instruction processing**

- The fetch decode execute (FDE) cycle is the series of steps that a computer carries out when it runs a program. 
	1) We fetch an instruction from memory, and place in IR
	2) Once in IR, it is decoded to determine next steps.
	3) If an operand is involved, it is retrieved and placed in the MBR
	4) With everything in place, the instruction is executed. 
	5) The PC is incremented 

**Micro-operations**

- Each ISA level instruction actually consists of a sequence of smaller instructions called micro-operations. 
- The exact sequence of micro-operations that are carried out by an instruction can be specified using the register transfer language (RTL) or register transfer notation (RTN)
- In the MARIE RTL, we use the notation M[X] to indicate the actual data value stored in memory location X, and NOT symbol to indicate the transfer of bytes to a register or memory location

Example Micro-operations

![[Pasted image 20250120153217.png]]

![[Pasted image 20250120153318.png]]

SKIPCOND Instruction

- SKIPCOND: Skip the next instruction on condition according to the value of the AC
- Conditional branch, just like if
- The opcode of the SKIPCOND instruction is used to specify the condition
- The RTL for this is complex 

![[Pasted image 20250120154130.png]]


**Extending instruction set**

- So far, all instructions use direct addressing
- This means that the address of the operand is stated in the instruction
- It is often useful to use indirect addressing, where the address of the address of the operand is given in the instruction

![[Pasted image 20250120155843.png]]

RISC vs CISC

- Computers become more complex, and their instruction sets reflect this. 
- There are 2 main philosophies. 
- CISC (Complex Instruction Set Computers)
	- Each single instruction executes a number of low-level instructions
	- Multiple addressing modes
	- Pre 1990
- RISC (Reduced Instruction Set Computer)
	- Each instruction is a single low-level instruction
	- Few addressing modes
	- Post 1990

RISC

- Fewer bits are allocated the opcode, which means a smaller instruction set
- Each instruction does less (e.g. add may require 2 instructions, LDA and ADD)
- More instructions needed for a given task
- A given instruction takes less clock cycles
- More RAM needed to store a program (more code)
- High level language compiler is more complex and slower
- Assembly programmers have more work to do
- Simpler instructions mean that RISC chips have less components and transistors, cheaper to produce and more power efficient. 
- More bits allocated to the operand means that more memory locations can be accessed directly
- Fewer addressing modes needed.

CISC

- More bits are allocated to the opcode, larger instruction set. 
- Each instruction can achieve more (e.g. add X, Y)
- Less instructions needed for a given task
- Each instruction takes more clock cycles
- Less RAM needed to store a program (less code)
- High level language compilers is less complex and quicker
- Easier for assembly programmers
- More complex chips are more expensive to design and produce
- Fewer bits allocated to the operand means that fewer memory locations can be accessed directly
- More addressing modes needed. 