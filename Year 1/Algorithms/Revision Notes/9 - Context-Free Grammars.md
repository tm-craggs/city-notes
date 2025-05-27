- Regular expressions are well suited to defining simple languages, such as search patterns or the basic symbols of a programming language. 
- As we noticed last week, there are some common structures, such as bracketing structures, that cannot be expressed by regular languages, 
- We will look at context-free grammars, which allow us to express more complex languages
- They are used to define the syntax of most programming languages. 

## Languages and Grammars

- A formal language is a set of strings over an alphabet. 
- We use different terms for context-free grammars:
	- For simple regular expressions, we call the elements of Σ letters and the strings of the language words. 
	- For richer context-free languages, we call the elements of Σ words, and the strings of the language sentences. 


Not any combination of words and symbols is valid. A **grammar** is a set of rules for constructing valid "sentences" of the language.

A grammar imposes a structure on these sentences, this is very important for computer processing, as it is the first step in turning human text into something a computer can use. 