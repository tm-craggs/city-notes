A pumping lemma is used to prove that a language is **not** regular. Meaning it cannot be represented using Finite State Machines.

It is one-way, it cannot be used to prove that a language **is** regular

Example Question

If A is a Regular Language, then A has a pumping length 'P' such that any string 'S' where |S| >= may be divided into 3 parts. S = x y z such that the following condition must be true. 

1.

x y<sup>i</sup> z $\epsilon$ A for every >= 0

What this means is that any string that is created must have x (the section that comes first), z (the section that comes last), y (the section in the middle that can be repeated for any number greater or equal to 0). The result must be in the language. 

2.

