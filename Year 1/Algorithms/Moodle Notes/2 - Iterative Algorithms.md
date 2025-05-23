There are three tools for expressing algorithms using loops

Loop invariants - For demonstrating partial correctness
Loop control variables - For keeping track of when to exit the loop
Order of Growth ("big O") notation - For measuring complexity, mainly worse case time

## Correctness

The first step is to distinguish between 2 types of correctness

**Total Correctness** - For all inputs, the algorithm produces the desired outputs. This is what we want, but it can be hard to establish in one go, so we aim for something easier. 

**Partial Correctness** - If the algorithm terminates, it produces the desired result. 

As an extreme example, an algorithm that loops forecer is a partially correct solution for any problem. 

However, separating the two simplifies the problem. Partial correctness is easier to proce, and the time analysis will imply termination. 

**Total correctness = partial correctness + termination**
**Worst-case time analysis -> termination**

## Loop invariants

**Loop invariant** - A property that holds before and after each execution of the loop. Example: Each time the execution reaches the WHILE line. 

For example, take a simple algorithm to find the largest item in an array. It is useful to identify a key property of the loop. In this case, a property that holds for each row of the table at right, we add it to our description of the algorithm. 


``` Pseudocode
max = a[0]
i = 1

// Invariant: i <= i <= n and max is largest of a[0] ... a [i-1]
WHILE i < n
	IF a[i] > max
		max = a[i]
	i = i + 1
	
RETURN max
```

The loop invariant is not executed, it is a comment. 

In more detail, stating a loop invariant means we have to establish that property before the loop starts and at the end of the body, but it also gives us properties that hold and the start of the loop body and the end of the loop. 


```Pseudocode
max = a[0]
i = 1

// Establish invariant: i <= i <= n and max is largest of a[0] ... a [i-1]
WHILE i < n
	// we have: 1 <= n < n and max is largest of a[0] ... a[i-1]
	IF a[i] > max
		max = a[i]
	i = i + 1
	// establish: 1 < i <= n and max is largest of a[0] ... a[i-1]

we have: 1 < i <= n and max is largest of a[0] ... a[i-1]

RETURN max
```

In general:

```
establish: invariant

WHILE condition:
	we have: invariant AND condition
	loop body
	establish: invariant

we have: invariant AND NOT condition

```

- This variable i in this algorithm is a **loop control variable**
- **Loop Control Variable**
	- Initialised before the loop starts
	- Used in the test whether to continue looping
	- Modified in the body of the loop

# Nested loops

- Consider the problem of testing if all the elements of an array are different, we'll need to go through all the elements. For each element we'll need to go through the others and check they're different to this one. This will require 2 loops, one inside of the other. 
- We place an invariant on each loop. 


```

i = 1
diff = true

// invariant: 0 ≤ i ≤ n and diff ≡ a[0] ... a[i-1] all different
WHILE i < n
	j = 0
	// invariant:0 ≤ i ≤ n and diff ≡ a[0] ... a[i-1] all different AND a[i] different from a[0] ... a[j-1]
	WHILE j < i
		IF a[j] = a[i]
			diff = false
		j = j + 1
	i = i + 1
RETURN DIFF

```


This algorithm has 2 loop control variables, keeping these separate makes it easier to work out when the loops will terminate

