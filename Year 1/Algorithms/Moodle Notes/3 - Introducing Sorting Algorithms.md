In this session, we will consider 2 simple O(n<sup>2</sup>) algorithms in detail. 
- Selection Sort
- Insertion Sort

We will need to demonstrate the operations of this algorithms on sample inputs, and also describe their properties. 

# Sorting

- Sorting means re-arranging the elements of a collection into ascending, or descending order
- Sorting is a fundamental computing task
	- We may sort data for presentation to users, such as by sorting contacts
	- Sorting is an important building block in larger algorithms, because it simplifies tasks such as searching for a particular key or detecting duplicates.
	- E.g. Binary search requires a sorted algorithm to work. 
- Sort keys can be numbers, strings, or anything that has an ordering. 
- We will use numbers in examples, but be careful to distingush an array of index i, from the value ```a[i]``` at that location. 

# Evaluating Sorting Algorithms

- How much space foes the algorithm require in addition to the original array?
	- At best this will be O(1) but some algorithms achieve faster times by using more memory (space-time trade off)
- How much time does it take? We will count comparison operations and consider both average and worst-case. 
- Does the algorithm perform better on sorted inputs? 
	- An **adaptive sort** is one that performs better on partially sorted inputs, and takes O(n) time on sorted or almost sorted inputs. 
	- This can be useful in some applications
- What happens if there are repeated keys?
	- A **stable sort** is one that preserves the relative ordering of elements that compare as equal
	- For example, is there are 2, 4s in an array, their position will not be swapped. The first 4 will always be before the second 4 in the array. 
- This is a useful property, for example we can sort people by first name, and then sort by surname. We will get them in surname, first name order.
- We can make any algorithm stable by including the original position in the sort, but this costs O(n) space and extra time. 

# Selection Sort

- The idea of selection sort is to build up a collection of the smallest elements, in order, at the start of the array. 
- To add a new element to this collections, fins the smallest in what is left, and swap it with the first element after our position. 

```
i = 0
WHILE i < n-1
	min = index of the smallest element in a[i..n-1]
	Swap(a, i, min)
	i = i + 1
```

![[Pasted image 20250317165403.png]]

**Finding the smallest element**

- To complete the algorithm, we need to spell out the line
- `min = index of the smallest element in a[i...n-1]`
- This is similar to the maximum exercise from week 1

```
min = i
j = i+1
WHILE j < n
	IF a[j] < a[min]
		min = j
	j = j + 1
```

- When we reach the end of this loop, j = n, so the invariant tells us that min is the index of the smallest element in the array. 
- This is the position we want to swap with i. 
- It can be that min = i, in which case the swap is unnessesary but harmless. 
- Plugging the two algorithms together makes the full selection sort algorithm

```
i = 0
WHILE i < n-1
	min = i
	j = i + 1
	WHILE j < n
		IF a[j] < a[min]
			min = j
		j = j + 1
	Swap(a, i, min)
	i = i + 1
```

**Evaluation of selection sort**

- Selection sort uses O(1) extra space, for several temporary variables. 
- The time complexity can be seen from the structure of the loops, O(n<sup>2</sup>)
- This means that selection sort is not an adaptive sort. 
- The swap operation can change the order of equal elements, so selection sort is not a stable sort. 

Efficiency
- There are some obvious inefficiencies in selection sort
	- The swap operations moves a small element down, but it moves a more-or-less random element up. Sometimes it moves a fairly small element up and then back down again. Quicksort (week 7) also uses swaps over long distances, but it always moves a large element up at the same time as it moves a small one down. 
	- Selection sort has to search through the whole remainder of the array to find the least element. Heapsort speeds this up with a clever organisation of the rest of the array called a heap. (year 2)

# Insertion Sort

- Insertion sort operations by building an ordered sub array on the left, expanding it by inserting each unsorted position into its appropriate place in the ordered sub-array. 
- Here is a high-level description of this strategy, leaving the detail of how we do the insertion later. 
- Notice that we start with i = 1, because the sub-array containing of just the first element is trivially ordered. 

```
i = 1
WHILE i < n
	insert a[i] in place in a[0...i-1]
	i++
```

![[Pasted image 20250317171301.png]]

**Insertion**

- To complete the algorithm, we need to flesh out the step `insert a[i] in place in a[0...i-1]`
- The idea is to search backwards from position i for the right position. 
- As we search, we move the elements greater than `a[i]` that we encounter one place to the right. 
- Then we find the place where `a[i]` belongs, we will have a slot to put in

Here is the pseudocode to do the insertion

```
tmp = a[i]
j = i
WHILE j > 0 AND a[j-1] > tmp
	a[j] = a[j-1]
	j--
a[j] = tmp
```

At the end of the loop, all the positions `a[j+1..i]` are larger than `tmp`, and either
- j = 0, so copying `tmp` to `a[0]` leaves `a[0..j-1]` in order, or
- all the elements `a[0..j-1]` are less than or equal to `tmp`, so copying `tmp` to `a[j]` leaves `a[0..i]` in order.

Plugging this in gives the complete insertion sort algorithm

```
i = 1
WHILE i < n
	tmp = a[i]
	WHILE j > 0 AND a[j-1] > tmp
		a[j] = a[j-1]
		j++
	a[j] = tmp
	i++
```

# Evaluating Insertion Sort

- Insertion sort uses O(1) extra space, for several temporary variables. 
- Again, we can work out the time complexity by examining the loops. O(n<sup>2</sup>)
- However, the inner loop of this algorithm has an extra condition, which depends on input data. 
	- If `a[i]` is at least as big as the preceding elements, the inner loop exits after only one comparison.
	- The inital array is already ordered, the algorithm does only n-1 comparisons, which is O(n). 
	- Thus, insertion sort is an adaptive sort. 
- The same test ensures that we never move `a[i]` past an equal element. Thus, insertion sort is a stable sort. 

# Can we do better?

- One idea for a faster sort is to move things over longer distances by first sorting the even and odd positions separatley using a simple adaptive sort. 

![[Pasted image 20250317173157.png]]
