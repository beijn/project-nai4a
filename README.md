# A Field Guide to Symbolic Music Representation Learning

\* best before next year. Download and interactively explore and expand from with obsidian [here](https://github.com/beijn/project-nai4a). 

Benjamin Eckhardt, Artificial and Natural Intelligence 2022/2023 (LTAT.02.024) @ University of Tartu

This is a web of knowledge of state of the art (23/01) approaches to computational musicology with a focus on generative and neuro-symbolic systems. It can be navigated by clicking on the cross-links (though most sadly remained placeholders) or #tags or by navigating the folder structure.  Each of the notes under 
- "Application Papers/" details a full recent paper, mainly following the same structure (best to be discovered, see e.g. [[ComMU]]).
- "Summaries and Conclusions/" tries to bring together related concepts from a higher point of view (like [[Evaluation]]) and draws overaching (sub-)conclusions (like [[Explainability vs Explain-Ability]]).
- "Other/" and "Tasks/" contain a specific concept, technique or encoding and task respectively.
Most notes include a core sentence at the top, summarizing the central idea / value proposition. All notes include references.

- Less polished material on relevant #symbolic and #neuro-symbolic approaches (mostly in the domain of language and abstract patterns) is to be found in "Checkpoint II.pdf".  This includes the [[Differential Neural Computer]] and [[VQ-VAE]](-II) architecturs. 
	- I did it for this course, but it hasn't made it into this final knowledge web, please see the [[A Field Guide to Symbolic Music Representation Learning#Checkpoint II|disclaimer below]].
- Entry material on human and AI #cocreativity (in the domain of images), including [[Meaningful Human Control]], [[Latent Space]] and [[VAE]] is to be found under "Previous Work/".
	- *It was for another course*, please see the [[A Field Guide to Symbolic Music Representation Learning#Previous Work on Human+AI Creativity|disclaimer below]].

Final conclusions are to be found in [[Explainability vs Explain-Ability]], [[Conclusion]] and [[A Field Guide to Symbolic Music Representation Learning#Future Directions and Spinoff Project Ideas]].


### No stub notes and secondary literature
To streamline the presentation, concepts that are used only once are explained at that location (against the spirit of Obsidian).
Some secondary references, which were mentioned in the primary literature only with respect to one specifc concept and seemed of limited relevance to be read and understood, have their citations been copied from the primary literature. 




## Future Directions and Spinoff Project Ideas
The *Future Work* sections of each review give points where one could continue expanding the work in relatively obvious directions. Below the horizontal lines, I have mentioned my ideas of how to expand on the respective work (only when not mentioned by the respective authors). Besides these, here are some of the bigger ideas I came up with. *Checkpoint II* contains more, but in less polished form. 
Besides these, several novel powerful architectures (that are not primarily [[Transformer]]s) have yet to be applied to music:
- [[Differential Neural Computer]][^@kolevNeuralAbstractReasoner2020], see [[Hierarchical Latents]]
- [[Hierarchical Dirichlet Process Gaussian Mixture Models|Hierachical and Nested Dirichlet Process Gaussian Mixture Models]] [^@kimPowerDeepGoing2022] [^@paisleyNestedHierarchicalDirichlet2015], see [[Bayesian Statistics#Hierachical Dirichlet Process Gaussian Mixture Models]]

While music exhibits complexely nested and self-referentially recursive structure, the latent space of current models has been inherently flat, see [[Hierarchical Latents]]. Above models provide prospectful directions of breaking up this flat plane.

This models' internal inductive bias is mirrored by the modelling aims that give rise to them: Most reviewed research has only come so far as to treat repetition as the embodiement of musical stucture (see [[Symbolic Music Loop Generation]] and [[Detecting Symmetries of All Cardinalities]]). An approach that incorporates more complex nested structure in their theoriy comes from [[Algebra]] ([[Generation of Musical Patterns through Operads]]).

Other project ideas include:

### [[Meaningful Human Control]] over musical [[Latent Space]] / Latent knobs
- If music is represented as a latent graph (even just a linear one (= sequence), or a single vector), one should be able to tune those values to excert [[Meaningful Human Control]] [^@aktenDeepVisualInstruments2021] in a models expressive latent space. 
- A single vector with hundreds of dimensions is incomprehensible, and thus meaningful human control becomes very difficult.
- Encouraging the latent representations to be disentangled could (maybe) be a prerequisite for a human to understand the controls by associating discrete concepts with each dimension. 
A project could explore whether disentangling or otherwise processing of latent vectors makes a difference in the likeliness of understandable concepts emerging. As well as the merits of distributing the code among multiple lower dimensional vectors, for example per structural unit of a piece.


### Information Content in Music Transformer Tokens
Similarly to the proposed project with visual transformer tokens, one could study
This is very interesting and could provide a more in-depth understanding of the capabilities ob recent music models, compared to just evaluating their outputs, as it could guide meaningful exploration of the design space. Yet, latent music representations are very understudied. 


## Related Work 
### Disclaimer on the scope of the presentation
I ran out of time. I have invested well over 70 hours, but struggling a long time to settle on a concrete plan, a big part of that was spent in blocks of different topics and research methodologies. Very interesting (though in volume much less) research in [[Evolutionary Algorithms]] has not been captured here, though it had a great impact on my interal idea space. Very unfortunately, I haven't managed, to transfer most of that work over to presentation in this work. This is because the process of converging on this presented format was very long and involved going over the same literature over and over. Most annoyingly it meant rereading a lot of material, sometimes multiple times, as my demands on content detail expanded. Calculating with the required energy of improving the representation of recently read papers, that of completely redoing the work on previously read papers (Checkpoint II), the energy it gives me to read a new fascinating paper, and the pain of leaving too much previous work unused, I settled for this. This is a small set of overly work-intensive presentations of the most relevant recent computational musicology papers.
- I invested quite a lot of time into understanding [[Hierarchical Dirichlet Process Gaussian Mixture Models]] and the like, but unfortunately, lacking a proper background in machine learning basics or probability theory, I did not quite converge to a general understanding before I had to focus on nearer things. I wrote down some intuitive definitions and consider this a very promising direction. (see [[Bayesian Statistics]] for drafts)

### Checkpoint II
In "Checkpoint II.pdf" several (less detailed and less accessible) reviews of papers relating to more #symbolic systems are collected. This includes recent work on the [[Abstract Reasoning Challange]], which provides state of the art neural, symbolic and hybrid approaches to complex patterned transformations aka reasoning. As detailed, the MIR community (as of early 2023) has recently mainly focussed on adapting deep neural networks like [[Transformer]]s. The paper selection in Checkpoint II could therefore provide new research directions, especially the [[Differential Neural Computer]] contains untapped potential. Recent work on (re-)introducing #grammar based approaches to (simple) language modelling in *[[Learning Compositional Rules via Neural Program Synthesis]]*. 

### Previous Work on Human+AI Creativity 
The folder *Previous Work* includes course work done for *another course*. It relates highly to my work here (as I realized in the end), but I wheighted the benefit of doubling the work to copy it over into this knowledge web relatively low, while there were more prospectful candidates both for improvement and novel reading. **It is submitted for the benefit of comilitons, not to be graded as work for this course.** It is kindly recommended as an entry to the topic of Human and AI #cocreativity based on the concepts of navigation in [[Latent Space]], most accessible through the therin presented [[VAE]], and [[Meaningful Human Control]].





## Ethical Statements

### On the cultural bias of *Western* music
The author has not invested into expanding his horizon beyond western music tradition. The music which is targeted in the works picked up by this one is dominantly western. I stress that other kinds of music, coming with ways to systematize than wester #music-theory, must exist in the world and that the fact that it is so marginalized is a consequence of post colonialism. *This work likely takes part in reenforcing this marginalization, by reflecting work targeting specifically "western" music. Especially because not even glimpsing at other cultures. None less because it was uninented.* Science and innovation that narrow their gaze down to a specific culture, for whatever unscientific reason, directly contribute to reinforcing this culture's imperialism, through a multitude of obvious and less obvious ways. This holds especially when paired with economic interests, like a big part of contemporary research in AI music. 

### Human Work
This work was done by a human with limited AI assistance. Every presented article was read by me (for details on secondary references, see above). AI was used only (mostly in form of TLDR;s and recommendations of related papers) through several mainstream literature websites like Semantic Scholar and Google Scholar, and for spelling.




[^@aktenDeepVisualInstruments2021]: Akten, Memo. 2021. “Deep Visual Instruments: Realtime Continuous, Meaningful Human Control over Deep Neural Networks for Creative Expression.” [https://doi.org/gq9654](https://doi.org/gq9654).


[^@hernandez-olivanMusicaizPythonLibrary2022]: Hernandez-Olivan, Carlos, and Jose R. Beltran. 2022. “Musicaiz: A Python Library for Symbolic Music Generation, Analysis and Visualization.” [https://doi.org/grmp4f](https://doi.org/grmp4f).

[^@kolevNeuralAbstractReasoner2020]: Kolev, Victor, Bogdan Georgiev, and Svetlin Penkov. 2020. “Neural Abstract Reasoner.” [https://doi.org/grbx38](https://doi.org/grbx38).

[^@kimPowerDeepGoing2022]: Kim, Jaehun*, and Cynthia C. S. Liem. 2022. “The Power of Deep Without Going Deep? A Study of HDPGMM Music Representation Learning.” In _Proceedings of the First MiniCon Conference_. [https://ismir2022program.ismir.net/poster_234.html](https://ismir2022program.ismir.net/poster_234.html).

[^@paisleyNestedHierarchicalDirichlet2015]: Paisley, John, Chong Wang, David M. Blei, and Michael I. Jordan. 2015. “Nested Hierarchical Dirichlet Processes.” _IEEE Trans. Pattern Anal. Mach. Intell._ 37 (2): 256–70. [https://doi.org/f622wh](https://doi.org/f622wh).


[^librosa]: McFee, Brian, Colin Raffel, Dawen Liang, Daniel PW Ellis, Matt McVicar, Eric Battenberg, and Oriol Nieto. “librosa: Audio and music signal analysis in python.” In Proceedings of the 14th python in science conference, pp. 18-25. 2015.
