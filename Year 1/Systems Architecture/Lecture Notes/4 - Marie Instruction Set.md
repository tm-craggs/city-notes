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
- Some ISAs include hundreds 