Write a method/function in pseudocode that receives an undirected graph, where the vertices contain unique positive integer values, finds the vertices that contain an even number and doubles the values of every vertex that it is adjacent to. Note that no vertex should be doubled more than once. The method returns the new graph.

The graph is stored on an adjacency list represented as an array of vertices with links to their corresponding adjacent vertices.

```
Function doubleCost( g )

// Create a new array of vertices to keep track of those to be doubled.
New toBdoubled[]

// Traverse the graphsearching for vertices that contain an even number.
// Track their adjacent vertices as we may need to visit a vertex more than once (may not need doubling when first visited)

FOR ALL vertices v in the graph g

     IF (v.info MOD 2) = 0  // OR “IF its label MOD 2 = 0”

     // the vertex has an even value, all its adjacent vertices should be doubled. That means

     // adding them to the array toBdoubled.

          FOR ALL vertices u adjacent to v

               IF they are not yet in the array toBdoubled 

                     Add u to the array toBdoubled

// All vertices to be doubled have now been identified and can now be doubled. Traverse

// the graph again, doubling all relevant entries.

FOR ALL vertices v in the graph g

     IF v is in the array toBdoubled

           v.info ← v.info * 2

Return g
```


Write a method/function in pseudocode that receives a stack of positive integers as its parameter, where each of the integers may appear more than once. Your algorithm should return a doubly linked list containing the same integers that were present in the stack. The doubly linked list is to contain no duplicated values. The items on the doubly linked list should be in the same order as they were in the stack (the first item retrieved from the stack should be the first value on the doubly linked list). Duplicated values should appear in the doubly linked list only once, in the same position as they were when first retrieved from the stack. If the stack is empty, the same should be true of the doubly linked list.

For example, given a stack with the values (from top to bottom)  10  2  34  5  10  2  10  9, the method should return a doubly linked list containing (from head to tail)  10  2  34  5  9.

Feel free to use auxiliary functions/methods if these help you. You may use (call) the basic operations taught to you in this module, without the need to redefine them. The use of programming language specific library functions is not allowed. 

Explain how your method works by means of comments in the algorithm. A correct method with **no comments** gets a maximum of 10 marks.



```
Function stk2dll( stk )

// This solution removes from the stk and adds to the doubly linked list, checking that the

// entry does not yet exist in the list before adding it.

Define an empty DLL called dll

WHILE !stk.isEmpty()

// Deal with the values from the stack one at a time.

      val ← stk.pop()   // keep track of value being handled
      ptr ← dll.head    // ptr used to traverse the list to check for duplicates
      found ← false     // flag whether the value is already in the list
      WHILE ptr != null and !found

            IF ptr.info == val

                  // the value is already in the list, it was a duplicate.
                  found ← true

            ptr ← ptr.next

      IF !found

            dll.addToTail(value)


Return dll
```

