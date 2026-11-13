A pumping lemma is used to prove that a language is **not** regular. Meaning it cannot be represented using Finite State Machines.

It is one-way, it cannot be used to prove that a language **is** regular

Example Question

If A is a Regular Language, then A has a pumping length 'P' such that any string 'S' where |S| >= may be divided into 3 parts. S = x y z such that the following condition must be true. 

1.

x y<sup>i</sup> z $\epsilon$ A for every >= 0

What this means is that any string that is created must have x (the section that comes first), z (the section that comes last), y (the section in the middle that can be repeated for any number greater or equal to 0). The result must be in the language. 

2.

|y| >  0. This means that the length of y should be greater than 0

3.

|xy| <= p 

This means that the length of x and y should be less than or equal to the pumping length


To prove that language is not regular using the **pumping lemma**, follow the steps to prove using contradiction.

- Assume that A is regular 
	- It has to have a pumping length (say P)
	- All strings longer than P can be pumped |S| >= P
- Now find a string 'S' in A such that |S| >= P. (greater than or equal to pumping length)
- Divide S into three parts x y z
- Show that x y<sup>i</sup> z is not in the language for some i value
- Then consider all ways that S can be divided into x y z
- Show that none of these can satisfy all the 3 pumping conditions at the same time
- If S cannot be pumped, this is a contradiction

