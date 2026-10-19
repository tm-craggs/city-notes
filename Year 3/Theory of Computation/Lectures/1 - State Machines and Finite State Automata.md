
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

Any machine that accepts only words in language 2, and rejects all others, could be described as an addition **accepetor**

**Example 3:**

Subtraction can be represented with {a<sup>m</sup>b<sup>n</sup>c<sup>m+n</sup> | m >= n >= 0}

**Example 4**

$\Sigma$ = {0, 1}
L = {w | w has an odd number of 1s}
or: {1, 01, 10, 001, 111, 010, etc...}


### Classes of Language and Machine

##### Regular Languages

- Language 4 belongs to the class of **regular languages**
- Language 2 does not
- For every regular language, an acceptor machine can be constructed that belongs to the **class of machines** called **finite state automata** (FSA)
- Note: One automation, many automata

##### Context-free Languages

- No FSA can be designed to accept the languages of addition and subtraction
- They belong to the class of **context-free languages**, a class that includes most programming languages
- To recognise context-free language requires the power of a class of machines called **push-down automata**, which can also recognise regular languages. 

##### Context-sensitive Languages

- The push-down automata are also limited in their **computational power**, meaning the class of languages they can recognise and the class of functions they can compute
- They cannot recognise the **context-sensitive languages**, this requires the power of **Turing Machines**
- This is the most powerful class of machine, no function that cannot be computed by a Turing machine can be computed at all


### Finite state automata (informal)

A FSA, or just finite automation, consists of
- A finite set of states
- A finite set of transitions from state to state, each of which is associated with a symbol from an alphabet

- Transitions tell is, for each state, based on the symbol being processed what the next state should be. 
- One is the initial state, where the automaton starts
- Some (or no) states are designated as accept/final states. 
- After reading the input, if the automaton ends up in an accept states, it accepts the input. 
- Otherwise, if stuck at some point or ending in a state that is not an accept state, it rejects the input. 

### Deterministic finite state automata (formal)

A deterministic Finite State Automaton is a 5-tuple. (Q, $\Sigma$, $\partial$, q<sub>0</sub>, F)