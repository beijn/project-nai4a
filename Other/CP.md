# Compound Word Representation
## group tokens by families for multiple parallel sequences per information type [^@hsiaoCompoundWordTransformer2021]

![[Compound Word Transformer - Figure 2.png]]

for only known application to date (23/01) see [[Compound Word Transformer]], 

- Event-wise related tokens are vertically grouped and tagged (e.g. metric- vs note related).
- Different attention heads can operate in parallel on the subsequences given by only the tokens of each type. To align those, most tokens in each are skips. Linear projections yield a token for each type per transformed compound representation (→ multiple tokens predicted at once). 
- First a group tag (“family“) is predicted, from this thereafter the other tokens. 
- Each type specific attention head can be independently customized (losses, dimensionalities, sampling)

## Context 
- inspired by [[Adaptive Input Representation]][^1] in NLP 
- kind of compressive memory as in [^2], but during present and not past

[^1]: Adaptive Input Representations for Neural Language Modeling,
Alexei Baevski, Michael Auli, https://arxiv.org/abs/1809.10853

[^2]: Rae, J. W.; Potapenko, A.; Jayakumar, S. M.; Hillier, C.; and Lillicrap, T. P. 2020. Compressive Transformers for longrange sequence modelling. In Proc. Int. Conf. Learning Representations.

[^@hsiaoCompoundWordTransformer2021]: Hsiao, Wen-Yi, Jen-Yu Liu, Yin-Cheng Yeh, and Yi-Hsuan Yang. 2021. “Compound Word Transformer: Learning to Compose Full-Song Music over Dynamic Directed Hypergraphs.” _Proceedings of the AAAI Conference on Artificial Intelligence_ 35 (1, 1): 178–86. [https://doi.org/grmj2g](https://doi.org/grmj2g).