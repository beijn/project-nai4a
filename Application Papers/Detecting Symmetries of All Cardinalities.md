# With Application to Musical 12-Tone Rows
## interval repetitions in 12-tone rows
[^@venkateshDetectingSymmetriesAll2022], #ISMIR 2022
[poster, paper and video](https://ismir2022program.ismir.net/poster_133.html)
![[Detecting Symmetries of All Cardinalities - Figure 3.png]]

## Motivation / Task
- prove that composers have a bias towards "symmetry" in 12-tone-rows
	- thus computer a measure of symmetry from 12-tone rows\*

## Ideas
Geometrical definition of *symmetry* 
- Count every possible repetition of interval chains in 12-tone rows\*.
	- Chains of any length (⇾ "symmetries of all cardinalities")
- Compute 4 previously defined symmetry metrics from these. (see paper)
- Show combinatorically how likely intentional the symmetries are across corpora of 3 different composers 12-tone rows. 

## Inductive Biases
- music = 12-tone-rows\*
- #symmetry = strict repetition of intervals in #12-tone-rows

## Results
- previous estimates of symmetry across corpora reproduced or improved → those 3 composers employ “symmetry“ extensively

## Future Work
- the “$n$\-tuple symmetry score“ could generalize to other structures like #rhythm and #melody (while the “hypereometric test“ for probability of these won't?)

## Remarks
\* apparently they work only on pregiven 12-tone rows, which are structures associated with (regularities in) specific musical compositions. No machine learning involved, only combinatorics/geometry/…


[^@venkateshDetectingSymmetriesAll2022]: Venkatesh, Anil*, and Viren Sachdev. 2022. “Detecting Symmetries of All Cardinalities With Application to Musical 12-Tone Rows.” In _Proceedings of the First MiniCon Conference_. [https://ismir2022program.ismir.net/poster_133.html](https://ismir2022program.ismir.net/poster_133.html).