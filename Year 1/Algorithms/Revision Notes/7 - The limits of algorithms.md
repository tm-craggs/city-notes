- There are problems that can't be solved in a reasonable amount of time
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

**NP** - The class of search problems for which constructing and checking a single possibility can be done in polynomial time. 

- It is easy to show that each of the above problems is in NP.
- For example, satisfiability is in NP because to construct a candiate