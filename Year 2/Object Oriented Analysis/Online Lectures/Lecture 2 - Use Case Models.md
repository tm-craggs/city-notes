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


###### What are use cases

- Description of the services that a system offers to its uses
- Use cases are **always** started by an actor
	- The **primary** actor triggers the use case. 
	- Every use case must have at least one primary actor
	- Zero or more secondary actiors interact with the use case in some way
		- For example, they may not trigger anything but may be notified
- Use cases are **always** written from the point of view of the actors
	- A Use Case Specigfication is provided for each use case to descrube the interaction of actors and the system. 

![[image-83.png|426x107]]



###### Naming Use Cases

- Use cases should describe something that happens
- They are named using **verbs** or **phrases**
- Naming standard: `UpperCamelCase`


###### Identifying Use Cases

Start with the list of actors that interact with the system
- What functions will a specific actor want?
- Does the system store and retrieve information? How are these triggered?
- What happens when the system changes state? Are any actors notified?
- Are there are external events that affect the system? What notifies the system about those events?
- Does the system interact with any external system?
- Does the system generate any reports? Who triggers report generation?

###### The Use Case Diagram

![[image-84.png|555x308]]

- If we want to make it explicitly clear who is the primary actor, we can use the trigger label
- However, we can usually infer this from their name

Each use case must be defined by a **Use Case Specification** 

![[image-85.png|522x328]]

###### Preconditions and Postconditions

- Preconditions and Postconditions are constraints which must be satisfied (these are facts)
- Preconditions constrain the state of the system before the use case can start
- Postconditions constrain the state of the system after the use case has executed
- If there are no preconditions or postconditions, write "None" under the heading

![[image-87.png|400x478]]


###### Examples of Pre/Post Conditions

**Preconditions**

- The user has a valid user account
- The user has successfully logged in
- A connection to the system has been established

**Postconditions**

- A new record with details of the booking is stored in the system database
- Connection is closed

###### Main Flow

The flow of events lists the steps in a use case. It follows the format 
`<number> The <something> <some action>`

- It **always** starts with an actor doing something. A good way to start the flow of events is `1) The use case starts when <actor> <function>`
- The flow of events should be a sequence of short steps that are:
	- Declarative
	- Numbered
	- Time ordered
- The main flow is always the **perfect world** scenario.
	- Everything goes as expected with no errors. 
	- Alternatives in the flow can be shown by branching or listing under Alternative Flows. 

###### A typical mistake

- The actor does something that has **no consequences** for the system state. 
- Consider the following step
	- X: Receptionist makes a phone call
		- This is not a valid step in Use Case Specification if the system does not maintain a **record about the call**
- Consider this fragment:
	- X: User makes a phone call
	- X+1: The system records the call
	- This is a valid fragment

###### Branching

- You can branch within the main flow if your system is not linear
- Use the keyword **if** to indicate alternatives
- Use indentation and numbering to indicate the conditional part of the flow
- Use **else** to indicate what happens if the condition is false.

![[image-89.png|455x135]]

###### Repetition

- There are two types of loop, **for** and **while**. 
- For is typically used when you know how many times the operation must be repeated. The iteration expression immediately after the for statement indicates the number of repetitions. 
- While is typically used when the number of times the operation must be repeated is unclear. There will be a clear break condition

![[image-90.png|455x154]]

![[image-91.png|457x120]]

###### Alternative Flows

We may specify one or more **alternative flows** through the flow of events. 
- Alternative flows capture **errors, anomalies** and **interrupts**, anything that is **not common**
- Alternative flows typically do not return to the main flow, although they can
- Potentially many alternative flows! You need to manage this. 
	- Pick the **most important** alternative flows and document those
	- If there are groups of similar alternative flows, document one member of the group as an **exemplar** and if necessary add notes to explain how the others differ. 
- Only document enough alternative flows to clarify the requirements

**Look for**
- Events - Not happening, too frequent, too infrequent, wrong order
- Actions - Insufficient information, not completing
- Cognitive exception - Slips, mistakes, lack of knowledge
- Other human exceptions - Age, disability
- Machine exceptions - Power failures, breakdowns
- Human-machine exceptions - Misinterpret interface
- Machine-machine exceptions - Communication failure, scrambled messages

![[image-92.png|176x243]]


###### Documenting Alternative Flows

List the names of the alternative flows at the end of the Use Case
Find alternative flows by examining each step in the main flow and looking for
- Anomalies
- Exceptions
- Interrupts

![[image-94.png|377x345]]

![[image-96.png]]

The alternative flow may be triggered:
- Instead of the main flow, started by an actor
- After a particular step
- At any time during the main flow

###### Requirements Tracing

-  Given that we can capture functional user requirements in a model and in a use case model, we need some way of relating the two. 
- There is a many-to-many relationship between user requirements and use cases:
	- One use case covers many individual functional user requirements
	- One functional user requirement may be realised by many use cases
- Hopefully we have CASE support for requirements tracing:
	- With UML tagged values, we can assign numbered requirements to use cases
	- We can capture case names in out Requirements Database
- If there is no CASE support, we can create a Requirements Traceability Matrix
- We can also use Volere Templates, each functional user requirement provides a link to the use-case ID it is related to. 

![[image-98.png]]

###### When to use use case models

- Use cases describe system behaviour from the POV of **one or more** actiors
- They are the best choice when
	- The system is dominated by functional requirements
	- The system has many types of user to which it delivers different functionality
	- The system has many interfaces
- The are a poor choice when
	- The system is dominated by **non-functional** requirements
	- The system has **few users**
	- The system has **few interfaces**

###### Tips for Use Case Modelling

- It is critical to define use case boundaries
- Identify all actors
- Think about all main tasks for which the system will be used
- Look for all alternative flows
- Always be prepared to revise your use case model
- Distinguish between use cases by frequency of use
- Only describe actions which incolce interaction between actor and system
	- The internal processing that the system might undertake is not part of the use case specification. Internal working will be captured later

## Part 2 - Advanced Use Case Modelling

- There are relationships we still have to explore
	- Action generalisation
	- `<<include>>` and `<<extend>>`


###### Actor Generalisation

![[image-100.png|359x301]]

- The Customer and Sales Agent Actors are very similar
- They both interact with `OrderProducts` `AcceptPayment` `ListProduct`
- Additionally, the sales agent interacts with `CalculateComission`
- Our diagram is a mess, we can simplify it

![[image-102.png|354x261]]

- If two actors communicate with the same set of use cases in the same way, we can express this as a generalisation. 
- The descendant actors inherit the roles and relationships to use cases held by the parent
- We can substitute a descendent actor anywhere the ancestor actor is expected
- This is called the **suitability principle**
-  Only use actor generalisation when it simplifies the model
- Abstract actors are written in *italics*
- Abstract actors do not really exist, they just exist the show the commonality between two actors

###### Use Case Generalisation

- We can use generalisation for use cases too 
- The ancestor use case must be a more general case of one or more descendant use cases
- Child use cases are more specific forms of their parent
- They can inherit, add and override features of their parent. 

![[image-103.png|460x167]]


###### `<<include>>`

- When use cases share common behaviour, we can factor this out into a separate inclusions use case and `<<include>>` it in base use cases
- The base use case executes until the point of inclusion
	- Control passes to the inclusion use case, which executes
	- When the inclusion use case is finished, control passes back to the base use case
- Note
	- Base use cases are not complete without the included use cases
	- Inclusion use cases may be complete use cases, or they may be a fragment of behaviour for inclusion elsewhere

![[image-104.png|469x268]]

![[image-105.png|468x215]]


What if the included use case does not complete successfully?