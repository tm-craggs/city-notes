# Boolean Algebra

- Boolean Algebra is a mathematical system for the manipulation of variables that can have one or two values
- In formal logic these values are "true" and "false" 
- In digital systems these are on or off, 1 and 0 or high or low
- Boolean expressions are created by performing operations on boolean variables
- Common boolean operators include and, or and not

**And & Or**

- A boolean operator can be described using a truth table
- And requires both inputs to be a 1 to return a 1
- Or requires only one
- The and operator is known as a Boolean product
- The or operator is the boolean sum

**Boolean Algebra and Digital Computers**
- Computers contain circuits that implement Boolean functions
- The simpler that we can make a Boolean function, the smaller the circuit
- Simpler circuits are cheaper to build, consume less power, and run faster than complex circuits. 

**The Hardware Hierarchy**
- Silicon -> Transistors -> Logic Gates
- Transistors and logic gates build:
- Computational Circuits
	- The output depends on the combination of inputs at that point
	- Total disregard to the past state of the inputs
	- Examples: functional units such as adders and subtractors
- Sequential Circuits
	- Outputs depend on a combination of both the present inputs as well as the previous outputs
	- Examples: Memory units

**Logic Gates**
- Boolean functions are implemented in digital computer circuits called gates
- A gate is an electronic device that produces a result based on two or more input values
- Gates consist of one to six transistors, but designers think of them as single units
- Integrated circuits contain collections of gates for various purposes
- Transistor: The basic physical component of a computer
- Gate: The basic logic element

**Fundamental Logic Gates**

- NOT - Reverses input
- AND - Both inputs must be true to return true
- NAND (NOT AND) - Anything other than both units being true, returns true
- OR - One or more inputs must be true to return true
- NOR (NOT OR) - Returns true if both inputs are false
- XOR (Exclusive OR) - Only returns true if exactly one input is true. 
- XNOR (Exclusive NOT OR) - Only returns true if both inputs are the same. 

![[Pasted image 20250114165012.png]]


**Truth tables**
- Truth tables describe the relationship between inputs and outputs. 
- For an n input gate, the truth table will have 2^n entries.

**Constructing an AND gate**

- How could an AND gate be built from transistors?
- Transistors are switches that control the flow of electricity
- Transistors are controlled by electrical signals from inputs
- AND gate can be build by using two transistors in sequence

![[Pasted image 20250114165141.png]]

 
**Constructing an OR gate**

- OR gate can built using two switches in parallel
- The output of an OR gate is true if a single value is true, therefore if the output is false, all inputs are false
- OR is an additive operator
- It is written as A OR B, can also be written as A+B

![[Pasted image 20250114171211.png]]

The NOT Gate (Inverter)
- NOT gates have only one input
- It will flip whatever value in entered.
- NOT A can be written as A' or A with a bar

Constructing a NOT gate
- NOT gate can be built using an inverted switch
- This is a switch that is closed when its input is true, and open when input is false

![[Pasted image 20250115163716.png]]

The NAND and NOR gates
- Not logically fundamental (derived from AND, OR and NOT)
	- NAND - NOT AND
	- NOR - NOT OR
- However, they are universal
- This means we can build any logic function with NAND/NOR
- They are widely used in real circuits

![[Pasted image 20250115163941.png]] ![[Pasted image 20250115164001.png]]


# Combined Circuits

Example 1:

- A binary adder can be made out of logic gates.

![[Pasted image 20250115164125.png]]

Example 2:

