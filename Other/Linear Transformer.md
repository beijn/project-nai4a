## Attention in linear time

For transformers and attention, please refer to other sources like https://jalammar.github.io/illustrated-transformer/, or your favorite lecture.
This note is a quick reference to recent *linear* attention transformers and an even more recent improvement.
A slightly improved transformer is also presented in [[The Piano Inpainting Application]] (Section 3.2.1).



# Linear Transformer
## Transformers are RNNs
### Fast Autoregressive Transformers with Linear Attention

[^@katharopoulosTransformersAreRNNs2020], #MLR 2020
Also called *kernel based attention*.
- Attention in linear space and time, by mathematically generalizing vanilla softmax attention, and re-specifing it with few assumptions.
- As an #autoregressive sequence model, the memory need is constant and the equivalence to specific RNNs is shown.

- Linear attention has been developed concurrently in [^@zhuoranEfficientAttentionAttention2021] (but without the RNN parallelism)
- Several other improvements on transformers are contextualized in section 2.1 of [^@katharopoulosTransformersAreRNNs2020]
- Related work also includes mentions of previously found parallelity between [[Transformer]]s and [[CNN]]s

## The Devil in Linear Transformer
[@qinDevilLinearTransformer2022], #EMNLP 2022
[source and (pictographic) explanation](https://github.com/opennlplab/transnormer)

- Other work has shown that [[Linear Transformer]]'s few assumptions for linear attention are too much - predictive performance and generalizability suffer, while higher compute efficiency is increased.
- This very recent and apparently uncited study presents
- improvements both in (predictive) performance bottlenecks of linear transformers and achieves both superior (compute) efficiency and performance on huge sequences is







[^@katharopoulosTransformersAreRNNs2020]: Katharopoulos, Angelos, Apoorv Vyas, Nikolaos Pappas, and François Fleuret. 2020. “Transformers Are RNNs: Fast Autoregressive Transformers with Linear Attention.” In _Proceedings of the 37th International Conference on Machine Learning_, 5156–65. PMLR. [https://proceedings.mlr.press/v119/katharopoulos20a.html](https://proceedings.mlr.press/v119/katharopoulos20a.html).

[^@zhuoranEfficientAttentionAttention2021]: Zhuoran, Shen, Zhang Mingyuan, Zhao Haiyu, Yi Shuai, and Li Hongsheng. 2021. “Efficient Attention: Attention with Linear Complexities.” In _2021 IEEE Winter Conference on Applications of Computer Vision (WACV)_, 3530–38. [https://doi.org/10.1109/WACV48630.2021.00357](https://doi.org/10.1109/WACV48630.2021.00357).


[^@qinDevilLinearTransformer2022]: Qin, Zhen, XiaoDong Han, Weixuan Sun, Dongxu Li, Lingpeng Kong, Nick Barnes, and Yiran Zhong. 2022. “The Devil in Linear Transformer.” [https://doi.org/grmkqq](https://doi.org/grmkqq).