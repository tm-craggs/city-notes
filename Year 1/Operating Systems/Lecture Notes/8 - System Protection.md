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
- UNIX allows to switch domains
- Domain Switch accomplished via file system
	- Each file has a domain bit (setuid bit)
	- When file is executed and  setuid = on, then user-id is set to owner of the file being executed.
	- When execution completes, user-id is reset. 
## Access Matrix

- View permissions as a matrix
- Rows represent domains
- Columns represent objects

![[image-6.png|398x171]]

- Access (i, j) is the set of operations that a process executing in Domain (i) can invoke on object (j)

**Groups**

- How many groups exist?
- Many, depending on the settings of the system. 
- There are several ways to check, but one is to look in /etc/group


![[image-7.png|340x362]]

- You can make a table where owners and groups are different. The processes is as follows:

- Step 1 - `cat` out the members of each group, and use `ls -l` to print the file permissions for each file.  

![[image-10.png|669x86]]

- Step 2 - Fill in an empty table with the file names as the columns and the users as the rows. 

- Step 3 - Check what permissions a user has with the below steps
	- Step 1 - Check if they are the owner of the file, if they are, they will have owner permissions (the first set of 3 permissions)
	- Step 2 - Check what group the file is in, and check if the user is also in that group. If they are, they will have group permissions (the second set of 3 permissions)
	- Step 3 - If they are not the owner or in the group, then they will have other permissions. (the final set of 3 permissions)

![[image-9.png|457x167]]

**Access Matrix: Mechanism vs Policy**

- Access matrix design separates mechanism from policy. 
- Mechanism
	- Operating system provides access matrix + rules
	- It ensures that the matrix is only manipulated by authorised agents and that rules are strictly enforced.
- Policy
	- User dictates policy
	- Who can access what object and in what mode. 
- The access matrix scheme provides us with a way to specify a variety of policies. 
- The mechanism enforces the rules specified by the access matrix, ensuring the semantic properties outlined hold
- Specifically: the mechanism must ensure that a process executing in domain `Di` can access only those objects specified in row i, and then only as allowed by the access-matrix entities. 
	- Our choice of policy decides which rights should be included in the `(i,j)th` entry. 
	- The access matrix mechanism enforces those choices. 
	- Imagine it like the legislature vs the judiciary 

## Revocation of Access Rights

- In a dynamic protection system, we may sometimes need to revoke access rights to objects shared by multiple users. 
- There are various options to remove the access right of a domain to an object, including:

- **Immediate vs Delayed**
	- Does revocation occur immediately, or is it delayed?
	- If revocations is delayed, can we find out when it will take place?

- **Selective vs General**
	- When an access right to an object is revoked, does it affect all the users who have an access right to that object, or can we specify a select group of users whose access rights should be revoked?

- **Partial vs Total**
	- Can a subset of the rights we associated with an object be revoked?
	- Or must all access right be revoked?

- **Temporary vs Permanent**
	- Can access be revoked permanently (revoked access right will never again be available)
	- Should access be revoked and later be obtained again?

## Access Control Policies

- An access control policy dictates what types of access are permitted, under what circumstances, and by whom. 
- ITU-T recommendation X.800 defines access control as follows:
	- The prevention of unauthorised use of a resource, including the prevention of a use of a resource in an authorised manner. 

- Access control policies are generally grouped into the following categories
	- Mandatory access control (MAC)
	- Discretionary access control (DAC)
	- Role-based access control (RBAC)

**Mandatory Access Control (MAC)**

- MAC controls accessed based on comparing security labels with security clearances for objects or users. 
- Policy dictates appropriate mapping between clearances and labels. 
- Example:
	- Consider a simple set of labels, ordered according to level of privilege. "unclassified", "secret", "top secret"
	- A process/user with secret clearance will be able to create similarly labelled processes, which will then have access to "unclassified" and "secret" files, but not to top secret files. 

**Discretionary Access Control (DAC)**

- DAC - Scheme in which an entity or object (user) may enable another entity to access to resource.
- This policy is termed discretionary, because an entity might have access rights that permit the entity, by its own volition, to enable another entity to access some resource.
- In MAC, it is centrally controlled, an administrator who changes the levels.
- In DAC, users have the ability to assign/without access rights - to edit cells within the access matrix, for the objects that they own

**Role-based access control (RBAC)**

- Controls access based on the roles that users have within the system, and on rules stating what accesses are allowed to users in given roles. 

![[image-11.png|345x163]]

- RBAC can still use a matrix-based allocation, but now there are 2 matrices. 
	- Map users and roles
	- Map access rights and roles

![[image-12.png|354x140]]

**Protection != Security**

- File system protection mechanisms may prevent a processes owned by `watson` from accessing a file owned by `sherlock` 
- But, what if `watson` can login as `sherlock` (masquerading)
	- Then `watson` can execute processes owned by `sherlock`
	- So `watson` can see and modify `sherlock's` data and processes
- This will be explored more next week. 