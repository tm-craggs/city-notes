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


