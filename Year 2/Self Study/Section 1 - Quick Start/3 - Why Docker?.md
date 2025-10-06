Why does docker need to exist? We have been packing software for decades with many different package managers. Here are 3 reasons why we need Docker, and why we need it now. 


#### Isolation

- Isolation was a big problem before containers. 
- There would be so many different apps running on the same server, it became very hard to manage.
- Different apps would need different things, different versions, different dependencies. 
- All apps would be sharing the same file system
- Having different versions of the same app took a lot of hacking. 

**How does docker help?**

- No longer need loads of different Virtual Machines with various different operating systems. 
- Lets you run different versions of the same app with 0 conflicts. 

#### Environments

- Before, we were spinning up loads of different environments and VMs 
- The "works on my machine" joke referred to the fact that the programmers could never test their apps on every single environment that exists, so things were never going to be 100% perfect on every computer.
- For example, dependencies may need to be installed in completely different ways on different machines and operating systems. 
- Containers have vastly improved how we ship software. If you take the metaphor of shipping containers, it does not matter to the shipping company what is inside of the container 

#### Speed
