Priority Queue Operations

- Add an element
- Remove an element (the one with the highest priority)
- Check if the queue is empty 

A way of implementing priority queues is to keep the elements in a sorted array. 
- To add an element, search and insertion are used
- To extract an element, the last element is extracted

Implementation in Java

```java
public class ArrayPQ implements PriorityQueue { 
	private int[] data;
	private int count = 0;
	
	public ArrayPQ(int size){ data = new int[size]; } 
	public boolean isEmpty(){ return count == 0; } 
	public void add(int elt){ 
		insert(data, count++, elt); 
	} 
	
	public int extractMax(){ return data[--count]; } }
```


We can optimise this using **trees**

- Trees are data structures that have a root, nodes, branches, and leaves
- Most node are at the end of a branch, apart from the root node
- Branches proceed from nodes
- Nodes without branches are called "leaves"
- Nodes at the end 