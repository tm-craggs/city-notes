## Goals and Principles of Protection

- A computer consists of a collection of objects
- Each object has a unique name and can be accessed through a well-defined set of operations
- Protection problem - ensure that each object is accessed correctly and only by those processes that are allowed to do so

- Protection involves controlling the access of processes and users to the resources defined by a computer system
- The processes in an operating system must be protected from one another's activities
- To provide this protection, we can use various mechanism to ensure only processes that have authorisation from the OS can operate on files, memory, CPU, networking and other system resources
- These mechanisms must provide a means for specifying the controls to be imposed, together with a means of enforcement. 

- Protection was originally designed for multiprogramming systems to let untrustworthy users safely share resources, like memory. 
- Over time protection mechanisms have evolved to improve the reliability of systems, especially ones connected to the internet. 
- Protection links heavily with [[7 - File Systems#File Sharing]]

**Principles of Protection**

- The guiding principle is the **principle of least privilege**
	- Programmes, users and systems should be given **just enough privileges** to perform their tasks
	- Limits damage if entity has a bug, or gets abused
	- Can be static or dynamic
	- Static - During life of system, during life of process
	- Dynamic - Changed by process as needed by domain switching or privilege escalation

**Least Privilege**

- Consider one of the tenets of UNIX - A user should not run as root
- Most users respect that, fearing an accidental delete operation of which there is no undo
- Because root is virtually omnipotent, the potential for human error when a user acts as root is grave, and its consequences can be far reaching. 
- Now, consider rather than human error, damage may result from malicious attack. A virus launched by a click for example, or a buffer overflow or other code injection attack that is successfully carried out against a root-privileged process. 
- These could affect all users if run as root. 

## Protection through Domains

**Domain Structure**

- Access-right = `<object-name, rights-set>` where rights-set is a subset of all valid operations that can be performed on the object. 
- Domain = set of access-rights

**Domain Implementation (MULTICS)**

- Multics (Multiplexed Information and Computing Service) was an early time-sharing OS.
- Imagine domains as concentric rings, like an archery target. 
- Ring 0 (centre) has most privileges - typically the kernel. 
- Outer rings, e.g.  `n - 1` have fewer privileges, typically user applications 

- Let `Di` and `Dj` be any two domain rings
- If `j < i` -> `Di ⊆ Dj`
- A process executing in domain `Dj` has more privileges than a processes executing in domain `Di`
- This means, a processes in domain `Dj` (inner ring) can do everything a process in `Di` can do - and more. 
- More inner = more privilege 

**Multics Benefits and Limits**

- Ring / hierarchical structure provided more than the basic kernel / user or root / normal user design. 
- Complex -> more overhead
- But does not allow strict need-to-know
	- If an object is accessible in `Dj` but not `Di` then `j < i`
	- But then every segment accessible in `Di` also accessible in `Dj`


**Domain Implementation (UNIX)**

- Domain switch accomplished via passwords.
	- `su` (superuser) command temporarily switches another user's domain when other domain's password is provided
- Domain switching via commands
	- `sudo` (superuser do) command executes specified command in another domain, if original domain has privilege or password given. 
- Each user-id names a domain determined by all the file permissions
- UNIX allows to switch 
## Access Matrix

## Revocation of Access Rights

## Access Control Policies

