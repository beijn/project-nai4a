
Evaluation of generated music is an open problem[^35]. This is only partly because there are many aspects of music generation one could value, like the Coherence-vs-Diversity trade-off. Nearly all papers in this review propose different evaluation schemes, often mutliple at once, capturing different complementary desiderata and intents, like different types of infromation given in conditional generation. See the respective subsections.

## Similarity of notes

- [[Compound Word Transformer]] splits the evaluation between melody and harmony, as suggested by the fact that their reference (for conditional MIDI generation), leadsheets, are built on this distinction. 
	- An obvious caveat of their LCS approach to melody seems to be, that wrongly inserted notes get ignored. A set of wrong notes could have disruptive effect on the melody without being regarded by this metric (as only matching notes count).
	- It seems likely that the [[Chroma Vector]] based harmony part of the metric would not be fully sensitive to this, as the disruptive effect can be located in just a small-time slice. 
	- The cosine similarity of [[Chroma Vector]]s is a simple and useful baseline for harmony, but other than octave invariance it is uniformed of music theory - certain notes missing or added are perceived to make a much greater difference in a cadence than others (consider removing the fifth vs adding a tritone).

- [[MuTE]], newly proposed in [[Music Translation]], is more similar to the harmony metric in [[Compound Word Transformer]], but denying octave invariance and with the major difference of an [[F1-Score]] instead of #cosine-similarity between the pitch vectors. MuTE appears because of its simple structure, readily suited for settings where notes have more attributes (in the case of [[Music Translation]] the *hand* which plays a note; especially timbre / instrument seems interesting).

- Even more features describing single bars are automatically extracted in [[FIGARO]] and successfully used for model training and evaluation.


## Diversity

## Quality



[^35]: Shih-Lun Wu and Yi-Hsuan Yang. The jazz transformer on the front line: Exploring the shortcomings of ai-composed music through quantitative measures. International Society for Music Information Retrieval (ISMIR), 2020.
