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

- The graph compares the rate of growth of 2<sup>n</sup> with that of n<sup>3</sup>, by plotting 2<sup>n</sup>/n<sup>3</sup>
- For small values of n, 2<sup>n</sup> <= n<sup>3</sup>
- This means that the function 2<sup>n</sup> is not O(n)


##### Operations on order functions

- Order notation simplifies calculations
- One common operations arises when an algorithm does one thing after another. 
- We want to add the costs of both parts
- For example:
	- **Property** - If f<sub>1</sub>(n) and f<sub>2</sub>(n) are both O(g(n)) then f<sub>1</sub>(n) + f<sub>2</sub>(n) is also O(g(n))
	- **Proof** - Definition shows that there are constants N<sub>1</sub> ,N<sub>2</sub>, <sub>c<sub>1</sub></sub> and c<sub>2</sub> such that
		- For all n > N<sub>1</sub>, f<sub>1</sub>(n)/g(n) <= c<sub>1</sub> and
		- For all n > N<sub>2</sub>, f<sub>2</sub>(n)/g(n) <= c<sub>2</sub>
	- If N is the larger of N<sub>1</sub> and N<sub>2</sub> then
		-  For all n > N, (f<sub>1</sub>(n) + f<sub>2</sub>(n))/g(n) ≤ c<sub>1</sub> + c<sup>2</sup>
		- i.e. f<sub>1</sub>(n) + f<sub>2</sub>(n) is also O(g(n))
	- 4 n3 + 6 n3 is O(n3), because both functions are O(n3).
	- 3 n20 + 2n is O(2n), because both functions are O(2n). The faster-growing 2n dominates n20
- We can use this to work out the complexity of methods from their parts.
	- If a method performs an operation taking O(n<sup>2</sup>) time, followed by another taking the same time, the whole thing takes O(2<sup>n</sup>) time
	- If a method performs an operation taking O(n<sup>3</sup>) time, followed by another operation taking O(2<sup>n</sup>) time, the whole thing takes O(2<sup>n</sup>) time. 



## Searching an Array

- We looked at sequential search in week 3, which takes O(n) time. 

##### Binary Search

- Binary Search is logarithmic time, O(log n)
- If the array in arranged in order, we can do much better than linear search. 
- We compare the middle value (mid) with the key value (k)
	- If mid = k, then we are done
	- If mid < k, we only need to search mid+1 ... n-1
	- If mid > k, we only need to search 0 ... mid - 1
- Repeating this process will halve the searching array each time. 
- We need two variables, low and high, to track the search area.
- If the key is not in the array, they will eventually cross. 


```
BinarySearch(a[0..n-1], k)

low = 0
high = n-1

WHILE low <= high
	mid = (low + high) / 2
	
	IF a[mid] = k
		RETURN mid
	ELSE IF a[mid] < k
		LOW = mid + 1
	ELSE
		high = mid - 1

RETURN -1
```


##### Analysis of Binary Search

- The loop has 2 control variables, low and high. 
- The fundamental step is examination of an element of the array, which is the same as an iteration of the loop. 
- On each iteration of the loop, we halve halve high-low+2 until it reaches 1


##### Reminder: Logarithms

- The logarithm of a number is the exponent to which another fixed value, the base, must be raised to produce that number. 
- We shall assume the base is 2. 
	- For example, log(32), the logarithm of 32 to base 2 is 5, because 32 = 2<sup>5</sup>
	- More generally, if y = 2<sup>x</sup> then x = log(y)
- That is, the logarithm graph is the mirror image of the exponential graph about the diagonal
- Logarithmic complexity is as good, and exponential complexity is bad
- O(log n) grows much more slowly than O(n)

## Complexity Classes

 **O(log n) (Logarithmic Time)**
 - The amount of time grows logarithmically (good)
 - This is typical of algorithm that repeatedly cut the size of the problem by some fraction (binary search)

**O(n log n) (Log-linear)**
- Fast sorting algorithms (week 7)
- 