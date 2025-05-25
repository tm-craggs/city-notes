- There are problems that can't be solved in a reasonable amount of time
- There are problem for which nobody knows whether they can be solved in a reasonable amount of time. 
- There are problems that can't be solved at all. 


## Tractability

- What kind of performance is acceptable?
- Some problems that appear to be intractable.

**Satisfiability Problem**

- Given a formula of propositional logic, like (A OR (NOT B) AND ((NOT A) OR B)
- Is there an assignment of truth values to variables that makes the formula true. 

**Knapsack Problem**

- Given a collection of items, each with a weight and value. 
- Is there a selection of items with total weight less that the capacity of the knapsack that achieves a certain value?

**Bin Packing Problem**

- Is there a way of dividing up a collection of various sizes so that they fit in a certain number of bins?

![[image-38.png|508x222]]

**Travelling Salesman Problem**

- Is there a tour of a graph, visiting each node and returning to the starting point, within a certain maximum distance?

**Maximal Clique Problem**

- Does a given graph contain a clique (a set of nodes directly connected to the others) of a certain size?

**Three Colouring Problem**

- Is there a way of colouring the nodes of a graph with 3 colours such that no two directly connected nodes have the same colour.

**Timetabling Problem**

- Given collection of modules, rooms and times, is there an exam timetable such that no student had two exams on the same day

These algorithms are all decision algorithms (is there a solution?) but can easily be adapted to searching algorithms. (what is the optimal soloution?) 


## Exploring These Problems

- The problems we considered are diverse, but all share the same characteristics.
- They are simple in structure (assignment of variables, selection of items, tour of a graph)
- However, the number of candidate solutions is enormous. 

**NP** - Nondeterministic Polynomial Time. Is the class of problem for which if the answer is yes, there exists a _certificate_ (or candidate solution) that can be verified in polynomial time. **If someone gives you a proposed solution, you can check whether it works in Polynomial Time**


- It is easy to show that each of the above problems is in NP.
- For example, satisfiability is in NP because to construct a candidate solution, we just guess boolean values for each of a the variables, and to check it we evaluate the boolean expression. 
- Both can be done in time proportional to the size of the expressions, (linear time) which is certainly polynomial. 
- Now every problem is in BP, but we don't know if the reverse is true. The question is. 
- P = NP or P ≠ NP
- There are more problems outside of NP, but we know they are intractable. 

Essentially, the only way to approach these problems is to guess a candidate solution and then verify if the candidate solution is valid, in polynomial (acceptable) time. 


## Reduction of problems

- One strategy to solve a problem is to reduce it to a problem for which we have a good algorithm.
- We say a problem A can be **reduced** to a problem B if we can write an algorithm for A that calls an algorithm for B.
- For example, consider the problem of finding the median number in an array of numbers.
	- We can reduce this to the sorting problem, and then just find the middle value. 
- We can reduce the three colouring problem to the satisfiability problem, by expression the colouring condition as a logical formula. 

- Suppose we reduce the three colouring problem to the satisfiability problem.
	- Suppose we have a graph with _n_ nodes.
	- Introduce 3 boolean variables for each node:
		- r<sub>i</sub> is true if node _i_ is red.
		- g<sub>i</sub> is true if node _i_ is green.
		- b<sub>i</sub>  is true if node _i_ is blue.
	- For each node, add a formula saying the node has only one colour
		- ¬(r<sub>i</sub> ∧ r<sub>i</sub>) ∧ ¬(g<sub>i</sub> ∧ g<sub>i</sub>) ∧ ¬(g<sub>i</sub> ∧ g<sub>i</sub>)
	- For each pair of nodes i and j connected connected by an edge, add a formula that they have different colours. 
		- ¬(r<sub>i</sub> ∧ r<sub>j</sub>) ∧ ¬(g<sub>i</sub> ∧ g<sub>j</sub>) ∧ ¬(g<sub>i</sub> ∧ g<sub>j</sub>)
	- Join all these formula together with ∧
- Then, the resulting formula is satisfiable, only if the graph has three colouring. 
- The size of the formula is proportional to the size of the graph. 
- Therefore a polynomial algorithm for the satisfiability problem would give us a polynomial algorithm for the Three Colouring Problem. So we have a polynomial-time reduction. 
- By reducing the three colouring problem to the satisfiability problem, we have shown that satisfiability is at least as hard as three colouring. 
- In this case, we can also perform a reduction the other way, implying they are equally hard. 

