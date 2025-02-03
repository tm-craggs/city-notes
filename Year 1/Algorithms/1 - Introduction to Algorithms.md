
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

# Tracing an Iterative Algorithm

- An iterative algorithm is a block of code that repeats until a condition is met. 