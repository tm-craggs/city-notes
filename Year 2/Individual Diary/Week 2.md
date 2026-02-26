## Week 2 Overview

February 2nd - February 8th

Week 2 was a productive week for organising the team. We had our first meeting, decided on team roles and how we would approach the project. 

I also attended a meeting with Peter Popov (playing the role of Mr Lancaster) to help clarify many unclear areas of the Client Requirements, and attended our first consultant meeting.


## Team Meeting - February 2nd

At our first team meeting, a few things were discussed. We had. 

-  A quick ice breaker, to get to know names and their strengths and weaknesses.
-  Role assignment, after this we discussed which roles. We collectively decided on the following:
	- Project Manager: Tom
	- Deputy Manager: Anu
	- System Analysts: Anu, Neil, Tharun
	- Designers: Rached, Fariha, Abdullah
	- Programmers: Rached, Fariha, Abdullah, Tom
	- Testers: Neil, Tharun


-  Technical discussion - We decided that we would use Java for any programming. It is a language we are all responsibly comfortable as we had used it in Year 1. Java also lends itself well to Object Oriented Programming, which would be used heavily throughout the project. 
-  We agreed to make this meeting a regular date, every week we will meet up to discuss the project. 
-  We agreed we would use Notion for the team binder, the Deputy Manager was assigned the Job to have it set up and keep it maintained. 
- We set up a GitHub repository for future programming collaboration. 
- Agreed on some basic ground rules on how we would collaborate on shared resources
- Wrote some questions for our interview with Mr Lancaster

![[image-136.png|457x344]]
*A picture of our final role assignments at the team meeting*
#### Reflection

After our meeting, I did a bit of reflection on what my, and other people's roles in the team would be. I wrote some documentation for the group, describing team roles, along with the rules we agreed upon for collaborative coding. I placed it on the GitHub README. I also included links to the resources that we had set up, such as our Project Binder, and shared folder for diagrams and documents. 

![[image-133.png|442x356]]
*An extract from the GitHub README I set up to clarify rules and roles with the group*

![[image-135.png|466x238]]
*Section describing my role in README*
## Mr Lancaster Interview (February 3rd)

I attended an interview with Mr Lancaster on Tuesday. All questions and answers from our team are recorded below. 

Attendees: Tom, Anu

**Q**: What type of security scope is needed for the prototype? Is it enough to just demonstrate functionality or should we include security features?
**A**: Just demonstrating functionality is enough, no need to encrypt user data for the prototype. 

**Q**: Do you want any additional discount plans or just the ones specified in the brief?
**A**: No - only the fixed and flexible discount plans are required. 

**Q**: Would like more clarification on the discount plans. Who assigns discount plans, and how long do they last? Can they change? can they have none?
**A**: Merchants choose their discount plan, they can choose either flexible or fixed, or have none. They can change their discount plan, and the differences must be counted<sup>1</sup>. 

<sup>1</sup> Will need more clarification on this once the development stage is underway. 

**Q**: How are accounts restored from "in-default" back to normal? 
**A**: There is a special account for the company director that has this functionality

**Q**: At what point do you define "low stock conditions" when sending a low stock warning, how is this calculated?
**A**: Each item in the catalogue has its own "low" value, the notification is triggered when stock falls below this number.

**Q**: How is the first admin account created?
**A**: This is a matter for you to decide. The first admin account could be hard coded into the system. 

**Q**: How are admin accounts created?
**A**: Admin accounts or the director can create other admins.

**Q**: Who gets notified when stock falls below minimum?
**A**: There is no notification, but reports can be generated that will specifically show all items that are low stock. 

**Q**: How much of the transaction history should we keep for the merchant for the purposes of generating reports?
**A**: Keep everything, there is no cutoff where history is deleted.

**Q**: How should the three teams products come together in the system demonstration
**A**: All three subsystems must communicate. You can demonstrate them all on one laptop, 

**Q**: How are payments being handled?
**A**: We will be using an external payment provider. Simulating these for the prototype is suffic

**Q**: When is stock reduced after an order, at placement or dispatch?
**A**: Stock should go down when order is placed and should go back if the order is cancelled. Invoice can be raised when shipped. 

**Q**: How does account suspension affect existing orders?
**A**: Any orders before suspension will be honoured, suspension is on new orders. 

## Consultant Meeting (February 6th)

This week we had our first consultant meeting with Konstantin Pozdniakov. We had a brief discussion about how our Use Case Diagrams would look, and confirmed that all team members had got in touch and that we were functioning well as a group. 

