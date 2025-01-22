- A way of making processors run more efficiently
- This can be done through doing tasks in parallel

There are 2 performance metrics
- Latency - The time it takes to do a single tasks
- Throughput - The total amount of work we can do in a given amount of time
- Pipelining affects throughput, but not latency. Tasks still take the same amount of time to process individually, but running more tasks in parallel increases the amount you can do in a given amount of time. 

**Pipelining at the conceptual level**

- Each task can be broken down into a series of smaller tasks (sub tasks)
- These tasks can often be run in parallel, this is called instruction level pipelining (IPL)
- When these sub-tasks do not compete for resources, the tasks can be run at the same time
- Pipelining is a way of executing these smaller tasks in parallel
- Simultaneous/parallel tasks use different resources

**Performance**
- Pipelining does not increase the latency of a single task, but it can increase throughput
- The more pipeline stages we have, the quicker we can go
- However, this can cause issues if they begin to conflict

**Pipelining and the FDE cycle**
- We can split the FDE cycle into 4 stages
	- 1) Fetches the instruction
	- 2) Decodes it and finds the address of the operand
	- 3) Fetches operand
	- 4) Executes the instruction
- For every clock cycle, we can make it so that one small task is carried out.
- For example, as soon as one instruction is fetched, the next instruction can be fetched on the next cycle, although the first instruction has not fully gone through the process yet.
- They are now running in parallel. 

![[Pasted image 20241206150639.png]]

**Hazards in pipelining**

- Pipelining is not perfect, there are some tradeoffs.
- Conditional branches are an example of this. When running an if, else conditional, the program cannot fetch the next instruction, because it is unknown if or not the program will need to skip instructions based on the outcome of the if condition. 
- It therefore will need to wait for the rest of the cycle to catch up, before it can check the if condition and know where the next instruction should be fetched from. 
- This is called pipeline stalling

![[Pasted image 20241206151655.png]]


- We assume the pipeline can be filled at all times, but this is not always the case.
- Hazards are situations that prevent the next instruction in the next cycle. 
- There are 3 main types of hazard:
	- Control Hazards - Loading instructions into pipeline before the result of a decision is known (loading instructions after a branch)
	- Data Hazards - Instruction depends upon the results of a previous instruction still in the pipeline (compound maths expressions)
	- Structural/resource hazards - Hardware cannot support some combination of instructions in the same clock cycle (simultaneous memory access or one instruction is writing while another is reading)

**Microprocessor without interlocked pipelined stages (MIPS)**

- A RISC instruction set architecture
- Originally, MIPS was designed for general purpose computing
- MIPS processors have started being implemented in routers and gateways

Notation for MIPS pipeline

- Five stages, one step per stage
- IF: Instruction fetched from memory
- ID: Instruction decode and register read
- EX: Execute operation or calculate address
- MEM: Access memory operand
- WB: Write result back to register

Example instruction:

- Add $s0, $t0, $t1 -> $s0 = $t0 + $t1
- Where $x denotes the contents of a register named x
- Add does not write until the 5th stage of the pipeline
