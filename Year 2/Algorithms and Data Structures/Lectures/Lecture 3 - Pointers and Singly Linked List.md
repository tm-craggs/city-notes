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

```java
public class Node {
	public int info   // stores the number at this location in the array
	public Node next; // stores the memory address of the next node	
}
```

- In arrays, you know when you are at the end when you are at the index of the array size.
- In linked lists, you know you are at the end of the array when there is a null pointer. 

#### Adding elements

- You can manipulate the list by changing the address held in `next` for a node. 

**Adding at the head**

**Adding at the tail**

**Pointers to the head and tail**

```java
public class SLList {

	private Node head = null;
	private Node tail = null;
	
	public boolean isEmpty(){
	
		return head == null
	
	}
	
	public void addToHead(int el){...}
	public void addToTail(int el){...}
	public void deleteFromHead(){...}

}
```


###### What Shouldn't happen in Linked Lists?

- Loops
- Errors with pointers (tail does not correctly point to next)
- Tail node with non-null pointer to next
- Non-tail node with null pointer to next

**Operations in Linked Lists**

- Adding an element at head
- Adding an element at tail
- Deleting the head element
- Deleting the tail element

**Adding**

```java
public void addToHead(int el) {

	head = new Node (el, head);
	if (tail == null){
		tail = head;
	}

}
```

```java
public void addToTail(int el) {

	if (!isEmpty()){
		tail.next = new Node(el);
		tail = tail.next;
	} else {
		head = tail = new Node(el);
	}

}
```

**Deleting**

```java
public void deleteFromHead() {

	// this will move the head pointer one forward
	
	int el = head.info; 
	if (head == tail) {  // one or no elements
		head = tail = null;
	} else {
		head = head.next;
	}
	
	return el;

}
```

```

```

**Note:**  We are not deleting this object, just moving where the list starts/ends. If using a language without garbage collection, remember to delete the class which is now no longer a part of the list. 