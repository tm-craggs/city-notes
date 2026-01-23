# Lecture 1

Types of time complexity

**Good**
Constant: O(1)
Logarithmic: O(log n)
Linear: O(n)

**Acceptable (Sometimes)**
Quadratic: O(n<sup>2</sup>)
Cubic: O(n<sup>3</sup>)
Polynomial: O(n<sup>k</sup>)

**Intractable**
Exponential: O(a<sup>n</sup>)
Factorial O(n!)

Divide and Conquer, if the input is not simple, the input should be divided into simpler components and applied recursively to each part, then recombined. 

Recursion
Pros:
- Elegant
- Compact
- Easy to prove
Cons:
- Careful design needed
- Hard to debug
- Function call stack needs extra memory

The space complexity of a recursive algorithm is O(d), where d is the maximum depth of the stack. 

**Stack**

A FIFO structure with add, remove, and check if empty operations. 

```java
// implements stack to fill abstract methods
public class ArrayStack implements Stack {
	private int[] a;
	private int count = 0;
	public ArrayStack(int size) {a = new int[size];}
	public boolean isEmpty() { return count == 0; }
	public void push(int elt) { a[count++] = elt; }
	public int pop() { return a[--count]; }
}
```

# Lecture 2

**Priority Queues**

Principle: You can only remove the element with the highest priority
Operations: Add, Remove (highest priority), check if empty

```java
public class ArrayPQ implements PriorityQueue {
	private int[] data;
	private int count = 0;
	public ArrayPQ(int size){ data = new int[size]; }
	public boolean isEmpty(){ return count == 0; }
	public void add(int elt){
		insert(data, count++, elt);
	}
	public int extractMax(){ return data[--count]; }
}
```

The time complexity of Priority Queues is not great, it is improved using Trees, as the extractMax or add will take O(n) depending on if the queue is ordered or not. 

**Trees**

Quick Summary: 
- Trees are data structures that have a root, node, branches, and leaves. 
- Every node apart from the root node is at the end of a branch. 
- Branches proceed from nodes
- Nodes without branches are called "leaves"
- The root has no parents, leaves have no children

Binary Tree - each node has at most 2 children
Perfectly Balanced Tree - binary tree whose least deep leaf is no more than one level apart from the deepest leaf. 

Using heaps, a kind of tree, we can achieve O(log n) for both add and extract max. 

**Heaps**

A heap is a perfectly balanced binary tree such that
- No node is larger than its parent
- All items on the lowest level are as far to the left as possible. 

Heap operations
- Heap is empty if root is empty
- Heap insertion: add a node to the heap, displacing other nodes as necessary so it remains a heap. 
- Heap extraction, remove the node with the highest value (the root), moving the other values so it remains a heap. 

Heap Insertion
- Add the new node as a leaf
- Sift the new node up to its correct position (worst case O(log n) levels)

![[image-125.png|341x218]]

Heap Extraction
- Extract root, and place the last leaf in root position
- Re-establish heap conditions

![[image-126.png|326x237]]


Heaps can be represented as arrays
![[image-127.png|407x218]]

- The parent of node n is node (n - 1) / 2 
	- Integer division, remove decimal place
- The left child of node n is node 2n + 1
- The right child of node n is node 2n + 2

**Heap Sort**
- Add elements to the heap, extract from the heap

```java
void heapsort(int[] data) {
\\ first phase: heap goes from data[i+1] to data[data.length-1]. The rest of data[] is unsorted
for (int i = data.length/2 - 1; i>= 0; i--) {
	moveDown(data, i, data.length-1);
	}
\\ second phase: heap goes from data[0] to data[i] the rest contains the largest elements, sorted

for (int i = data.length - 1; i>= 1; i--) {
	swap(data, 0, i);
	moveDown(data, 0, i-1);
	}
}
```
# Lecture 3

In Java, variables do not contain classes, they contain references to memory of where they are stored.
- Every variable can store null
- Several variables may refer to the same object

Singly Linked Lists

Each node contains a value and a pointer to the next node. To add to the head, create a new node and point it to the current first node. Then update the pointer stored in the list that points to the head. 

To delete from the head, just move the pointer along one space and garbage collection will do its thing. 

Adding and deleting from the tail require traversing the entire list until finding a node that points to null (last node)

Use a doubly linked list if adding to the tail is needed functionality. 

# Lecture 4

Other types of Linked List are doubly linked lists, which store a pointer to the tail. Making operations at the tail achievable in O(1) for slightly more space complexity. 

Circular linked lists are where the tail node points back to the head. Only store the pointer to head or tail so you can tell when a full traversal has been completed. 
# Lecture 5

Sets in maths are a collection of things, no matter the order. Sets are the simplest case of a table, where the key is the value. 

Hash Tables provide O(1) time complexity for search, insert and delete operations bu calculating array indices directly from keys, by using a hash function. 

index = hash(key)

A good hash function
- Distributes keys uniformly across the array
- Uses prime numbers for modulo operations to avoid patterns
- Minimise collisions

Collision Handling, there are two main strategies

Chaining / Closed Hashing
- Each array slot contains a linked list. 
- Colliding elements are stored together
- Performance depends on load factor (elements / table size)
- Search time: O(1) average if load factor is bounded

Open Addressing
- Store all elements in the array itself using probing sequences.
- Linear probing: Try next slow, simple but causes clustering. 
- Try h(k), h(k)+1², h(k)+2², h(k)+3² - reduces primary clustering
- Double Hashing - use a second hash function for probe offset. Removes primary and secondary clustering. 

# Lecture 6

Trees are hierarchical structures with nodes connected by branches. Can represent organisational structures, file systems, and more. 

- Root: Top node with no parent
- Leaves: Nodes with no children
- Height: Longest path from root to leaf (in edges)
- Depth: Distance from a node to root
- Level: Depth + 1

Trees naturally support recursion. Two types of traversal, BFS and DFS. More in cheat sheet. 
# Lecture 7

Binary search tree, BST. 
- All keys in left subtree < node key
- All keys in right subtree > node keys
- No duplicate keys

In order traversal of a binary tree produces a sorted sequence.

BST Operations, all log(n) average O(n) worst. 

Search
- Compare key with current node
- Go left if smaller, right if larger

Insert
- Search for the key
- If not found, add new node at empty position. 

Delete
- No children, remove node
- One child, replace node with child
- Two children, replace with sucessor (left) or predeccesor, then delete. 

# Lecture 8

# Lecture 9



