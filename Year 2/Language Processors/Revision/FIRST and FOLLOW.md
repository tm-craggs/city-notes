
Step 1: Identify Nullable Non-Terminals.

To check it is not a terminal, it should not be in capitals and appear as an expression. 
If it is nullable, it will have one entry mapping to the entry string. Example:

`Terminal -> `

Step 2: FIRST sets

FIRST(x) = the set of tokens that can appear as the first token of any string derived from X

Rules
- If X -> A (where A is a token) add A to FIRST(X)
- If X -> Y (where Y is a non-terminal) add FIRST(Y) to FIRST(X)
- If X -> Y and Y is nullable, also look at what comes after Y (need more explanation)
- 

