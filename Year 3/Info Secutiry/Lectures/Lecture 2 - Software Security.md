
### Outline

- Software security
- Buffer overflow
- Malware

### Software Security

What is software security?

- Ensures software functions correctly even when under attack
- Focuses on prevention, detection and mitigation of vulnerabilities
- Integral to trustworthy computing

Why it matters

- Most modern attacks target software flaws, not hardware
- Economic and reputation damage can be enormous 
- Early prevention is cheaper than most incident response

Common vulnerabilities

- Memory safety (buffer overflow, dangling pointer)
- Injection attacks (SQL, command, LDAP, XSS)
- Authentication and session flaws (weak password, token reuse)
- Insecure deserialization and race conditions

Deserialization - 
Race Condition -  when multiple processes attempt to access the same shared resource simultaneously 


Secure Software Development Lifecycle (SSDLC)

- Integrate security into all stages of development
- Key practises
	- Threat modelling
	- Secure code review
	- Security testing (static and dynamic)
- The goal is to "shift security left", or address issues early


Secure Coding Practices

- Validate all inputs and sanitise all outputs
- Avoid dangerous functions `strcpy, eval`
- Follow the principle of least privilege
- Use well-maintained libraries and frameworks
- Keep dependencies up to date
- Document assumptions and threat mitigations 


Testing and Verification


