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

Formally:

A **derivation** tree for a context-free grammar is a tree such that:
- Each node is labelled with a terminal or non-terminal symbol
- The root of the tree is labelled with the start symbol
- A node labelled with a non-terminal symbol A has children labelled left-to-right with the symbols in β, where A → β is a production of the grammar
- Nodes labelled with terminal symbols have no children (leaves)


A string can be **derived** from the grammar if there is a derivation tree for the grammar whose leaves, read left-to-right, comprise the string w. 

The **language** of a context free grammar is the set of strings of terminals that can be derived from the grammar. 

Derivation is sometimes presented as beginning with the start symbol, and repeatedly expanding non-terminals until only terminals are left.

Because the grammar is context-free, we could expand the braced words in any order, and still get the same response.

## Programming Languages 

Context-free grammars are commonly used to describe the syntax of a programming languages. For example, here is a simple grammar for Java. 

- ⟨statement⟩ → **;**
- ⟨statement⟩ → ⟨expression⟩ **;**
- ⟨statement⟩ → **{** ⟨statement-list⟩ **}**
- ⟨statement⟩ → **while** **(** ⟨expression⟩ **)** ⟨statement⟩
- ⟨statement⟩ → **do** ⟨statement⟩ **while** **(** ⟨expression⟩ **)** **;**
- ...
- ⟨statement-list⟩ → ε
- ⟨statement-list⟩ → ⟨statement⟩ ⟨statement-list⟩

## Algorithms

A **recogniser** for a grammar is an algorithm that tells us if an input string belongs to the language. 

More often, people want to go the other way. Starting with a string and working out how it can be derived from the start symbol. This process is called parsing. 

A **parser** for a context-free grammar is an algorithm that takes as input a string and either. 
- Returns a parse tree for the string. 
- Announces that not parse tree exists. 

General parsing algorithms parse a string of length n in O(n3) time. In practice, one uses special kinds of context-free grammar that have O(n) time parsers,

## Regular Languages and context-free languages

Any regular language can be described using a context-free grammar. Indeed we can express Kleene star α* (zero or more α's) as a production in two ways, either

- X → ε | α X

or, equivalently

- X → ε | X α

For example, let's start with the regular expression (a|b)((a|b)(a|b))*. We introduce non-terminals to stand for the various parts of the expression, and build up until we have a grammar for the whole thing:

- Let X stand for (a|b). We can define it with a production
    - X → a | b
- Let Y stand for ((a|b)(a|b))*, which we can write more briefly using the previous definition as (XX)*. We can express that as either
    
    - Y → ε | X X Y
    
    or, equivalently
    - Y → ε | Y X X
- Now if S stands for the whole expression, we can define it with
    - S → X Y

## The Chomsky Hierarchy

- The different types of languages in the hierarchy are described by grammars that allow for different types of productions. 

|Type|Grammars|Productions|Recognizers|
|---|---|---|---|
|0|general|α → β|Turing machines|
|1|context-sensitive|αXβ → αγβ|linear-bounded Turing machines|
|2|context-free|X → γ|Pushdown machines|
|3|regular|X → a B  <br>X → ε|Finite state machines|

## Ambiguity

- A context-free grammar is ambiguous if there is more than one parse tree for an input. 
- We want to avoid these grammars
- We can usually tighten grammars that are ambiguous 

## Decision problems

There exist algorithms to test whether the language represented by a context-free grammar is empty, finite or infinite. However, many other properties of context-free grammars are undecidable. That is, there is no general procedure for any of these problems:

Ambiguity

Is the grammar ambiguous?

Universality

Is the language equal to Σ*?

Equality

Do two grammars describe the same language?

Inclusion

Is the language described by one grammar a subset of the language described by another?

Overlap

Is there a string derivable by both of two grammars?