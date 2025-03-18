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

- The straightforward algorithm for the subset sum problem is similar. 
- Try each selection and choose the largest one that fits.

![[Pasted image 20250318123348.png]]

- For three items, the number of selections to check is 2x2x2 = 2<sup>3</sup> = 8
- In general, for n items the number is selections to check is 2<sup>n</sup>

##### Powers of two

- The cost functions of the satisifibility tester and the subset sum algorithm are powers of two, which increase very steeply. 
- These algorithms do not scale well. 

![[Pasted image 20250318123609.png]]

## Big-O notation revisited

- We have discussed big o for polynomial functions, however for other cost function, a more generalised distinction is needed. 
- Consider the function 3n<sup>2</sup> + 27n<sup>2</sup> + 10n + 52
- When we say this is O(n<sup>3</sup>), we mean it grows no faster than n<sup>3</sup> 
- To compare the rates of growth of these two functions, we can plot their ratio. f(n)/n<sup>3</sup>
- We can see that for large n, the ratio between the two functions has an upper bound. 

![[Pasted image 20250318124745.png]]

##### Formal Definition of big-O notation

- A function f(n) belongs to the complexity class O(g(n)) if there is a size N and a constant c such that 
	- For all n > N, f(n) <= c g(n)
- There are two constant, both of which can be as big as we like.
	- N, which means only the behaviour for large n matters
	- c, which means that we ignore constant factors. 
- A consequence of this definition is that if a function is O(n<sup>2</sup>) then it is also O(n<sup>3</sup>), O(n<sup>4</sup>) etc...
- However, we generally prefer the tightest class. 


##### Exponential Growth

- The graph compares the rate of growth of 2<sup>n</sup> with that of n<sup>3</sup> 