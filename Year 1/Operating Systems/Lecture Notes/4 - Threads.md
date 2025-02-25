# Quantitative Performance Measures

**User Oriented**
- Response time - Time between when the process arrives in the ready queue and when it is assigned to the CPU for the first time. 
- Turnaround time - Time between when the process arrives in the ready queue and when it finishes executing. 

**System Oriented**
- Throughput - The number of processes that start and complete during the duration of observing the system (the time between when the first process arrives and the last process terminates)
- Wait time - For each process, the total time the process spends waiting to be assigned CPU
- These definitions assume no overhead in the creation of a process, and negligible time taken to admit processes to the ready queue. 


![[Pasted image 20250225171603.png]]


## Arrival and Service Times

- Processes A B C and D are admitted into the ready queue by the long term scheduler. 
- Their estimated service times are (how long they need the CPU for) - 3, 6, 4 and 2
- Service times are another name for CPU burst time
- Assume:
	- These processes are all CPU bound, with no I/O requests
	- These processes will complete their execution sucessfully
	- No overhead in assigning processes to the CPU or freeing the CPU from processes
	- There are no other processes
	- Processes join the ready queue as soon as they are created. 
- Using an FCFS model, we now illustrate the order in which these processes are assigned to the CPU and how long they execute for, when they are assigned.
- We compute the response time, average turnaround time, throughput and average wait time resulting from FCFS policy.

FCFS - [[3 - CPU scheduling#First Come First-Served]]

Decision