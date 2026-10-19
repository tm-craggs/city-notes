
### Contents

- Alphabets and strings
- Languages and machines
- Deterministic FSA and transition diagrams 
- Non-deterministic FSA
- Comparing DFSA and NFSA

### Alphabets

Alphabet - A finite set of symbols/characters used for encoding, often represented with the symbol $\Sigma$

Examples:
$\Sigma$ = {0, 1}
$\Sigma$ = {a,b c}
$\Sigma$ = All characters in the Roman alphabet


### Strings

A string `w` over an alphabet $\Sigma$  is a finite sequence of symbols in $\Sigma$

Examples over alphabet $\Sigma$ = {a,b}

- a
- b
- abb
- baababa
- $\varepsilon$ (empty string)

### Languages and Machines

Language - A set of strings

A language `L` over an alphabet $\Sigma$ is a set of strings over $\Sigma$ . L is a subset of $\Sigma$*

Machines - Compute by accepting **all** the strings in some language, and rejecting **all** others. 

There is an equivalence between language and machine. They both only accept words if it is part of the language. 

**Example:**
