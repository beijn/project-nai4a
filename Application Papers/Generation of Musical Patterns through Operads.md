## Musical phrases as operations on musical phrases [^@giraudoGenerationMusicalPatterns2021]
[source, examples, and further literature](https://github.com/SamueleGiraudo/Bud-Music-Box)

![[Generation of Musical Patterns through Operads - Formula 32-34.png]]

## Motivation
- [[Operads]] from [[Algebraic Combinatorics]]

## Ideas
- Musical patterns are [[Operators]] on musical patterns (thus forming an [[Operad]]): $\square\bar{2}1\square 1\ \circ_2\ 0\square\bar{1}\ =\ \square\bar{2}\ 1\square 0\ \square 1$ (25)
	- (insert at the position indexed by the composition the second sequence, where the steps become shifted by the replaced element's step (numbers denote steps on a rooted #scale, with bar downwards, squares denote rests))
	- A *multi-pattern* is a mathematical abstraction of polyphonic music by steps over *any* rooted scale on beat-or-sustain time-slices. 
	- An [[Operad]] is, e.g. a set of multi-argument functions ([[Operator]]s), where rules for [[Composition]] are defined over all n arguments. 
		- A partial operad composition is a composition indexed by the position of a specific argument of the first operator. (Instead of taking the original n-th argument, the composition takes tne n' arguments of the second operator at this place.)
- [[Colored Operads|Colors]] [^12] are a way to restrict compositon (similar to types restricting function plumbing), e.g. prohibiting certain intervals
- Grammar based #random #generation through [[Bud Generating Systems]] [^5], which are similar but more general to [[Context Free Formal Grammars]] [^8]
	- They allow for 3 random generation algorithms, starting with an inital population of patterns.
	- Thus, a powerfull parametric generative device for Evolutionary Algorithms.

## Inductive Biases
- music = pitch^n per time step
	- *patterns* have no different notions for quite rest vs sustained note (besides expressivity this impacts polyphony)
- The presented generative system is capable of explicitely encoding powerfull rules for #compositon as nested composition' of patterns [^1] 

## Context
- enables a [[Formal Grammar]] based, very parametric generative device for [[Evolutionary Algorithms]]

## Other noteworthy points 
- naming: multi-patterns similar to paper tapes of a programmable music box

## Results
- An extremely expressive generative device for polyphonic rhythmic musical patterns is presented. 
	- Clever declarative design of *bud generative systems* allows 

## Future Work
---
- A simple way of integrating this with deep learning could be to use the language defined by the possible [[Bud Generating System]]s as a meta-grammar in an adaption of [[Learning Compositional Rules via Neural Program Synthesis]] 
- Use a [[Probabilistic Grammar]] for the generation 
	- If the probabilities could be learned (e.g. by a neural network) this would be a powerfull #neuro-symbolic system! Due to the extremely expressive explicit formulation, it could be possible to ground on this a system, which learns very quickly (modifying weights at apropriate levels of abstraction). 
- Make an #interactive composition system, where the system proposes well-chosen tunes and updates its possibility space through user feedback (proposing the most designative options *and* modifying the generative device can both be learned).
- Incorporate additional information into the representation (velocity, instrument specific expressivity)
- Model proper rests in contrast to sustained notes.


## Errors
- In (22) the index of the composition is 1-based, everywhere else it's 0-based?




[^1]: The notion that through patterns, data and function-on-data become the same seems very powerful for generative systems.


[^5]: S. Giraudo. Colored operads, series on colored operads, and combinatorial generating systems. Discrete Math., 342(6):1624–1657, 2019.

[^8]: J. E. Hopcroft, R. Matwani, and J. D. Ullman. Introduction to Automata Theory, Languages, and Computation. Pearson, 3rd edition, 2006.

[^12]:  D. Yau. Colored Operads. Graduate Studies in Mathematics. American Mathematical Society, 2016.

[^@giraudoGenerationMusicalPatterns2021]: Giraudo, Samuele. 2021. “Generation of Musical Patterns Through Operads.” arXiv. [https://doi.org/10.48550/arXiv.2104.12432](https://doi.org/10.48550/arXiv.2104.12432).


