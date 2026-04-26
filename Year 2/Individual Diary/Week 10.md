
## Week 10 Overview

March 30th - April 5th

This week saw me begin API programming for our system integration, and also speaking at the Group Project lecture on behalf of Group 11. 

## Speaking at Lecture - March 30th

During this lecture, I had the chance to speak to the class on behalf of Group 11, to share some tips from our group. Here is an overview of what was covered:

-  Talked about our tech stack of Java, JavaFX, Javalin and SQLite
-  Spoke about the benefits of our tech stack:
	-  **Java benefits:** 
	- **SQLite benefits**: Stores all databases in a local file, no need to manage a server. 
	- **Javalin benefits:** Lightweight rest API that is easy to build on-top of your project. Spring Boot required changing our Launcher methods and was conflicting with JavaFX. 
	- Most people had been using MySQL and Spring Boot, so I wanted to share alternatives that could help other groups.
	
- I also briefly discussed how our group are integrating and our convention for port number usage.

## Programming Progress

This week I began programming our rest API, which will be used to integrate with other groups. This involved downloading and setting up a new dependency, along with reworking a few functions inside DatabaseManager to be compatible with a JSON format. 

I decided on Javalin for the rest API after initially trying to implement Spring Boot. Spring Boot required fundamentally changing how our program launcher and ran. Javalin was much easier to layer on top of our existing code. 

Changelog:
- Add `Server.java` where API boilerplate is modelled
- Add handling for API endpoints `/` and `/track` 
- Add API initialisation to Launch process

## Merge Requests

By now, code from other team members is starting to be merged into. There were merge conflicts that required resolving, particularly in the DatabaseManager file. The first code from the RPT and CAT subsystems


![[image-142.png]]

![[image-141.png]]

![[image-144.png]]