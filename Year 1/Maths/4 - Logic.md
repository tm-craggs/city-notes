#### Basic Connectives and Truth Tables

- In the development of mathematical theory, assertions are made in the form of sentences.
- Such verbal or written assertions, called statements (or propositions) are declarative sentences that are either true or false - but not both. 
- For example, the following are statements, we use the lowercase alphabet to represent these.
	- p: Logic is a required subject for Computer Scientists
	- q: The moon is made out of green cheese
	- r: 2 + 3 = 5

- On the other hand, sentences such as:
	- Shut the door!
	- What a lovely evening!
	- I name this ship the "RMS Titanic"
- These do not have an obvious truth value.
- Other sentences are problematic because their truth value is subjective. 
	- e.g. He is well qualified for this position

- The statements represented by p,q,r are considered to be **primitive** statements, for there is no meaningful way of breaking them down into anything simpler. 
- New statements can be obtained from existing ones in two ways. 

1. Transform a given statement p into the statement ¬p, which denotes its negation and is read Not P
2. Combine two or more statements into a compound statement, using the following logical connectives.
	1. **Conjunction**: The conjunction of any statement p,q is denoted by p ^ q.
	2. **Disjunction**: The expression p ⌄ q denotes disjunction. 
	3. **Implication**: We say that "p implies q" and write p -> Q to designate the setentence, which is the implication of q by p. The statement p is sometimes referred to as the hypothesis, and q is called the conclusion. 

		When statements are combined in this manner, there does not have to be any causal relationship between the statements for the implication to be true. Think of it as a vow or a promise. E.g. If I get 95% in this test, I will have a drink to celebrate
	4. **Biconditional**: The biconditional of two statements p,q, is denoted by p <-> q, which is read p if and only if q

We can further explore the truth or falsity of statements by constructing truth tables



#### Logical Equivalence

Two statements are said to be logically equivalent if they always produce the same truth and falsity for every possible input. For example, if every row of the truth table for each statement is the same.

Here, ¬p or q is the same as p -> q

![[image-47.png]]

#### Compound Statements

- A compound statement (proposition) is called a **tautology** if it is **true** for all truth value assignments for its component statements. 
- If a compound statement is **false** for all such assignments, then it is called a **contradiction** 
- A proposition is called **satisfiable** is there exists a truth assignment that makes the proposition true.
- We can use the ideas of tautology and implication to form a valid argument which will also be of use if we are proving maths theories

### Equivalences

**Idempotence**

![[image-49.png]]

**Associativity**

The conjuction and disjunctions of operators are associative, it does not matter in which order they are considered. 

![[image-51.png]]

**Commutativity**

The conjunction and disjunction operators are commutative, the order of the conjuncts can be reversed. 

![[image-52.png]]

**Distributivity**

Conjunction distributes over disjunction, and vice versa 

![[image-53.png]]

