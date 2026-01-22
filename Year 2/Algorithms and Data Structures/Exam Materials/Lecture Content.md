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

# Lecture 3

# Lecture 4

# Lecture 5

# Lecture 6

# Lecture 7

# Lecture 8

# Lecture 9

# Lecture 10

