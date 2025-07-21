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

**Double Negation** 

The negation of a negation is equivalent to the original proposition

**Excluded Middle**

The law of excluded middle (**tertium non datur**) says that either a proposition is true or its negation is true. In addition, a statement cannot be true and false. 

![[image-54.png]]

**De Morgan Duality**

A negation of an entire statement can be split but negating each letter and reversing the sign. 

![[image-55.png]]
### Logical Implication

- Consider the implication `p1 and p2 and p3 ... pn) -> q`
- Here n is a positive integer, and the statement p1 and p2... are called **premises** of the argument. 
- Statement q is the conclusion of the argument. 
- One way of demonstrating the validity of the argument is to show that the statement is a tautology. 

**Examples**

Consider the following propositions

**If it is raining, I will get wet**
**It is raining**

If we denote raining as p, and getting wet by q, it is natural to conclude that if the above propositions are true, then I will get wet is also true. 

![[image-56.png]]

- The first three columns are obvious, they represent the truth table for a simple implication. 
- The fourth column represents the truth value for the 2 statements. If it is raining, then I will get wet (p -> q) and It is raining (p)
- The final column looks at the consequences of taking the two statements to see when q is true. We can see that it is true for all possible combinations, it is a tautology. Hence we can say it is a valid argument and that p, logically implies q. 

### Rules of interference

- From logical implication, rules of inference are derived. The first rule of interence is called **modus ponens**
- This is expressed with the logical implication

![[image-57.png]]

- This rule of inference allows us to make inferences from given facts. For example
- If I go to Greece for a holiday, then I will get a suntan. I went to Greece for a holiday. 
- From which we can deduce, that I have got a suntan. 
- I have won the lottery. If I win the lottery then I will quit my job. 
- From this we can deduce that I will quit my job. 
- However, it does not work backwards.
- I have quit my job. If I win the lottery, then I will quit my job. Does not mean that 

