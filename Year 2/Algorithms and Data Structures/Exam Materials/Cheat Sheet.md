## Time Complexities

**Sorting**

Bubble Sort 
Average/Worst: O(n<sup>2</sup>)
Best: O(n)
Space: O(1)

Insertion Sort
Average/Worst: O(n<sup>2</sup>)
Best: O(n)
Space: O(1)

Merge Sort
All cases: O(n log n) 
Space: O(n)

Heap Sort
All Cases: O(n log n)
Space: O(1)

Quick Sort
Average O(n log n)
Worst O(log n)
Space O(log n)

Bucket
Average/Best: O(n + k) where n is output and k is number of buckets
Worst: O(n+k)
Space: O(n+k) or O(n) if k is proportional to n

**Searching**

Linear Search
Best: O(1)
Average/Worst: O(n)
Space: O(1)

Binary Search
Time: O(log n)
Space: O(1)

Breadth/Depth First Search
Time: O(V + E)
Space: O(V)
*Where V is the number of vertices (nodes) and E is the number of Edges (connections between vertices*

**Abstract Structures**

Singly Linked List
Access by index: O(n)
Search: O(n)
Insert at head: O(1)
Insert at tail: O(n)
Delete at head: O(1)
Delete at position: O(n)

Doubly linked list is the same, but stores a pointer to tail meaning:
Insert at tail: O(1)
Delete at tail: O(1)

Priority Queue
Insert: O(log n)
Extract (min or max): O(log n)
Delete: O(log n) with position known
Search: O(n)

Stack:
Insert: O(1)
Pop/Peek: O(1)
Search: O(n)
Delete: O(log n) with position known

Hash table
Search Insert and Delete: Average O(1) Worst O(n)

## Definitions

Node/Vertex - A unit representing an entity or an object

Edges (links) - A connection between nodes

Binary Tree - A tree where each node has at most 2 children

Root - The node with no parent

Leaf - A node with no children

Perfectly Balanced Tree - A tree who's least deep leaf is no more than one level apart from the deepest leaf

Heap - A binary tree that satisfies the **Heap Property**

Heap Property - A perfectly balanced **binary tree** such that **no node is larger than its parent** and **all items on the lowest level are far to the left as possible**

Graph - A structure representing relationships between objects, using nodes and edges

Directed Graph (digraph) - A set of nodes connection by directed edges (arrows) showing a **one way** relationship. Written {A -> B}

Undirected Graph - A set of nodes connected by edges where they have no direction. Written {A, B}

Cyclic Graph - A graph containing at least one cycle, which is a path that starts and ends at the same node, forming a closed loop. These can be directed or undirected.

Tree - An undirected graph with no cycles, meaning there is one unique path between any nodes. 

Binary Search Tree (BST) - A binary tree with an **ordering property**, all children to the left must be smaller than its parent, any children on the right must be larger. Duplicates are generally not allowed, if they are a consistent rule must be used. 

Splay Tree - A tree where recently accessed nodes are made quickly accessible. Any binary search tree can be a splay tree. 

Key - A value stored in the node

B-Tree - A tree where each node can have up to m children, and store up to m-1 keys per node. 

Hash Function - A function that maps keys to array indices (hash values)

Hash Table - A data structure that uses a hash function to map keys positions in an array for fast lookup.

Hash Value - The integer output of a hash function, used as an index in the hash table

Collision - When two keys map to the same index

Clustering - Groups of consecutive slors that form and degrade the performance. 

Bucket - A slow in the hash table array that stores key/value

Chaining (Closed Adressing) - A method for resolving collisions, each bucket stores a linked list of all keys that hash to that position. Seach time O(1 + a) *where a = load factor*

Open Addressing - When collision occurs, look for the next avaliable slot. Types include:

Linear Probing - Check the next slot sequentially
Quadratic Probing - Check the next slot quadratically. 
Double Hashing - Use a second hash function to determine the step size. 

Breadth First Traversal

Depth First Traversal 

Pre order - 
In order -
Post order - 

## Considerations for Algorithms

- Remember to handle edge cases initially, such as checking if queues are empty
- Remember to return values at the end of functions
