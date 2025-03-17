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
	- A **stable sort** is one that preserves the relative ordering of element