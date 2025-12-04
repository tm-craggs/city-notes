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
- Nodes at the end of a branch are "children" of the node above "parent"
- The root has no parents
- The leaves are nodes with no children


A **binary tree** is a tree which has, at most, two children. 

A **perfectly balanced** binary tree is a tree whose least deep lead is no more than one level apart from the deepest one. 

Using **heaps**, we can distribute and reduce the load, achieving O(log n) time for both add, and extract. 

A **heap** is a perfectly balanced tree such that:
- No node is larger than its parent
- All items on the lowest level are as far to the left as possible. 

**Heap Operations**

- If a heap is empty, the root is empty. 
- Heap insertion, add a node to the heap, displacing other nodes as necessary so that the heap remains a heap. 
- Heap extraction, remove the element with the highest value in the heap (the root), moving the other nodes as necessary so that the heap remains a heap. 

**Heap Insertion**

- Add the new node as a leaf
- Sift the new node up to its correct position, which has at most O(log n) swaps, as the tree has log n levels. 

**Heap Extraction**

- Extract the root, and place the last leaf in the root position
- Re-establish the heap conditions