Good practise for clear code:
- Do not modify a loop control variable in an inner loop. 
- Modify the loop control variable in as few places as possible. 
- Many languages support this special case directly, e.g. in languages of the C family (including C++, Java and C#), this is written `for (i = A; i < B; i++) ...`

# Analysing Algorithms

- We want to measure the number of steps taken by the algorithm, usually in the worst case. 
- We need to consider:
	- How to measure the size of the input to the algorithm. 
	- What a fundamental step for the algorithm is
	- What input gives the most number of steps (worst case)
- Then we want to compare the rates of growth of different functions.

**Input size**
- The input size is usually straightforward to decide upon, simply by working out what aspect of the input is used in the algorithm. For example:
	- An array of n elements has size n (in an algorithm where the fundamental steps involve elements of a list)
	- The size of a graph might be the number of nodes or edges or both
	- The size of a logical formula might be the number of variables, or the number of connectives. 

**Counting steps**
- To work out the number of steps an algorithm may take (given an input size of n)
	- Identify the fundamental step of the algorithm
	- Set up a mathematical formula describing the number of times this step occurs, this should depend on (if anything) the size of the input. 
	- Manipulate this to establish a succinct description of the number of steps. 

**Comparing cost functions**
- If we have reduced the costs of two algorithms to cost functions f(n) and g(n), we wish to compare these. 
- Smaller cost is better, but we are most concerend with the costs for large input sizes.
- In the below graph, we can see n<sup>2</sup> eventually overtakes c<sup>*</sup>n for any constant c. We say that n<sup>2</sup> **dominates** c<sup>*</sup>n. Similarly, n<sup>3</sup> **dominates** c<sup>*</sup>n<sup>2</sup> and so on.

![[Pasted image 20250313153749.png]]

**Order-of-growth notation**
- We take a simplified view of a cost function, restricting our attention to the term that grows fastest for large inputs, and ignoring constant factors. 
- Thus, we might say the worst-case-complexity of an algorithm is O(n<sup>2</sup>), meaning that for large inputs, its cost function f(n) grows no faster than n<sup>2</sup>
- For polynomial functions, the complexity class is quite easy to work out. 
	- 1, 23, and 1000 are all O(1)
	- 5n + 4 is O(n)
	- 20n<sup>2</sup> + 56n + 478 is O(n<sup>2</sup>)
	- And so on 

**Examples:**

Select a random element:
```
i = random number between 0 and n-1
RETURN a[i]
```

- This algorithm has input size n, the length of the array
- The basic step is an array lookup
- The number of steps taken by this algorithm is always 1
- Therefore, it is constant time, O(1)

Analysis of sequential search

```
i = 0
WHILE i < n AND a[i] != x
	i = i + 1
RETURN i
```

- For the input size, we use the size of the array n. 
- The steps counted are the comparisions of the array elements with x. 
- The number of steps executed by the algorithm varies for inputs of the same length
	- The worst case occurs when x is not in the array, the algorithm compares it with every item in the array. n steps. 
	- The best case is when x occurs as as the first element of the array, so only one comparison is needed. 
	- If the first x occurs at a random position in the array, the algorithm takes between 1 and n steps, with an average of (n+1/2)
- The worst case time complexity is O(n), linear time
- The average case time when the value is present is also O(n)

Analysis of all different


```
i = 1
diff = true
WHILE i < n
	j = 0
	WHILE j < i
		IF a[j] = a[i]
			diff = false
		j = j + 1
	i = i + 1
RETURN diff
```

- Again, we use the size n of the array as input size. 
- This algorithm compares each of the n elements with the n-1 other elements, but it only compares each pair once, so it requires n(n-1)/2 comparisons, that is n<sup>2</sup>/2 - n/2
- This is O(n<sup>2<sup></sup></sup>), quadratic time. 
- Algorithms that have a single nested loop are usually O(n<sup>2</sup>)

# Complexity Classes

We classify algorithms according to the order of their cost function

**O(1) - Constant Time**
- Algorithm always takes the same amount of time. 
- Occurs only in rare cases of good fortune (first element)

**O(n) - Linear Time**
- Time taken grows in direct proportion to input size. (good)
- Typically for problems requiring a limited number of passes over the input. (sequential search)
- Any algorithm that examines all its input must take at least linear time

**O(n<sup>2</sup>) - Quadratic Time**
- The time taken grows in proportion to the square of the input size (ok)
- This often occurs with algorithms involving two nested loops. (bubble sort)

**O(n<sup>3</sup>) - Cubic Time**
- The time taken grows in proportion of the cube of the input size (bad)
- This often occurs in algorithms with three nested loops

**O(n<sup>k</sup>) - Polynomial Time**
- This is the limit of what is usually considered feasible. 
- Although it can be very expensive for larger k. 
- Some algorithms and problems are even worse. 

There are more categories such as Logarithmic time. 