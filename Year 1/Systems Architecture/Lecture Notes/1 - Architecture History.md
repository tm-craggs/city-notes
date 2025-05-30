
**Early Devices** 
- Mechanical calculating machines (1642-1945) such as the Mechanical Calculating Clock
- Difference Engine and Analytical Engine - Charles Babbage
- Analytical Engine had many of the components of a modern computer, the mill (ALU), the store (memory) and input and output devices. 

**First Generation**: Vacuum Tube Computers (1945-53)
- These computers used valves and vacuum tubes to create logic circuits. 
- Very large, could take up entire rooms.
- ENIAC 1945 - The first general purpose, all electronic computer. 

**Second Generation:** Transistorised Computers (1955-65)
- Transistors replaced the vacuum tubes, could use electricity to create logic circuits. 
- Computers became smaller, faster and consumed less power.
- Still bulky and expensive
- Examples: IBM 7094, DEC PDP-1

**Third Generation:** Integrated Circuit Computers (1965-80)
- Integrated Circuits contained dozens of integrated transistors
- Integrated circuits were made of silicon, often called microchips
- Computers became faster, smaller and cheaper

**Fourth Generation:** Very Large Scale Integration (VLSI) Computers (1980-Present) 
- VLSI chips could have 10,000 components per chip
- 1981, IBM introduced the Personal Computer

**Modern Computers:**
- System on Chip (SoC) - All components of the computer are stored on one chip.
- New types of processors and memory, such as Graphics Processing Units (GPUs)
- Laptops, smartphones, tablets and smart watches. 

Mechanical ➔ Vacuum tube ➔ Transistor ➔ Integrated Circuit ➔ Very Large
Scale Integration ➔ System on Chip

**Semiconductors**
- The most significant factor that allowed progress was the move to the use of semiconductors
- They are a type of material that can act as conductors or insulators.
- They switch between these two states under external control. 
- These can be used to create transistors that function as switches, this makes the basic logic of a computer. 
- Silicon is a semiconductor material that can be manufactured and processed efficiently and inexpensively
- This is why modern electronics are called "silicon chips"

**Moore's Law**
- Transistor count in Integrated Circuit chips will double roughly every 18-24 months. - Gordon Moore (1965)
- Moore's law predicts that this trend will continue into the foreseeable future. 
- Shrinking transistors have powered this trend, however we are reaching the limits of what is physically possible. New ways must be found to improve computing power (quantum computing)

**The von Neumann model:**
- All modern stored-program computers are based on the von Neumann model 
- Also called stored program digital computer.
- It consists of 5 main components
	- Control Unit
	- Arithmetic Logic Unit
	- Registers
	- Main memory
	- Input/Output system
- There is a single datapath between the CPU and main memory (von Neumann bottleneck)

**Fetch-Decode-Execute Cycle:**
- The von Neumann model uses the Fetch-Decode-Execute cycle
- Control Unit fetches next instruction to execute from memory
- Instruction is decoded
- Any required data operands are fetched from memory to registers
- The ALU executes instruction and puts results in registers/memory

**Harvard Model**
- An incremental improvement based on von Neumann
- It adds processors, and has separate busses for data and instructions. Which reduces the von Neumann bottleneck. 

**Key Processor Components**
- Registers - Local storage of key data
- Memory Management Unit (MMU) - Interface to main memory
- Instruction fetcher/decoder - Fetches/decodes instruction given at program counter
- Arithmetic Logic Unit (ALU) - Performs calculations and operations.
- Datapath / Control - Controls the flow of information that allows instruction to be executed.

**Abstraction:**
- The act of representing essential features without including the background details
- The abstraction principle is used to allow efficient design and implementation of complex software systems. 

**Key Layers of Abstraction**
- Systems can be decomposed into layers
- Abstraction allows layers to hide lower level information from higher levels
- Higher levels should be useful without being cluttered with unnecessary detail
- For example: You do not need to know about electron flow or binary calculations while running a word processor. 
- Sometimes you need to break abstraction to get things right, such as optimising a program, which may require in-depth knowledge about caching architecture. 

![[Pasted image 20250108185713.png]]

