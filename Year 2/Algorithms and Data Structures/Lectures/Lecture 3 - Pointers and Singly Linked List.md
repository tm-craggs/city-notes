#### Dynamic Data Structures

- Amount of data to store often vary in size in ways we cannot determine beforehand.
- This is difficult when using a language without garbage collection (C, C++)
- Reallocate-and-copy of arrays can solve this problem. 
- In general, linked structures are more flexible. 
	- Singly linked lists
	- Doubly linked list and circular lists
	- Trees and graphs

#### Pointers

- When we create a new object, in a language like Java, and give it a variable. All it contains is a memory reference. 
- This is known as a **pointer**, as it points to a physical location in memory where the class is. 
- Every reference type can have value null, which refers to no object at all. 
- Several variables may refer to the same address

#### What are links?

- So all object variables in Java are actually pointers
- A pointer is a **link** to some object (a piece of memory)
- Links can be thought of as arrows, addresses or references. 
- They point at an object that is somewhere in the systems memory. 

#### Pointers are Links

- When you create and assign objects, the system allocates memory and assigns addresses. 
	- `Foo p;` `p = null`
	- 
- Creating a new object in a variables stores a memory address
	- `Foo p = new Foo();` `p =  E1E42FB
	`
- Can have multiple references to same object
	- `Foo q = p;` `q = E1E42FB`

#### Singly Linked Lists

- Singly linked lists use pointer as links to the next element in the list
- Linked Lists are made up of **nodes**,
- Each node contains a **value**, and a **pointer** to the next node. 
