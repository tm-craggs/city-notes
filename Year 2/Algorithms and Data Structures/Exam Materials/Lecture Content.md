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


# Lecture 3

# Lecture 4

# Lecture 5

# Lecture 6

# Lecture 7

# Lecture 8

# Lecture 9

# Lecture 10

