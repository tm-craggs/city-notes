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

- Pr

# Disk and Directory Structure

# File-System Mounting

# File Sharing

# Protection
