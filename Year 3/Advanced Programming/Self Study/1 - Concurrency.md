### What is a Concurrent Program?

A **sequential program** has a single thread of control. A **concurrent** program has multiple threads of control allowing it to perform multiple computations in parallel and to control multiple external activities which happen at the same time. 

Don't rely on what is "reasonable" or intuitive in concurrent programming, because the memory model allows surprising behaviour. 

For example
- Reads can see "future" writes. In Java's memory model, a thread can read a value that is written later in the execution order. This feels backwards, but it is allowed.
- Java's guarantee is called "happens-before consistency"
- This can be unacceptable in practice, happens before consistency isn't considered enough and there can be further constraints. 

So why use concurrent programming?

- Performance gain from multiprocessing hardware
- Increased application throughput
- Increased application responsiveness 
- More appropriate structure for programs that interact with the environment or control multiple activities/events

### Parallel vs Concurrent Programming

**Parallel** - Do as many concurrent actions, quickly as possible
**Concurrent** - Happy if we can do it correctly 

Parallel Slowdown - As processors increase, speedup decreases and may even become negative. Coordination has a cost (Brook's law: adding manpower to a late project makes it later)


![[Pasted image 20261117152554.png|596]]

