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
- One method for determining whether or not a formula 