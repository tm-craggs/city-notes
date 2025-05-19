
We should be familiar with
- Describing **regular languages** using **regular expressions**
- Recognising these languages using finite state machines. 

## Formal Languages

- General linguistics is hard. In Computer Science, we work with a simplified view of languages called "formal languages"
- We are only concerned with the surface structure of (syntax) of languages, not their meaning (semantics)
- Surface structure is a pre-cursor to meaning. 

**An Alphabet** - Usually written Σ is a finite set of symbols or letters.

**Examples of alphabets:**

Σbits = {0, 1}
Σdigits = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}
Σletters = {a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z}

**A string over an alphabet Σ** - A finite sequence of symbols from the alphabet Σ. 
- The set of strings over and alphabet Σ is written as Σ*
- The empty string is usually written ε (sometimes λ)

The symbols of a string are usually written together, without commas.

Although each string is finite, there are infinite many of them. Σ* is an infinite set. 

**A language over an alphabet Σ** - A finite or infinite set of strings over the alphabet, that is, a subset of of Σ*. 

The following are examples of languages over the alphabet Σ = {a,b}

- `∅`, the empty set of strings
- `{ε}`, the set containing only the empty string
- `{ε, a, b, aa, ab, ba, bb}`, the set of strings of length at most 2
- `{ε, a, aa, aaa, ...}`, the infinite set of strings consisting of just a's
- `{ε, a, b, aa, ab, ba, bb, aaa, aab, ...}`, the infinite set of all combinations of a's and b's
- `{ε, ab, aabb, aaabbb, aaaabbbb, ...}`, the infinite set of strings consisting of _n_ a's followed by _n_ b's.

For any formal language, a key task is testing for membership of the set of strings. 

A **recogniser** for a language L over an alphabet Σ is a machine that can be used to decide whether a string over Σ is in L.

## The Chomsky Hierarchy

There are several ways to define particular formal languages. The following types were defined by Noam Chomsky. Each type is a restriction of the previous one. 

![[image.png]]


Computer processing relies on the last two. These languages are simple enough to allow efficient recognisers. That is, algorithms can recognise a string of length n in O(n) time.

## Operations on formal languages

- There are various operations to make new languages from existing ones.

Example:

- Union
	- The **union** of two languages, L<sub>1</sub>
- Intersection
- Compliment
- Concatenation
