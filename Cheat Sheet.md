## Lecture 1

NFSA and DFSA. Make a table  n


## Lecture 2

Regex. Concatenation, union and Kleene star are allowed. Union acts as an or


Kleene theorem - any finite state automata has an equivalent regular language. 

Build regex from FSA by adding a new start and accept state with null transitions and simplifying. Parallel transitions can be represented by doing the union, ones that are a straight route can be concatentated, and kleene stars are loops 

You can do this in reverse too, start with machines that accept the basic language fundamentals and build from there 

## Lecture 3

The pumping Lemma conditions are

1. |y| > 0
2. |xy| `<=` P
3. xy<sup>i</sup>z $\epsilon$ L for all i >= 0


# Lecture 4

Push Down Automata are FSA with a stack (memory) Each operation can read input, push onto the stack, pop off from the stack, or go to another state.

It is considered accepted when all input is empty, the stack is empty, and the state is in an accept state. 