
1.  Do we need to use UML for all design elements?
2. Ask for clarification on the systems analyst role. What are some day to day responsibilities of the role. 
3. Clarify security scope. 
4. How should IPOS-SA be interacted with. Do the administrators need a GUI, TUI, etc. 
5. How are accounts restored from in-default to normal. 
6. When is it decided what discount plan should be provided. Can a user have no discount plan, can it change, who should decide what a users discount plan is. How long do discounts last, are they allowed another after expirity. 
7. Can orders be cancelled or modified?
8. Do our packages have to interact with the email confirmation mechanic. 


Final Questions

1. What type of security scope is needed for the prototype, is it enough to just demonstrate functionality or should we include a full security suite.

Just demonstrating functionality is enough. 

2. Do you want any additional discount plans or just the ones specified in the brief?

No - they are not required

2. Would like more clarification on the discount plans. Who assigns discount plans, and how long do they last? Can they change? can they have none?

They do not have to have a discount plan, decision lies with the merchant through the program. If someone switches from 
Fixed applied to any sale during the month, 

Flex to fixed - freeze the amount when they switch. 

3. How are accounts restored from "in-default" back to normal? 

Special account for the director that has this functionality. 

4. What what point do you define "low stock conditions" when sending out the notification, how is this calculated?

Each item in the catalogue has its own "low" value

3. How is a manager account created? 
4. How is the first admin account created?

	Hard code in a backup account, admins can create other admins.

5. Do you need a GUI to interact directly with IPOS-SA, if so what do you expect from the GUI. 
6. Who gets notified when stock falls below minimum?

Function that allows for quick generation of list of all items which are below stock. No notification. 

7. When an order is placed, does stock reduce instantly or after dispatch?

How much history should we keep for the report, when is the cutoff?
Everything

How should the three teams products come together?
They do need to communicate, all programs can be run on one laptop, or we will need to agree how we will do it online. 


Can simulate third party payments

Stock should go down when order is placed. Should go back if the order is cancelled. Invoice can be raised when shipped. 

Any orders before suspension will be honoured, suspension is on new orders. 