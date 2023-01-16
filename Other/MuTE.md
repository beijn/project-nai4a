## Pitch-time grid corespondence of attributes [^@goverMusicTranslationGenerating2022]

![[Music Translation - Figure 3.png]]

The *MuTE Evaluation Metric* compares generated music with a ground truth. It is the [[F1 score]] over time-step-sequences of all-active-pitches-tokens. To preserve order and timing, time-step-wise scores are averaged.

## In [[Music Translation]]
- Skipped or added measures are identified by automatic alignment of bars (because model based on bars) through comparison of pitch-class piano-rolls. 
- Consider hands separately and average.

## On [[BLEU]]
BLEU is a similarity metric in machine translation that uses *precision on n-grams*.
- = how many of the predicted n-sequences of tokens are present in any reference translation
- but not recall, because *false negative n-grams* don’t make sense in the presence of multiple possible references 
	- sequences of n words that are not predicted but appear in the reference 
	- an n-gram may match not all reference translations but may still be preferable.

## Caveats
- sustained notes equal repeated notes (half = quarter + quarter)
- valid variations disallowed (octave transposition, rhythm, {harmonically valid complementation})

[^@goverMusicTranslationGenerating2022]: Gover, Matan*, and Oded Zewi. 2022. “Music Translation: Generating Piano Arrangements in Different Playing Levels.” In _Proceedings of the First MiniCon Conference_. [https://ismir2022program.ismir.net/poster_37.html](https://ismir2022program.ismir.net/poster_37.html).