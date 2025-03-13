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

In more detail, stating a loop invariant means we have to establish that property before the loop starts. 