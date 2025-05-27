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

- An alphabet Σ of symbols called **terminals** from which strings in a language will be constructed. 
- A separate set of symbols called **non-terminals** or **variables**
- A distinguished non-terminal called the **start-symbol** usually called *S*
- A finite set of **productions** or **rules** of the form A → β, where A is a non-terminal and β is a finite sequence of zero or more terminal or non-terminal symbols. 

## Alternative Notation

- Sometimes a more compact notation can be used, combining rules with the same left side and separate the right side with vertical bars. 

⟨sentence⟩ → ⟨subject⟩ ⟨predicate⟩
⟨subject⟩ → ⟨noun-phrase⟩
⟨predicate⟩ → ⟨verb⟩ ⟨noun-phrase⟩
⟨noun-phrase⟩ → ⟨article⟩ ⟨modified-noun⟩
⟨modified-noun⟩ → ⟨adjective⟩ ⟨modified-noun⟩ | ⟨noun⟩
⟨noun⟩ → apple | bear | worm | dog
⟨verb⟩ → eats | follows | eats | hugs
⟨adjective⟩ → wriggly | tasty
⟨article⟩ → a | an | the

This notation is known as Backus-Naur form. (BNF)


## Deriving a Sentence

- The language derived from the above grammar includes the sentence.
- "The wriggly worm eats the tasty apple"

- We can show this using a **derivation tree**, starting with the start symbol ⟨sentence⟩ and expanding a non-terminal symbol (here marked with angle brackets), such as ⟨noun⟩, using a rule from the grammar until the only terminal symbols (concrete words) remain:

![[image-43.png|416x309]]

- Trees are drawn upside-down with the root at the top and the leaves at the bottom. 
- The root of the tree is labelled with the start symbol. 
- The leaves of the tree (at the bottom) are labelled with non-terminals. 
- The children of each non-terminal correspond to the right hand side of a production of that non-terminal. 