## Inpainting of specified note(-attribute)s
[^@hadjeresPianoInpaintingApplication2021]
[page](https://ghadjeres.github.io/piano-inpainting-application/) [source](https://github.com/Ghadjeres/piano-inpainting-application)

![[The Piano Inpainting Application - Figure 3.png]]

## Motivation
- [[Meaningful Human Control|Artistic control]] over #generative models
- Classic [[Transformer]] in combination with #MIDI is too slow and suffers from limited #long-term-coherence 

## Tasks
- [[Inpainting]] ([[Conditional Generation]]) of slices, specific notes or *specific note-attributes* based on number; variation
- [[Unconditional Generation]]

## Ideas
- [[Structured MIDI Encoding]] proposed, to enhance input structure (see Appendix B). 
	- Holes are marked with special (**N**on **C**onstraint) tokens
		- *Number of notes in a given timeframe needs to be specified precisely*
		- desired notes and even *specific note attributes* can be inpainted
	- allows *factorization of positional embeddings* into channel (token #type), corresponding note index and total elapsed time (see Appendix A)
- [[Transformer]] provide fast [[RNN]]-like conditional generation (reactive inpainting); long sequence context; while in contrast to [[RNN]]s predicting on all timesteps in parralel 
	- Improvements (see Section 3.2.1)
	- synergizes with sMIDIe for *highly efficient*
		- *training* with *[[Causal Attention#Anti-Causal|(anti-)]] [[Causal Attention|causal masking]]* 
		- *inference* through parallel encoding and [[Transformer#RNN-like inference|RNN-like iterative inference]]
		
## Context 
- Control over conditional generation, previous research listed in *Introduction*:
 	*continuation of a priming section [22, 14, 15, 12] : harmonization [10, 14], variation of an input sequences [9, 7], interpolation between two fragments [23], or mapping of a musical gesture to a performance [5].*
- Previous inpainting methods assume simpler, less flexible data representations (like heavily quantized and monophonic)
### On [[Compound Word Transformer]] 
- see [[Structured MIDI Encoding#On Compound Word Representation]]
- similar in having multiple attention heads per token type
- authors believe CWT's (relatively) independent generation of multiple tokens at once is a limitation

## Data
- MIDI from [[GiantMIDI-Piano]] (split (90,10,**0**)) 
- augmented
	- multiplicative dilation of time, additive shifts in velocity and pitch\*
	- adaptive quantization as proposed in [^4]. Almost imperceptible (see Appendix B)
- translated into [[Structured MIDI Encoding]]. 

## Other noteworthy points 
- Plugin for a commercial DAW 

## Results
- *No quantitative evaluations are given.* But reasoning and playful experiments
- Generates *variations* when sequence is fully constrained (see Section 3.3.4) ([[Resampling]])
- the described tool

## Future Work

--- 
* apply inpainting to an even more flexible representation such as [[CP]] (the synergies between this model and [[Structured MIDI Encoding]] appear parallelable)


## Remarks
\* I would assume that the augmentations are applied uniformly over a score, else its structure gets heavily corrupted


[^4]: C. Donahue, H. H. Mao, Y. E. Li, G. W. Cottrell, and J. McAuley. Lakhnes: Improving multi-instrumental music generation with cross-domain pre-training. arXiv preprint arXiv:1907.04868, 2019.



[^@hadjeresPianoInpaintingApplication2021]: Hadjeres, Gaëtan, and Léopold Crestel. 2021. “The Piano Inpainting Application.” arXiv. [https://doi.org/10.48550/arXiv.2107.05944](https://doi.org/10.48550/arXiv.2107.05944).