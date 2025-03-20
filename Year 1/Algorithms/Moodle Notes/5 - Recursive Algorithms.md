
- One strategy for solving problems is
	- If the problem is too big to solve directly, reduce it to smaller problems of the same type. 
	- Apply the same procedure to those.
- That is, the algorithm calls itself, it is recursive.
- This is used in fast sorting algorithms, but first we will review methods.

## Understanding Method Calls

- We'll begin with another look at methods, which were covered in Java week 3. 

##### Tracing Method Calls

- Consider the following simple algorithms
	- Square(x)`RETURN x*x;`
	- Cube(x)`y = Square(x); RETURN y*x;
	- FourthPower(x) `y = Cube(x); RETURN y*x`
- We can trace the execution of fourth power, using indentation to show method calls

```
FourthPower(2)
	call Cube(2)
		call Square(2)
			return 4
		y = 4
		return 8
	y = 8
return 16
```

##### Implementation of methods: The Stack

```Java

public static void main(String[] args){
	int a = 3;
	f(a+1);
	a = g(7);
	System.out.println(a);
}

public static void f(int x){
	System.out.printlb(x);
	int y = g(x + 5);
	System.out.println(y*2);
}

public static int g (int v){
	System.out.println(v)
	return v*7 - 8;
}

```

- In the above Java program, `main()` calls a method `f()` which calls a method `g()`
- During the execution of a method, the runtime system stores
	- The values of the parameters passed to the method. 
	- The return address: the location in the program from which the method was called, and which control will be passed back to when the method returns. 
	- Any local variables defined within the method
	- Possible other housekeeping information
- This bundle is called an **activation record** or **stack frame**
- There will be one of these for each active method
- They are held on the stack, which grows and shrinks during the execution of the program. 
- When a method is called, a new activation record is added to the stack. 
- When the method returns, its activation record is discarded, so the stack will shrink. 

![[Pasted image 20250320161422.png]]

- The shown stack is expanding downwards. 
- Note: Objects created with `new` are stored in a different area, the heap. 

## Recursion

- Recursive algorithms use the general strategy of solving large problems by reducing them to smaller ones, and then using the same method on those.

##### Example: Counting Powers

- We want to compute the function x<sup>k</sup> = x * ... * x. Where k x's are multiplied together. 
- A simple method relies on these two equations
	- x<sup>0</sup> = 1
	- x<sup>k</sup> = x * x<sup>k - 1</sup>, if k > 0
- We can translate this into a simple recursive algorithm

Power(x, k)
```
IF k <= 0
	RETURN 1
ELSE 
	y = Power(x, k-1)
	RETURN x * y
```

Here is a trace of Power(2, 5)

```
Power(2,5)
	call Power(2,4)
		call Power (2, 3)
			call Power(2, 2)
				call Power (2, 1)
					call Power(2, 0)
						return 1
					return 2*1 = 2
				return 2*2 = 4
			return 2*4 = 8
		return 2*8 = 15
	return 2*16 = 32
```

##### Analysis

- We shall use exponent k as the parameter, and count multiplication as our basic steps 