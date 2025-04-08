# File Concept

- File system refers to the logical structure, and not the hardware in which the data is stored.
- A file system allows data to be formatted, stored, and accessed in a disciplined and convenient manner. 
- The users of a file system do not need to understand how the underlying physical storage media works. 
- The same file system can be implemented on many different devices. (Even in RAM)

##### File attributes

- Files contain data but also have other attributes
	- Name - Only information kept in human-readable form, this is what users see.
	- Identifier - Unique tag (number) which IDs each file within a file system
		- In UNIX these are called i-numbers

- In UNIX
	- File names are only stored in directories, they are not attributes of files themselves. 
	- A directory contains a mapping from names to i-numbers. 
	- More than one name can be mapped to the same i-number

- Files contain data but also have other attributes:
	- Type - In systems that support different file types
	- Location - Point to file location on device (disk)
	- Size - Current file size. 
	- Protection - Controls who can read, write, and execute
	- Time, date and user ID - Data for ownership, protection, security and auditing. 

# File Operations

- A file is an abstract data type. 
- This means a group of objects that are defined by its behaviour, the behaviour is defined by values and operations
- The main file operations are:
	- Create
	- Read
	- Write
	- Open
	- Close
	- Delete
- Further operations include:
	- Reposition (a pointer) within file
		- Write (at write pointer location)
		- Read (at read pointer location)
	- Truncate
	- Append
	- Get attribute
	- Set attribute

##### Open Files

- Several pieces of data are needed to manage open files:
	- Open file table - Tracks open files
	- File pointer - Pointer to last read/write location, per process that has the file open. 
	- File-open count - Counter of number of times a file is open. To allow removal of data from open-file table when last processes closes it. 
	- Disk location of the file - Block on disk
	- Access rights - Per-process access mode information

##### Open File Locking

- Provided by some OS and file systems
- Mediates access to a file
- Can be **mandatory** or **advisory**
	- Mandatory - Access is denied depending on locks held and requested
	- Advisory - Processes can find status of locks and decide what to do. 

##### Files Types

- An OS may distinguish between a range of different types. 
	- Text, binary, sound, video
	- In such a typed system, copy binary to text would not be permitted. 
- More common, all files are just a sequence of bytes.
	- OS and user applications may use file name extensions as hints about data formats. 

![[Pasted image 20250408144916.png|349x367]]

##### Access Methods

**Sequential Access**
- The most simple access method. 
- Data is accessed in order, one record after another, like reading a cassette tape. 
- Operations:
	- Read next - Read the next piece of data
	- Write next - Write the next piece of data
	- Reset - Go back to the beginning of the file. 
- You cannot jump to an arbitrary location directly


**Direct Access**
- File is fixed length logical records
- You can jump to any record directly. 
- Operations:
	- Read n - Read nth record
	- Write n - Write to the nth record
	- Position to n - Move the pointer to the nth record
	- Read next - Work like sequential after positioning 
	- Write next
- This is like a CD, you can skip to any track instantly 
# Disk and Directory Structure

##### Operations Performed on Directories
- Search for a file
- Create a file
- Delete a file
- List a directory
- Rename a file
- Traverse the file system 

##### Disk Structure
- Disk can be subdivided into partitions
- Disk or partition can be used raw - without a file system, or formatted with a file system. 
	- Different partitions may be formatted as different types of file system. 
	- Linux Supports many: ext4, btrfs etc.
- Each partition containing a file system will store info relating to that file system in a device directory or a volume table of contents. 

##### RAID

- Disks or partitions can be RAID protected against failure
- RAID - Redundant Array of Inexpensive (Independent) Disks
	- Use multiple smaller disks
	- Parallelism improves performance
	- Plus extra disks for redundant data storage. 
- Provides fault tolerant storage system
	- Especially if failed disks can be "hot swapped"

##### RAID 1
- RAID 1 mirroring: N + N disks, replicate data. 
- Write data to both data disk and mirror disk. 
- On disk failure, read from mirror. 

##### RAID 5: Distributed Parity

- N + 1 disks
	- Data striped across N disks at block level. 
	- Redundant disk stores parity for a group of blocks, but parity blocks distributed across disks. 

##### Directory Organisations
- The directory is organised logically to obtain
	- Efficiency - Locating a file quickly
	- Naming - Convenient to users
		- Two users can have same name for different files
		- The same file can have several different names
	- Grouping - Logical grouping of files by properties 

##### Directory Structure
- A collection of nodes containing information about all files. 

![[Pasted image 20250408163339.png|457x215]]

##### Additional File-system Structure
- Different file systems provide different ways of structuring file access to make life easier for users and applications. 
- From simple to sophisticated
	- Single-level folder structure
	- Two-level folder structure
	- Tree-structured
	- Graph-structured

##### Single-Level Directory

- A single directory for all users. 
- It has naming and grouping problems

![[Pasted image 20250408163701.png|514x155]]

##### Two-Level Directory

- Separate directory for each user
- Can have the same file name for different users
- Efficient searching
- No grouping capability

![[Pasted image 20250408163811.png|515x180]]


##### Tree-Structured Directories

- Efficient searching
- Grouping capability

![[Pasted image 20250408163855.png|488x332]]

- Absolute or relative path names
	- Unix absolute path starts with /
	- Windows absolute path starts with C:, F:
- Examples:
	- mkdir /home/troy/fruit
	- cd /home/troy/fruit
	- touch apples
	- touch pears
	- mkdir ../veg

![[Pasted image 20250408164153.png|289x308]]

##### Acyclic-Graph Directories 

- Have shared sub-directories and files

![[Pasted image 20250408165031.png|341x271]]

- Two different names (ali)


# File-System Mounting

# File Sharing

# Protection
