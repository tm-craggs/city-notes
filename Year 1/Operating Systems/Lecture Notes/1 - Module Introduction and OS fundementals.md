# Assessment

Coursework (40%)
- 2 quizzes in lecture worth 8% each + 4% bonus
- 2 quizzes in weeks 5 and 11 during lecture
- 1 final "take home" quiz - 16%

Exam (60%)
- Final exam - 60%
- Sat during spring exam period

**Note: Re-watch first half of lecture and revise number systems**

# Operating Systems

**What is an operating system**?

- A program or collections of programs that controls the execution of application programs. 
- An interface between applications and hardware. 

Main objectives of an OS
- User convenience
- System efficiency, reliability and security
- Ability to add new system functions without interfering with services provided by the system. 

What services does an OS provide?
- Program development
- Manage program execution
- Access I/O devices via uniform interface
- Controlled access to files
- System access
- Error detection and response
- Usage and performance statistics


An OS is a big deal!
- A CPU can only execute one instruction at a time, but we want to run lots of programs at the same time, without interfering with each other
- We need the CPU to work with multiple different devices (keyboard, disk drive, display, etc.)
- The CPU can only execute instructions which are in RAM, so we need a way to transfer a program from disk into RAM.

The CPU and OS must work together
- IF the OS controls the use of a computers resources and the OS is not in explicit control of the CPU, it must relinquish control of the CPU to programs, and must depend on the CPU to retake control when needed. 
- To assist the OS, the CPU supports two modes of operation. 

Modes of CPU operation

User mode
- CPU executes in use mode for user programs
- Certain areas of memory are protected from user access
- Certain instructions may not be executed. 

Kernel Mode
- CPU executes in kernel mode for OS
- Protected areas of memory may be accessed
- Privileged instructions may be run

# Interrupts 

x