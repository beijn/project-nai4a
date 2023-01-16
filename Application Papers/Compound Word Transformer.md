# Learning to Compose Full-Song Music over Dynamic Directed Hypergraphs 
## compound tokens processed in parallel per type
[^@hsiaoCompoundWordTransformer2021], AAAI 2021
[page](https://ailabs.tw/human-interaction/compound-word-transformer-generate-pop-piano-music-of-full-song-length/) [source](https://github.com/YatingMusic/compound-word-transformer)

| Figure 1                                      | Figure 2 |
| --------------------------------------------- | -------- |
| ![[Compound Word Transformer - Figure 1.png]] | ![[Compound Word Transformer - Figure 2.png]]         |

## Motivation
- higher [[Transformer]] performace and throughput and more #context

## Tasks
- efficient music [[Tokenization]]
- #conditional and #unconditional #generation of full length piano MIDI with #long-term-coherence ( #unsupervised)

## Ideas
- [[CP]] increases structure, densitiy and parallelizability
	- Different [[Transformer#Attention Head]]s can operate in parallel on the subsequences given by only the tokens of each #type. To align those, most tokens in each are skips. Linear projections yield a token for each type per transformed compound representation (→ multiple tokens predicted at once). 
	- First a group tag (“family“) is predicted, from this thereafter the other tokens. 
	- Each type specific attention head can be independently customized (losses, dimensionalities, [[Sampling]])
- **Prefix LM Method**: interleaving of multiple sequences enables relation learning between two representations (here #piano performance and #lead-sheet)
	- For relation learning between two parallel musical sequences and related conditional generation. Each bar of the interleaved sequence is constituted of one corresponding bar of each sequence, prefixed with a special token indicating the source sequence. This effectively presents the interdependence of the sequences (here lead sheet and piano performance) and enables an “encoder free“ solution to the conditional generation task: using only a single transformer (first proposed in [^@raffelExploringLimitsTransfer2019]
- A [[Transformer]] for performance and #long-term-coherence through wider #context yields inprovements over [[Transformer#Trans]] / classical [[Transformer]]

## Data
- Data preparation done fully automatic (ignoring existing [[A Field Guide to Symbolic Music Representation Learning#Datasets|Datasets]]) from audio files: #transcription to #MIDI by [[Onsets and Frames]], for other steps see paper (including a custom [[Chord Recognition]] algorithm).

## [[Evaluation]]
### Matchness
Quantitative: “Matchness” of paino performance to lead sheet
- #melody: average of per bar [longest common sub-sequence](https://en.wikipedia.org/wiki/Longest_common_subsequence) of notes (by pitch and rough onset time) (in [[REMI]] format)
- #harmony: #cosine-similarities of [[Chroma Vector]]s of corresponding time slices
More automated features are used in [[FIGARO]].
A discussion relating this to [[MuTE]], the metrics in [[FIGARO]] and others is given in [[Evaluation]].

### Questionary 
Qualitative. 
- A #human-survey (with very little subjects and test data!)

## Other noteworthy points 
- All the data gathering is done with a combination of previous automated methods, agregating lots of annotations according to #music-theory, starting with simple #audio.
- The analogy of *learning on dynamic directed hyper-graphs* is left unused and without proper context.

## Results
- Though the selling point of [[Transformer]]s is the assumption-saving ability to operate on much longer sequences (in this case complete songs vs small fragments), the performance in this case is just “competitive” with respect to [[Transformer XL]][^34]. In conjunction with [[CP]] it is much faster in training and generation, given its explicitly synergizing design (for much longer sequences\*), yet it uses more GPU memory.\*\* 
- It remains a bit unclear which performance gain is due to the architecture or the representation.

## Future Work
*   Apply the idea of #compound-words to other domains of sequential tokens.
--- 
*   Choose different evaluation [[Evaluation]], like [[MuTE]].
*   Make a comparative study implementing recent improvements upon [[Linear Transformer#The Devil in Linear Transformer]] 
*   To better understand the merits of CP vs REMI and linear vs XL transformers, the combination CP+XL should be evaluated as well.
*   Maybe the idea of compound-wise attention heads can be used for polyphonic music, to process each voice in parallel.


## Remarks
\* It is unclear if the vastly larger number of (conditionally) generated tokens is related to the fact, that, after being fed through the transformer, most predicted tokens are (typed) “\[ignore]” tokens.
\*\* The higher memory requirements may stem from the fact that the sequence length is increased for the l.t. models. It is unclear why t. XL is not allowed such sequence length and memory for a fair comparison. Maybe the training time would be even higher for achieving the same loss.


[^@hsiaoCompoundWordTransformer2021]: Hsiao, Wen-Yi, Jen-Yu Liu, Yin-Cheng Yeh, and Yi-Hsuan Yang. 2021. “Compound Word Transformer: Learning to Compose Full-Song Music over Dynamic Directed Hypergraphs.” _Proceedings of the AAAI Conference on Artificial Intelligence_ 35 (1, 1): 178–86. [https://doi.org/grmj2g](https://doi.org/grmj2g).

[^@raffelExploringLimitsTransfer2019]: Raffel, Colin, Noam M. Shazeer, Adam Roberts, Katherine Lee, Sharan Narang, Michael Matena, Yanqi Zhou, Wei Li, and Peter J. Liu. 2019. “Exploring the Limits of Transfer Learning with a Unified Text-to-Text Transformer.” _ArXiv_, October. 

[^34]: Zihang Dai, Zhilin Yang, Yiming Yang, Jaime G Carbonell, Quoc Le, and Ruslan Salakhutdinov. Transformer-xl: Attentive language models beyond a fixed-length context. In Proceedings of the 57th Annual Meeting of the Association for Computational Linguistics (ACL), pages 2978–2988, 2019.
