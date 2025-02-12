
Assessment Structure

**Algorithms**

- There are many broadly similar definitions of an algorithm
- Informally, an algorithm is any well-defined computational procedure that takes some value, or set of values and produces a value, or set of values as an output. 
- An algorithm is thus a sequence of computational steps that transform the input into the output. 

**Pseudocode**

- Pseudocode is a plain text algorithm
- It is often ambiguous
- It is not a language that is understood by computers, it is a code-like language that is very understandable to humans, used to describe algorithms or plan code.
- It's rule set is rough and flexible. 
- Pseudocode:
	- Abstracts away from specific programming languages
	- Describes sequential computations, with assignment, conditionals loops, and function calls. 
	- It's syntax is far less verbose than typical programming languages, for easier comprehension. 
	- Typically indicates structure using indentation (rather than curly brackets)
	- Left arrow for assignment <-
	- Avoids many of the finer details of a programming language
	- May include pieces of English text
	- No fixed notation. 

Example: This code loops through array a, and adds all the values. 

Algorithm Sum (a|0..n-1)

total <- 0
i <- 0
WHILE i < n
	total <- total + a[i]
	i <- i + 1
RETURN total

To write this in Java, you would need to declare data types and have the function inside of a defined class, etc.

# Types of common problem

- Searching - Find an element in a collection or find a sub-sequence with certain properties (find a path through a maze)
- Sorting - Take a collection of things and arrange elements in order. This is very common and is often a component of bigger tasks, such as finding duplicates in a collection. 
	- Selection Sort
	- Insertion Sort
	- Bubble Sort
	- Merge Sort
- Text processing - Find occurrences of a substring, formatting of text. 
- Numerical Operations - Arithmetic on large numbers (factorisation, matrix operations)
- Computational Geometry - Collision detection, mesh generation (in graphics)
- Combinatoric problems - Given 


# Comparing Algorithms

**Complexity Analysis**

**Correctness**
- This is essential. We will use methods used to show that algorithms always produce the desired results. 

**Efficency**
- How much resources do we need? Usually we are concerned with time, but sometimes also space. Is the algorithm fast? Does it make efficient use of memory?

Simplicity
- This is desirable, but not required. 
