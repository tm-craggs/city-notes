- So far, we have only considered complexity functions O(1), O(n), O(n<sup>2</sup>), in general only O(n<sup>k</sup>)
- This session will look at other function that charactize other common agorithms. 

- **Exponential Time** - Very bad, typically found in algorithms that perform an exhaustive search. 
- **Logarithmic Time** - Very good, typically achieved by algorithms that cut the size of the problem each step. 

## Exponential Time

- Many algorithms operate by considering all possibilities in a set, this is called **exhaustive search**
- This is often very expensive. 

##### Satisfiability Checking

- The satisfiability checking problem is to determine weather, given a formula, there is an assignment of truth values to the variables that make it true. 
- Consider the following
	- p AND NOT p
	- (p OR q) AND NOT p
	- NOT p and ((NOT q OR v) -> p)
	- And so on...
- A method for determining whether or not a formula is satisfiable using truth tables:
	- Generate all rows of the truth table for f
	- If any row gives true, then f is satisfiable, else f is not satisfiable
- The input to the algorithm is the formula f, a measure of size is the number of distinct variables.
	- If there is only one variable, we must test 2 rows
	- If there are two variables, we must test 2x2 = 4 rows
	- If there are three variables, we must test 2x2x2 = 8 rows. 
	- For n variables, 2<sup>n</sup> rows. 

##### Subset Sum Algorithm

- The straightforward algorithm for the subset sum problem 