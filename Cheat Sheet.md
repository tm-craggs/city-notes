## Lecture 1

NFSA and DFSA. Make a table and do union. 

Transitions are done by {((state, input),new state)}

the properties of machines are

Q = {set of all the states}
$\Sigma$ = the alphabet
q<sub>0</sub> = the starting state (or states)
S = transition algebra shit
F = accept state

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

In English. y can't be 0, x and y together cannot be longer than the pumping length, and that y can be infinitely repeated, with x before and z after, and still be in the language. 

# Lecture 4

Push Down Automata are FSA with a stack (memory) Each operation can read input, push onto the stack, pop off from the stack, or go to another state.

It is considered accepted when all input is empty, the stack is empty, and the state is in an accept state. 


In the transition list, it uses the format

{((state, read, pop), (go to, push)),
etc.
}

((s0, a, ε), (u, A)): In s0, read **a**, pop nothing, push **A**, go to **u**.