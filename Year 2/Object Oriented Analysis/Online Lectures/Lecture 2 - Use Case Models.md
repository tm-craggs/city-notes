#### Part 1 - Basics of Use Case Modelling

###### Objectives

Introduce use case modelling and the UML Use Case Diagrams
- System Boundaries
- Actors
- Use Cases
	- Main and alternative flows
	- Controlling the flow
		- Branching with "if" repetition with for and while
- Relationship between use cases and actors
- Requirements tracing

###### Use Case Modelling

- Use case modelling is a form of **requirements engineering**
- Use case modelling proceeds as follows
	- Find the **system boundary**
	- Find actors
	- Find use cases
		- Use case specification
		- Scenarios

It lets us identify the system boundary, **who** or **what** uses the system, and **what** functions the system should offer.

###### The Subject

Before we can build a system we must know
- Where the boundary of the system lies
- Who or what uses the system
- What functions the system should offer to users

We create a Use Case model containing
- Subject - the edge of the system (system boundary)
- Actors - who or what uses the system
- Use Cases - things actors do with the system
- Relationships - between actors and use cases

###### What are Actors

- An actor is anything that interacts **directly** with the system
- Actors identify **who** or **what** uses the system and so indicate where the system boundary lies.
- Actors can be people or external devices (other systems)
- Actors are **external** to the system, 
- An Actor specifies a role that some external entity adopts when interacting with the system. 
- For example: An online shop isn't processing their own payments, relies on PayPal as an actor. 
- The name of the actor should represent the role

![[image-82.png|336x127]]
*Common notation for an actor called **customer***

###### Identify Actors

This is a best effort activity, no method to always identify every actor. Asking some questions may help. 

- Who or what uses the system?
- What roles do they play in the interaction?
- Who starts and shuts down the system?
- Who maintains the system?
- What other systems use this system?
- Who gets and provides information to the system?
- Does anything happen at a fixed time?
	- Automatic functions in the system are modelled as triggered by an actor called **Time**


