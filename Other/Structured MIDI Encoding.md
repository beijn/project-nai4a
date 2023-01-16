## Notewise pitch, velocity, duration and *time shift* [^@hadjeresPianoInpaintingApplication2021]

![[The Piano Inpainting Application - Figure 2.png]]

- Each note is always represented by four consecutive ordered tokens indicating its pitch, velocity, duration and *time shift*. 
- The *time shift* is the time elapsed between this note's and the next's onset. It provides structure in time different from duration and polyphony (e.g. if set to 0).

## On [[MIDI]]
Separation of note-on and note-off events 
- complicated *nested* structure
- possibly syntactically *ill-formed* sequences generation
- note duration is *implicit* in time shift events between note-on and -off

## On [[REMI]]
- both use a *note duration* token instead of *note-off* to improve uppon MIDI
- REMI has no relative *time shift* token, but a beat-in-bar related absolutish *position* token
- REMI is *less general* as it needs a beat, chord or tempo tokens. (Though those can be easily inferred with existing methods as shown in [[Compound Word Transformer]] and I would assume a great generalization error on all music, for which this is impossible.)
- REMI's additional tokens impact the structuredness of the input and thus assumptions that (presumably) performant models as in [[The Piano Inpainting Application]] rely on. (A different solution for improving the structure while preserving many informative token types is by vertical grouping in "families" as in [[CP]].)

## On [[CP]]
- similar way of deviding large input alphabets into multiple smaller ones, and operating distinctly on those types
- CP achieves higher flexibility by grouping more different kinds of tokens (lile beat/bar and chord as above) by grouping in distinct "families"
	- family tokens condition the model on the types of tokens to produce to nudge-in the more flexible structure
---
- To adapt [[Inpainting]] as in [[The Piano Inpainting Application]] for CP, don't mix up constraining *ignore* and unconstrained *paint-this-in* tokens.


[^@hadjeresPianoInpaintingApplication2021]: Hadjeres, Gaëtan, and Léopold Crestel. 2021. “The Piano Inpainting Application.” arXiv. [https://doi.org/10.48550/arXiv.2107.05944](https://doi.org/10.48550/arXiv.2107.05944).