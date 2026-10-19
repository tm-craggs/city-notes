
### Contents

- Alphabets and strings
- Languages and machines
- Deterministic FSA and transition diagrams 
- Non-deterministic FSA
- Comparing DFSA and NFSA

### Alphabets

Alphabet - A finite set of symbols/characters used for encoding, often represented with the symbol $\Sigma$

Examples:
$\Sigma$ = {0, 1}
$\Sigma$ = {a,b c}
$\Sigma$ = All characters in the Roman alphabet


### Strings

A string `w` over an alphabet $\Sigma$  is a finite sequence of symbols in $\Sigma$

Examples over alphabet $\Sigma$ = {a,b}

- a
- b
- abb
- baababa
- $\varepsilon$ (empty string)

### Languages and Machines

Language - A set of strings

A language `L` over an alphabet $\Sigma$ is a set of strings over $\Sigma$ . L is a subset of $\Sigma$*

Machines - Compute by accepting **all** the strings in some language, and rejecting **all** others. 

There is an equivalence between language and machine. They both only accept words if it is part of the language. 

**Example:** Machine `M` for a language `L`

Given an input string `w`, machines `M` scans `w` from left to right, processing one symbol in each step. 

Reading the string `w`, `M` should either accept or reject `w`, depending on whether or not `w` is in `L`

### Languages and Problems 

**Example 1:**

L = `{<G> | G is a connected graph}`

`<G>` is an encoding of graph G as a string over an appropriate alphabet

<G<sub>A</sub>> = (1,2,3,4)((1,2)(1,3)(2,3))

![[image-178.png|170]]

<G<sub>B</sub>> = (1,2,3,4)((1,2)(1,3)(2,3)(2,4))

![[image-179.png|169]]

Decision Problem: Given `<G>`, is `G` in `L`?

**Example 2**

The set of all words of the form: a<sup>m</sup>b<sup>n</sup>c<sup>m+n</sup>, where:
- m, n range over the number 0, 1, 2...
- x<sup>n</sup> denotes the string containing n successive copies of the symbol x


That is: {a<sup>m</sup>b<sup>n</sup>c<sup>m+n</sup> | m,n >= 0} and alphabet $\Sigma$ = {a,b,c}

Here are some valid words in this language
- aaabbccccc
- aabbcccc
- ac

Here are some words that have the same alphabet but are **not** in the language:
- aabbcc
- abccc
- bbaccc

This language can be said to represent addition. the number of As, added with the number of Bs, should be equal to the number of Cs

**Example 3:**
Subtraction can be represented with {a<sup>m</sup>b<sup>n</sup>c<sup>m+n</sup> | m >= n >= 0}

Any machine that accepts only words in language 2, and rejects all others, could be described as an addition **accepetor**


