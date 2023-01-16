# With Neural Discrete Representations
## detect and resample from highly corelated bars
[^@hanSymbolicMusicLoop2022], #ISMIR 2022
[materials and source](https://github.com/sjhan91/Loop_VQVAE_Official) [ISMIR workshop with poster and video](https://ismir2022program.ismir.net/poster_66.html)

| Figure 1                                           | Figure 3 |
| -------------------------------------------------- | -------- |
| ![[Symbolic Music Loop Generation - Figure 1.png]] | ![[Symbolic Music Loop Generation - Figure 3.png]]         |

## Motivation
- Automate production of loop based music.

## Tasks
- [[Loop Extraction]]: musical piece (analog/symbolic) → extract, embed and generate repeatable phrases; *semi-/unsupervised* 

## Ideas
1. Detect loops with [[Deep SVDD]][^dsvdd] (unsupervised one class / anomaly classifier) 
	- A loop is multiple roughly repeated bars.
	- The distance metric of a bar in a piece is a measure of how loopy it is in the piece. (*loop score*)
2. Embedded [[Autoregressive]]ly with a [[VQ-VAE]]
3. Sample in latent space with an [[Autoregressive]] (on-directional) sequence model ([[LSTM]])
	- VQ-VAE's quantized vectors are modelled as a sequence of descrete tokens.
	- Sampling in latent, decoded by VQ-VAE's decoder. Yields [[Creativity#Novel and Valuable|novel but similar]] loops.
	- [[Rejection Sampling]] based on loop scores

## Inductive Biases
- Flatness: Only repeating full bars relevant, non-repeating aspects of bars interpreted as noise and fractional or multiple bared loops unrecognized. Bar code flat. 
- [[VQ-VAE|Latent Quantization]]: enables sampling of code vectors from autoregressive sequence models, but reduces reconstruction fidelity (no intrinsic benefits of quantization shown, like e.g. out of domain generalization).

## Context
- Music domain independent: Loop detector operates on correlation matrices, which are computable from any representation. (Here trained on WAV correlations and tested on MIDI) 
- [[Autoencoder]] part bridges between any domain and latent space.

## Metrics
- Multiple complementary pairs of metrics for music fidelity and diversity are proposed. Refer to paper for details.

## Results 
- [[Deep SVDD]] can be used to discern any fuzzy binary class, here loops basd on correlation matrices
- [[VQ-VAE]] + [[LSTM]] enable sampling from a latent space of repeatable portions of music
- [[CNN]]-[[VAE]] baseline is better in reconstruction \*

## Future Work
- to enable multiple voices
--- 
- compare with a model, able to sample in *continous* latents of a CNN-VAE (see \*)
- test out-of-distribution generalization benefits from quantized latents (see \*)

## Remarks
\* [[VQ-VAE]] is apparantly only used to enable latent sampling by a token based model like [[LSTM]] (or probably in future work [[Transformer]]s). No analysis of the benefits of a VQ-VAE are given, like generalization or efficient learning.


[^dsvdd]: Deep SVDD is an architecture for deep outlier detection presented in [^@ruffDeepOneClassClassification2018]. The **Task** *Anomaly detection (AD) / one-class classification* is to discern unusual/anomalous samples in data. In an unsupervised setting it is assumed that the majority of the training data is non-anomalous, thus a volume (in any dimensionality) can be fitted to most reasonably include non-anomalous data and exclude likely "anomalous".



[^@hanSymbolicMusicLoop2022]: Han, Sangjun*, Hyeongrae Ihm, Moontae Lee, and Woohyung Lim. 2022. “Symbolic Music Loop Generation with Neural Discrete Representations.” In _Proceedings of the First MiniCon Conference_. [https://ismir2022program.ismir.net/poster_66.html](https://ismir2022program.ismir.net/poster_66.html).

[^@ruffDeepOneClassClassification2018]: Ruff, Lukas, Robert Vandermeulen, Nico Goernitz, Lucas Deecke, Shoaib Ahmed Siddiqui, Alexander Binder, Emmanuel Müller, and Marius Kloft. 2018. “Deep One-Class Classification.” In _Proceedings of the 35th International Conference on Machine Learning_, 4393–4402. PMLR. [https://proceedings.mlr.press/v80/ruff18a.html](https://proceedings.mlr.press/v80/ruff18a.html).