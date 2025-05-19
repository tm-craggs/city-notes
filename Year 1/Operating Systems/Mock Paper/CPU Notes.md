## Performance Measures

**User Oriented** - From the perspective of a user or process

Response Time - The time between when the process arrives in the ready queue and when it is assigned to the CPU for the first time

Wait Time - Response Time + any additional delays

CPU burst time (service time) - Total time the process needs to spend running on the CPU

Turnaround Time - Time between when the process arrives in the ready queue and when it finishes executing. 

**System Oriented** - From the perspective of the system as a whole

Throughput - The number of processes that start and complete during the duration of observing the system

Wait time - For each process the total time the process spent waiting to be assigned to the CPU. 

All these assume negligible overhead in creating and admitting of processes

## First-Come First-Served

- Selection Function: Under the FCFS policy, the steps are
	- When a process is assigned to the CPU it runs till it terminates.
	- When the running process terminates, the process that has been in the queue the longest is assigned.
- Decision Mode:
	- Non-preemptive. A process will run on the CPU until it successfully completes.
	- Since we have assumed no processes will fail or make I/O requests. 

Throughput = number of executed processes / duration of observing system

![[Year 1/Operating Systems/Mock Paper/image-2.png|555x274]]

## Round Robin

- Decision Mode: Preemptive, based on hardware clock
- Selection Function:
	- When a process assigned, it runs for a fixed amount of time, called a quantum of time or a time slice.
	- If the process does not terminate before the time quantum elapses, the process rejoins the ready queue. Otherwise it terminates. 
	- The next process assigned to the CPU is the one waiting the longest. 

## Shortest Time Remaining

- Decision Mode: Preemptive version of shortest process next. The CPU can be reassigned whenever a new process enters the ready queue. 
- Selection Function: Under the SRT policy and the assumptions on our 4 processes, the steps are.
	- When a new process is assigned to the CPU, it runs until it either terminates or a new process joins the ready queue. 
	- When a process terminates or a new process joins the ready queue, the process assigned to the CPU is the process with the shortest remaining CPU burst time. 
	- Tie - resort the FCFS
