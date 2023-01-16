
Abstraction is hierachical nesting of information, most deep learning model's is a flat sequence of number without relation. Can we generalize from latent sequences to graphs?

## Deep Learning is flat
- The latent space of most [[Deep Learning]] models is *flat*. 
- At the same moment, abstraction is a hierachical, recursice process. Latent space is usually a sequence or an array of values, without possibility to explicitely specify any structure or relation. This is only implicitey realized by the decoder parts (read further).
- Hierarchy and interdependence are nonetheless somewhat implicitely covered in most succesfull deep learning models, as has often been shown for e.g. #CNN s [see NAI Lecture 12, Vicente 2022]. 
- Something similar applies to [[Transformer]]s, which model interdependence of latent tokens' meanings through attention. The multiple attention layers have been shown to capture different kinds of abstraction. 
- Together with the fact that e.g. programming languages demonstrate how finite, a-priori unnested, sequences of tokens can express arbitrarily complex, nested and self-referential structures, [[Transformer]]s can be seen as fuzzy interpreters and the need for explicit latent structures seems to vanish. 
- Yet as is shown 
- The [[Differential Neural Computer]] [^@kolevNeuralAbstractReasoner2020] has a notion of recursive data structures with flexible edges
	- an attention matrix is applied to every vector in the infinitely growable store
	- (an attention matrix that)
	- It is very recent, solves the [[Abstract Reasoning Challange]] very well, has not been applied to musc and thus appears like a very fruitfull future direction

## [[Bayesian Statistics#Hierachical Dirichlet Process Gaussian Mixture Models]] 



[^@kolevNeuralAbstractReasoner2020]: Kolev, Victor, Bogdan Georgiev, and Svetlin Penkov. 2020. “Neural Abstract Reasoner.” [https://doi.org/grbx38](https://doi.org/grbx38).