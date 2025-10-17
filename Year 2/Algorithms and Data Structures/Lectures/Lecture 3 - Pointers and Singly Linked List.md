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