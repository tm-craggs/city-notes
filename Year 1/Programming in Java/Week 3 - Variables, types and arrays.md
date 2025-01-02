**What is Java?**
- A computer platform for executing bytecode
- The java compiler reads file with .java extension, checks syntax and creates a .class file which can run independently from any machine
- JVM translates bytecode into instructions 

**Variables**
- To use a variable declare its type and name

**Primitive Data Types** 
- byte - 8 bit signed two's compliment binary value
- short - 16 bit signed two's compliment binary value
- int - By default int is a signed 32 bit binary value, but can also be unsigned if changed
- long - By default, is a 32 bit binary value, but can also be unsigned
- float - 32 bit floating point binary value
- double - 64 bit floating point binary value, more accurate than float
- boolean - true/false
- char - single 16 bit Unicode character

String is not a primitive data type, as it is a class. However, its support is so good that it is often thought as one. 

**Default Values**

- When a variable is declared without a value, it is given a default value by the compiler. However, only when it is being declared in a field. Local vars never have a default value, and using one that does not have a value will give a compiler error. 

**Literals**

- The new keyword is not used when declaring primitive data types.
- Primitive types are special as they are built into the language, they are not created from a class
- A literal is the source code representation of a fixed value, literals are represented in your code without requiring computation.
- It is possible to assign a literal to a variable of a primitive type.

**Integer Literals**

- Usually you will use regular decimal, but if you need to use other number systems they should be defined as follows
- int hexVal = 0x1a;
- int binVal = 0b11010

**Floating-Point Literals**

- A floating point value is of type float if it ends with the letter f, otherwise it is a double, and can optionally end with d

**Character and String Literals**

- Literals of char and String may contain any unicode characters
- Always use single quotes for char literals and double quotes for String literals

Null may be used as a literal for any datatype

**Using underscore characters in Numeric Literals**

- You can place any number of underscores between digits in a numeric literal. 
- This can help improve the readability of your code, for example, by separating groups of 4 digits. 
- An underscore cannot be used in the following positions
	- At the beginning or end of a number
	- Adjacent to a decimal point
	- Prior to an F or L suffix
	- In positions where a string of digits is detected.


**Operators**

- = assignment operator, assigns a value
- + additive operator, also used for string concatenation
- * multiplication operator
- / division operator
- % remainder operator

**Unary Operators**

- Only require one operand
- + unary positive operator, indicates positive value
- - unary minus operator, negates an expression
- ++ increment operator
- -- decrement operator
- ! logical compliment, inverts a bool

**Equality and relational operators**

- Used for if conditionals
- == equal to
- != not equal to 
- > greater than
- < less than
- >= greater than or equal to

**Conditional Operators**

- Performed between two boolean expressions
- && conditional and
- || conditional or

**The ternary operator**

- ? can be thought of as a shorthand if/else statement
- It uses 3 operands. If a condition is true, assign value one, else assign value 2
- result = someCondition ? value1 : value2

**Arrays**
- Fixed container that holds a fixed number of values of a single type
- Length of the array is established when it is created

**Declaring an Array**
- Has type and name
- The brackets [] are a special symbol that the value holds an array
- This does not create an array, but tells the compiler that this var will hold an array of the specified type. 
- You do not need to declare the size if declaring the array straight away on the same line. It will be inferred. 

**Accessing an Array**
- Arrays use 0 indexing, the first item is 0
- The length of the array is the number of values in it. 

**Copying Arrays**
- The System class has an arraycopy method that you can use to copy an array into another. 
- Declare an empty new array of the same type, then use the function to assign value.

**Array Manipulation**
- Java has many inbuilt functions held in java.util.Arrays such as
	- Searching
	- Equivalence checks
	- Sorting
	- Filling a specific value


Testing commits