
## Bayes’ Theorem

![[Bayes.svg]]

$P(H|E)=\frac{P(H\cap E)}{P(E)}=\frac{Both}{\text{Evidence}}=\frac{P(E|H)\ P(H)}{P(E)}=\frac{\text{Likelihood}\ \cdot\ \text{Prior}}{\text{Evidence}}$
self-made graphic

## Idea
Alternative / complementary formulations:
- The known probability of some hypothesis $H$ can be informed *a posteriori* by the probability of some related evidence $E$ and the knowledge of its happening. 
- The presence of some evidence $E$ restricts the possible worlds with respect to a hypothesis $H$ and one should know how. 
- The $P$robability of $H$aving corona g$|$ven a positive t$E$st is the probability of both in co$\cap$junction dev$/$ded by the probability of seeing the $E$vidence at all (without respect to any other information), devided since we know we live in one of the worlds where the evidence occurs. 
- From all the possible worlds where the $E$vidence occurs (no matter if its intended implications hold or not) we zoom in on the subset in which the $H$ypothesis holds as well. This subset of worlds in which $H$ypothesis a$\cap$d $E$vidence are given is as probable as \[the *Likelihood* of having the evidence *cond$|$tioned* on the holding of the hypothesis] a$\times$d the holding of the $H$ypothesis in general (*prior* to consideration of evidence). 
- $H$aving corona a$\cap$d a positive t$E$st is \[to have a positive test dur$|$ng having corona] a$\times$d having corona *prior* to knowing Bayes. 
- $E$vident that it was sunny y$E$sterday makes it more probable to have sunshine $H$eute *a posteriori* as well, than it would be *prior* to knowing y$E$sterdays weather, considering that $H$eute’s weather also has something to say about the likelihood of its caus$E$.

## In #conditional #generation 
In [[VQ-VAE]] the word *prior* is used to denote the distribution in latent space from which can be sampled and decoded. This technique is used at the core of [[Symbolic Music Loop Generation]]. 

## Bayesian models
#wip
Besides [[Deep Learning]] and [[Evolutionary Algorithms]] methods of Bayesian statisics form a main branche of AI and generative modelling. The idea is to enable deep probabilistic reasoning by chaining the above formula for conditional probability. This enables [[Explainability vs Explain-Ability|Explainability]] in the sense that reasoning is hierarchical. 

### Hierachical Dirichlet Process Gaussian Mixture Models
Proposed in [^@kimPowerDeepGoing2022] at #ISMIR 2022 ([see poster, paper and video](https://ismir2022program.ismir.net/poster_234.html)) as a powerfull and explainable model for music. Seems like a very prospectfull research direction. 
- Hierarchy in this case means that score-level distributions are conditioned by global distributions across corpora.
- The nature of Dirichlet Processes (see below) lets the model infer the optimal number of components to represent a peice, wheras most neural architectures are fixed in their latent space dimensionality.
In [^@paisleyNestedHierarchicalDirichlet2015] an apperently more general version is proposed, which is even more flexible in that it seems to be able to infer the optimal depth of the hierachy. It has to my knowledge not been applied to music. 

### Gaussian Mixture Models
-  Fitting a mixture model is to find the parameters of a given number of given distributions (in a Gaussian mm that's Gaussian=normal distributions) that maximizes the probability that the data was drawn from their superposition.
### Dirichlet Processes 
- Distributions over distributions in arbitrary dimensionality: A draw from a dirichlet process is a discrete distribution over *customizably many dimensions*.
- Has been used previously in [[Latent Dirichlet Allocation]] models: 
- Allow adaptive inference of optimal number of components.


---
**see**: [a video](https://www.youtube.com/watch?v=NIqeFYUhSzU)



[^@kimPowerDeepGoing2022]: Kim, Jaehun*, and Cynthia C. S. Liem. 2022. “The Power of Deep Without Going Deep? A Study of HDPGMM Music Representation Learning.” In _Proceedings of the First MiniCon Conference_. [https://ismir2022program.ismir.net/poster_234.html](https://ismir2022program.ismir.net/poster_234.html).

 [^@paisleyNestedHierarchicalDirichlet2015]: Paisley, John, Chong Wang, David M. Blei, and Michael I. Jordan. 2015. “Nested Hierarchical Dirichlet Processes.” _IEEE Trans. Pattern Anal. Mach. Intell._ 37 (2): 256–70. [https://doi.org/f622wh](https://doi.org/f622wh).
