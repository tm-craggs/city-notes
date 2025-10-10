#### Priority Queue

- You can only remove the array with the highest priority
- **Examples**: Printer Queues, Hospitals, Air Traffic Control

**Priority Queue Operations**

- Add an element
- Remove an element
- Check if the queue is empty

**Applications of Priority Queues**

- As a component of various algorithms
- **Sorting**: Add all of the items into the queue one by one and then extract them in order.

**Analysing the Data Structure**

- The data structure takes O(n) space complexity
- By using the ordered array structure
	- `isEmpty` takes time O(??)
	- `add` takes time O(n)
	- `extractMax` takes time O(n)
- You have to check every value to know what is the highest priority, so it is slow at extracting.


#### Trees

- Trees are data structures that have a root, nodes, branches, and leaves. 
- All nodes, apart from the root, are at the end of a branch. 
- Branches proceed from nodes. 
- Nodes without branches are called "leaves"
- Nodes are described as parents and nodes.

**Types of Tree**

- A binary tree is a tree where each node has at most, 2 children.
- A perfectly balanced tree is a tree whose least deep leaf is no more than one level apart from the deepest one. 

- Using heaps, a kind of tree, we can distribute the  load for priority queue, achieving O(log n) for `add` and `extractMax`


#### Heaps

- A heap is a perfectly balanced binary tree such that:
	- No node is larger than its parent
	- All items on the lowest level are as far left as possible. 

**Heap Operations**

- Heap is empty if the root is empty. 
- Heap insertion: add a node to the heap, displacing other nodes as necessary so that the heap, remains a heap. 
- Heap extraction: Remove the element with the highest value in the heap (the root), moving the other nodes as necessary so that the heap remains a heap. 

**Heap insertion**

![[image-59.png|325x211]]

- 12 is inserted at the bottom layer as a leaf
- Note that this means now that the tree is no longer a heap, as this node is now larger than its parent. 
- 12 will swap with 9, then check the node above. 
- 12 will swap with 10, then check the node above. 
- 12 is now smaller than the node above (16), insertion complete. 


![[Lecture 2  - Queues, Trees and Heaps 2025-10-10 09.53.54.excalidraw]]

```python
# Heap Insertion

pos = count + 1

while pos > 1 and data[parent_of_pos] < elt:
	data[pos] = data[parent_of_pos]
	pos = parent_of_pos
	
data[pos] = elt
count = count + 1
```


**Heap Extraction**

```Python
# Heap Extraction

def extractMax():
	max = data[1]
	data[1] = data[count]
	count = count - 1
	moveDown(data, 1, count)
	return max
	
	
def moveDown(data, first, last):
	while first_left_child_pos <= last:
	larger = po
	if data[first] >= data[larger]:
		break
	
	
```

