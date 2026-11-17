### What is a Concurrent Program

A **sequential program** has a single thread of control. A **concurrent** program has multiple threads of control allowing it to perform multiple computations in parallel and to control multiple external activities which happen at the same time. 

Don't rely on what is "reasonable" or intuitive in concurrent programming, because the memory model allows suprising behaviour. 

For example
- Reads can see "future" writes. In Java's memory model, a thread can read a value that is written later in the execution order. This feels backwards, but it is allowed.
- Java's guarantee is called "happens-before consistency"
- This can be unacceptable in prac