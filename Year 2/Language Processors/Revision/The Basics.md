
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

## Grammar Rules

Once you have tokens, you need rules to describe how they fit together to make programs. This is what **non-terminals** are used for. 

Think of non-terminals like abstract concepts, or a logical structure. They aren't actually a symbol in any kind of input, things like "expressions", "statement" or "program" are non-terminals. They exist only in the grammar. 

You could say that an expression is either just a number, or a number plus another expression, take this example

``