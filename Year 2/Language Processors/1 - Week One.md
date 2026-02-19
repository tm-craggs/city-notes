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

High level languages have features like if statements, while loops and methods. Machinene languages have few, if any of these. 
- SSM has none
- There is no general formula for translating low level language features 