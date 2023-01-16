# Dataset for Combinatorial Music Generation
## automated mainstream drag-and-drop composing from high quality metadata

[^@hyunComMUDatasetCombinatorial2022], #NIPS 2022
[NIPS workshop](https://nips.cc/virtual/2022/workshop/55747) [page and source](https://pozalabs.github.io/ComMU)

 ![[ComMU - Figure 1.png]]             

## Motivation
- Industrializable [[Meaningful Human Control|artistic control]] over #generative models (in preformatted mainstream domains)

## Tasks
- [[Combinatorial Music Generation]] ( #conditional) (training is #supervised)

## Ideas
- high quality #human-expert data with powerful domain specific constraints ("12 metadata")
- #autoregressive #sequence-completion (with [[Transformer-XL]][^34]) as a baseline to show potential
	- #teacher-forcing: #chord symbols are injected to intended positions during generation

## Inductive Biases
- music = [[Structure as Repetition|repeated]] overlay of unrelated, short, monophonic sequences. Relation only through common metadata in prompt. 
- The usual flatness concern in latent codes applies (see [[Hierarchical Latents]])

## Context
- see also [[ComMU Dataset]]
### On [[FIGARO]]
- similar in [[Description to Sequence]], but in FIGARO:
- description is automatically generated from a bigger (unsorted) dataset 
- using fewer assumptions 
	- and thus fewer description components
	- #per-bar, thus less overall structure, but more flexible
### On [[MMM]][^19]
- is the most similar in previous literature, but
- not feasable for [[Combinatorial Music Generation#Homophonic Composition]], because of no track role- nor chord-conditioning
- specialized for #resampling or [[Inpainting]]

## Data
- see [[ComMU Dataset]]
- #data-augmentation: with transposition and time dilation, yields ×60 data amount

## [[Evaluation]]
### Controllability 
- whether metadata information is faithfully adhered to
- determinable via simple algorithms, that heuristically extract information like note density, chords, tempo
### Diversity
- Sum of pairwise #cosine-similarity between [[Chroma Vector]]s ( #harmony) and [[Groove]][^37] ( #rhythm) across multiple generations from same metadata
### Fidelity
- #winrate between generated and real sample ( #human-survey)

## Results
- [[Sampling#Temperature]] controls a between trade-off Controllability and Diversity.
- [[Sampling#Top-K]] ([^32], [^33]) K-value has neglegible effect - unlike with text
	- due to smaller vocab size
- extended *chord symbols* and *track roles* are powerfull #conditioning, as shown by the #ablation-study

## Future Work
- to develop specific architectures for the structure of music rather than text


[^@hyunComMUDatasetCombinatorial2022]: Hyun, Lee, Taehyun Kim, Hyolim Kang, Minjoo Ki, Hyeonchan Hwang, Kwanho Park, Sharang Han, and Seon Joo Kim. 2022. “ComMU: Dataset for Combinatorial Music Generation.” arXiv. [https://doi.org/10.48550/arXiv.2211.09385](https://doi.org/10.48550/arXiv.2211.09385).



[^19]: Jeff Ens and Philippe Pasquier. Mmm: Exploring conditional multi-track music generation with the transformer. arXiv preprint arXiv:2008.06048, 2020.


[^32]: Angela Fan, Mike Lewis, and Yann Dauphin. Hierarchical neural story generation. In Proceedings of the 56th Annual Meeting of the Association for Computational Linguistics (ACL), pages 889–898, 2018. 

[^33]: Ari Holtzman, Jan Buys, Maxwell Forbes, Antoine Bosselut, David Golub, and Yejin Choi. Learning to write with cooperative discriminators. In Annual Meeting of the Association for Computational Linguistics (ACL), 2018.


[^34]: Zihang Dai, Zhilin Yang, Yiming Yang, Jaime G Carbonell, Quoc Le, and Ruslan Salakhutdinov. Transformer-xl: Attentive language models beyond a fixed-length context. In Proceedings of the 57th Annual Meeting of the Association for Computational Linguistics (ACL), pages 2978–2988, 2019.

[^37]: Simon Dixon, Fabien Gouyon, Gerhard Widmer, et al. Towards characterisation of music via rhythmic patterns. In International Society for Music Information Retrieval (ISMIR), 2004.
