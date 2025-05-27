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

## Approximating Natural Languages

- Languages people speak and write follow very complex grammar rules, but we can approximate them for a simple subset to illustrate the idea of a formal grammar. 
- Think about constructing simple English sentences from a small vocabulary. 
- Use the following braced words to name syntactic categories.

⟨sentence⟩, ⟨subject⟩, ⟨predicate⟩, ⟨noun-phrase⟩, ⟨article⟩, ⟨modified-noun⟩, ⟨adjective⟩, ⟨noun⟩ and ⟨verb⟩.

A formal grammar would give possible expansions of these categories in terms of other categories and concrete words. 

⟨sentence⟩ → ⟨subject⟩ ⟨predicate⟩ 
⟨subject⟩ → ⟨noun-phrase⟩
⟨predicate⟩ → ⟨verb⟩ ⟨noun-phrase⟩
⟨noun-phrase⟩ → ⟨article⟩ ⟨modified-noun⟩
⟨modified-noun⟩ → ⟨adjective⟩ ⟨modified-noun⟩
⟨modified-noun⟩ → ⟨noun⟩
⟨noun⟩ → apple
⟨noun⟩ → bear
⟨noun⟩ → worm
⟨noun⟩ → dog
⟨verb⟩ → eats
⟨verb⟩ → follows
⟨verb⟩ → eats
⟨verb⟩ → hugs
⟨adjective⟩ → wriggly
⟨adjective⟩ → tasty
⟨article⟩ → a
⟨article⟩ → an
⟨article⟩ → the

We call this a **context-free grammar**, because the possible expansion of a category like ⟨noun-phrase⟩ does not depend on any words that surround it (i.e. its context).

Formalising these ideas, a **context-free grammar** is a collection of 4 different things. 

- An alphabet 