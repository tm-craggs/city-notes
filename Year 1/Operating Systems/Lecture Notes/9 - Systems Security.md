## Computer Security Overview

- Computer Security is defined as
	- "The protection afforded to an automated information system in order to attain the applicable objectives of preserving the integrity, availability and confidentiality of information system resources"
- Preserving integrity, availability and confidentiality is known as the CIA Triad

##### **Key Security Concepts**

- **Confidentiality**
	- Preserving authorised restriction on information access and disclosure
	- Including means for protecting personal privacy and proprietary information
- **Integrity**
	- Guarding against improper information modification or destruction
	- Including ensuring information non repudiation and authenticity
- **Availability**
	- Ensuring timely and reliable access to and use of information

##### The Security Problem

- System secure if resource used and accessed as intended under all circumstances
	- This is unachievable
- **Intruders** attempt to breach security
- **Threat** is potential security violation
- **Attack** is attempt to breach security (accidental or malicious)
- Easier to protect against accidental than malicious

##### Security Violations

- **Breach of confidentiality**
	- Unauthorised reading of data
- **Breach of integrity**
	- Unauthorised modification of data
- **Breach of availability**
	- Unauthorised destruction of data
- **Theft of service**
	- Unauthorised use of resources
- **Denial of Service (DOS)**
	- Prevention of legitimate use. 

## Problems: Security Violation Methods

##### Some Computer Security Challenges

- Computer Security is not as simple as it might seem
- Potential attacks on the security features must be considered
- Procedures used to provide particular services are often counter intuitive
- Physical and logical placement needs to be determined
- Additional algorithms or protocols are usually needed on top of what may be provided by the functional requirements of the system
- Attackers only need one weakness, developers need to find all weaknesses
- Users and system managers tend not to see the benefit of security until a failure occurs
- Security requires constant monitoring
- Security is often an afterthought incorporated into a system after the design is complete. 

## Actions to Mitigate the Problems

- Impossible to have absolute security, but make cost high enough to deter attackers to easier targets
- Security must occur at 4 levels to be effective

- **Physical**
	- Data centres, servers, connected terminals
- **Human**
	- Avoid social engineering, phishing, dumpster diving etc.
- **Operating System**
	- Protection mechanisms, debugging
- **Network**
	- Intercepted communications, interruption, DOS

- Security is as weak as the weakest link in the chain.
- Can too much security be a problem? Does it effect availability?


## Authentication, Passwords and Alternatives

##### Authentication

- Defined as: "The process of verifying an identity claimed by or for a system entity"
- Authentication is a fundamental of computer security and the primary line of defence. 
- It provides the basis for access control and use accountability. 
- There are 2 broad steps in the auth process

- **Identification**
	- Step presenting an identifier to the security
- **Verification**
	- Step presenting or generating authentication information that corroborates the binding between the entity and the identifier

![[image-13.png|351x188]]


##### Means of Authentication

- Three main aspects under the user's control which can be used to auth a user
	- The users possession of something (a key or a card)
	- The users knowledge of something (a user ID and password)
	- An attribute of the user (fingerprint, retina pattern, signature)

##### Password Authentication

- Widely used line of defence against intruders
- User provides name/ID and password
- System compares password with the one stored for that ID
- Once authenticated, the user ID
	- Determines if the user is authorised to access the system at all
	- Determines the users privileges if so

##### Password Vulnerabilities

- Offline dictionary attack
- Specific account attack
- Popular password attack
- Workstation hijacking
- Exploiting user mistakes
- Exploiting multiple password use
- Electronic monitoring


##### Countermeasures

- Controls to prevent unauth access to password file
- Intrusion detection methods
- Rapid re-issuance of compromised passwords
- Account lockout mechanisms
- Policies to inhibit users from selecting common passwords
- Training in and enforcement of password policies
- Automatic workstation logout
- Policies against similar passwords on network devices. 

##### Password Selection Techniques

- User education
	- Users can be told the importance of using hard to guess passwords, provided with guidelines
- Computer Generated Passwords
	- Very effective, but users have trouble remembering them
- Reactive password checking
	- System periodically runs its own password cracker to find guessable passwords
- Proactive password checking
	- User is allowed to pick their own password within certain parameters.
	- Goal is to eliminate guessable passwords while allowing user to pick something that is memorable. 

## More on threats
