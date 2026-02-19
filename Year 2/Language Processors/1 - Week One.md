What the course is about

- Programming languages is about programming languages as order of study
- This course is about grammars, parsers, interpreters, compilers
- We will be using Java to implement a compiler 

Key Words
- Grammar - Defining the syntax of a language
- Parser - A program which checks the syntax of source code and builds its abstract syntax tree
- Interpreter - A program that executes other programs
- Virtual Machine - A program that executes low level code (interpreter)
- Compiler - A program that translates programs written in a high-level language into low-level code

- The JVM is a program which executes java byte code
- More generally, a VM is an interpreter for a low level language
- We will be implementing a small high-level language (LPL26) by compiling to Simple Stack Machine (SSM) code. 
- SSM is a small virtual machine, similar to the JVM

What does a compiler do

- Start with the high level source code
- Basically, code is just a stream of characters
- The compilers input is the character stream
- Then, it cuts it up into chunks (tokens)
	-  For example, it will notice the keywords and
	-  This stage is carried out by the lexical analyser 
- The parser then checks that the sequence of tokens is a valid Java program, and will build an Abstract Syntax tree. 
- Then the compiler undertakes static analysis, it involves a lot of checking data types
- After this, we have a symbol table. 
	-  It is a record about the types of names you have used, variable names, method names, etc.
	- The table will store everything it knows about these names
- Finally, the code is generated. 

High level languages have features like if statements, while loops and methods. Machine languages have few, if any of these. 
- SSM has none
- There is no general formula for translating high level language features into machine code, so we have to invent our own ways in the translation. 


- SSM primarily uses a stack, for example when doing an addition, you will add both numbers onto the operand stack, and then pop using the add operation. 


Example:

Let's execute this program

```SSM
push 6
push 7
mul
push 9
add
sysc 3
halt
```

1. `push 6` puts 6 inside the operand stack
2. `push 7` does the same
3. `mul` multiplies them together, 6 and 7 **come off** the operand stack and are replaced by 42
4. `push 9` puts 9 on-top of the 42 that is on the stack
5.  `add` means that the 9, and 42, are removed from the stack. 51 replaces them
6. `sysc 3` is a system call, it takes the value from the operand stack and prints it to standard output. 51 is taken off the stack. 
  