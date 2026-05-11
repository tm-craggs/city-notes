
This is a quick look over the basics of a programming language

**What is a Language?**

A language is simply a set of valid strings. For example, the Java language is the set of all valid Java programs.

The job of the compiler is to figure out if a string belongs to the language, and if so, what it means. 

**Tokens (Terminals)**

A token is the smallest unit of a language, like words in English. For example, the line of code

```
x = 5 + 3
```

A human reads this as five things. `x`, `=`, `5`, `+` and `3`. Each of these are known as a 'token'

The **lexer** is the first stage of the compilation process. It scans the raw characters and groups them into tokens. The line of code above will become

`ID("x) ASSIGN INT(5) PLUS INT(3)`

Tokens can also be called **terminals**, because they are the **final** symbols and cannot be broken down any further. Tokens are defined by regular expressions. 

```
INT: "[0-9]+"
PLUS: "\+"
ASSIGN: "="
ID: "[a-zA-Z]+"
```

To summarise, Tokens represent a piece of text in Regex
## Grammar Rules

Once you have tokens, you need rules to describe how they fit together to make programs. This is what **non-terminals** are used for. 

Think of non-terminals like abstract concepts, or a logical structure. They aren't actually a symbol in any kind of input, things like "expressions", "statement" or "program" are non-terminals. They exist only in the grammar. 

You could say that an expression is either just a number, or a number plus another expression, take this example

```
Expr -> INT
Expr -> INT PLUS Expr
```

The arrow just means consists of. This means that Expr is a non-terminal, INT and PLUS are terminals.

## The Compilation Pipeline

There are multiple stages of the compilation process. 

Stage 1 - Lexing

The lexer reads the raw source code and groups everything into tokens, it'll throw away stuff like whitespace and comments. 

If it catches anything that isn't a token, i.e. not compliant with any defined Regex, it will be a lexical error. 

Stage 2 - Parsing

At this point, the tokens will look like collections of the Regex we defined. For example

```
ID("X") ASSIGN INT(5) PLUS INT(3) SEMIC
```

The parser checks that the tokens follow the grammar rules. It does not check each token 1 by 1 like the Lexer does, it checks how everything fits together. It does this by generating an Abstract Syntax Tree (AST) from the list of tokens. 

For example, the token list:

```
ID("X") ASSIGN ASSIGN INT("3") SEMIC
```

These are all valid tokens, but the structure is not right. You cannot have 2 assign tokens together


Stage 3 - Semantic Analysis

This is where the compiler checks things that are structurally valid, but they are meaningless or wrong. A big part of this is **type checking**, but there is more. Here are some things that can be picked up in semantic analysis. Remember, these can be different per programming language. For example, Java allows variables to be assigned and never used. Go does not. 

**Type Checking**

Makes sure your types are used correctly. 



