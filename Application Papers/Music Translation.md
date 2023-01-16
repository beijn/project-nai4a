# Generating Piano Arrangements in Different Playing Levels
## different piano playing levels with same content

[^@goverMusicTranslationGenerating2022], #ISMIR 2022 
[paper, poster and video](https://ismir2022program.ismir.net/poster_37.html)

| Figure 1                              | Figure 3 |
| ------------------------------------- | -------- |
| ![[Music Translation - Figure 1.png]] | ![[Music Translation - Figure 3.png]]

## Motivation
- Translate between difficulty levels of an arrangment 
-  [[Meaningful Human Control|Interactivity]] through [[Conditional Generation]]

## Tasks
- [[Music Translation]]:
	- #sequence-to-sequence translation of #symbolic #music between different difficulties while preserving content; #supervised

## Ideas
- Create pairs of #human-expert made #piano #arrangments in different difficulty levels 
- *Hand* as additional information per note in input representation,
	- else duration based (offset, pitch, duration) [[REMI]] without special tokens like *chord* or *beat*
- A [[Transformer]] ([[BART]]) trained #sequence-to-sequence on pairs of corresponding phrases
	- BART has something with special learned position embeddings
- Align musical phrases with handcrafted heuristics and expert annotations
	- #transposition heuristic: time × pitchclass × (0,1) matrices are transposed ($O(11)$) until best match
- [[MuTE#In Music Translation]] evaluation metric captures #alignment of notes between target and source sequence
- limited [[Meaningful Human Control]] 
	- through modification of generated notes and conditional regeneration of some rests
	- choose among different variants
	- or manipulate probabilistic parameters which leads to the [[Evaluation]] trade-off

## Data
- #data-augmentation:
	- *chopping*: add empty measures and remove measures (needs #alignment afterwards)
	- *time dilation*: rhythmic elongation by multipying 
* **no** transposition as that contains relevant info impacting the difficulty level (more or less black keys)

## [[Evaluation]]
- [[MuTE]] is proposed

## Other noteworthy points
- the Paper is very thorough in explanation of methodology, detailing reasoning, experiments and ablation studies on their design decisions. 
- Opensourced [[MuTE]] and #data-ugmentation code.

## Results
- generation with [[Beam Search]] yields better results but less diversity than [[Sampling]] (→ [[Evaluation]])
- Automatic rearrangements (from intermediate to easy) are competitive to human ones. 
- [[MuTE]] correlates (0.56) with overall similarity rating by humans.
- In an ablation study, specific changes in data representation are shown to coincide with changes in specific human metrics.

## Future Work
- see [[MuTE#Caveats]]
---
- Provide more [[Meaningful Human Control]] over the generation process by meaningfully manipulating latent codes. E.g. by pulling apart latent codes for music content and style. Style could encode different accompaniment schemes.


[^@goverMusicTranslationGenerating2022]: Gover, Matan*, and Oded Zewi. 2022. “Music Translation: Generating Piano Arrangements in Different Playing Levels.” In _Proceedings of the First MiniCon Conference_. [https://ismir2022program.ismir.net/poster_37.html](https://ismir2022program.ismir.net/poster_37.html).