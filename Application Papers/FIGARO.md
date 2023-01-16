# Generating Symbolic Music with Fine-Grained Artistic Control 
## Bar-wise merged latent and natural codes to sequence [^@rutteFIGAROGeneratingSymbolic2022]

| Figure 1                   | Figure 2 |
| -------------------------- | -------- |
| ![[FIGARO - Figure 1.png]] | ![[FIGARO - Figure 2.png]]         |

## Motivation
- [[Meaningful Human Control|Artistic control over generative models]]

## Tasks
- [[Description to Sequence]]: generate a sequence (of symbolic music) from #per-bar token sequences (descriptions). (here #unsupervised)

## Ideas
### Descriptions
* Two kinds of low dimensional bar-wise automatically generated codes (“descriptions“) for a sequence are generated and fed together into a [[Autoregressive]] #sequence-to-sequence [[Transformer]] with the objective to reconstruct the original sequence from this description.
	- *Expert description*: Engineered and easy to understand rough features extracted with different heuristic methods (see Appendix B).
	- *Learned description*: The latent code of a [[VQ-VAE]]. After separate fully unsupervised training, it is frozen and its encoder part is used in the same manner as the engineered features to yield an input to the description-to-sequence transformer.
	The human understandable part of the description can 
### REMI+ Input Representation 
- extends [[REMI]] from [[Pop Music Transformer]] to be more robust and include more information (like varying time signatures and multiple instruments)

## Inductive Biases 
- Simple concepts derived from age-old (western) #music-theory define the *expert description*. They are herewith *empirically proven* to be somewhat meaningful. Though no comparison is given with other frameworks. 
- Relations of multiple bars are expressed through #attention, but the learned description of the [[VQ-VAE]] is learned only #per-bar, without musical context!

## [[Evaluation]] 
#wip

## Other Noteworthy Points
- A fully automated training pipeline by combining multiple previous methods for feature extraction.
- Has an #ethical-statement.

## Results
* Method to excert sequence-level (global *and* bar-wise) [[Meaningful Human Control]] over musical content. See also [[music impainting with stable diffusion]]
* State-of-the-art #symbolic #music #generation as of 22/03
* #ablation-study for expert description components: removing each part of the expert description significantly lowers the model’s performance, even regarding metrics that were assumed to be disentangled.  

## Future Work
* to Improve the expert description
	* since every existing part is shown to be highly valuable, distilling more advanced and detailed (music theoretical) insights into it could yield huge improvements, both to prediction quality *and* meaningful human control.


[^@rutteFIGAROGeneratingSymbolic2022]: Rutte, Dimitri von, L. Biggio, Yannic Kilcher, and Thomas Hofmann. 2022. “FIGARO: Generating Symbolic Music with Fine-Grained Artistic Control.” _ArXiv_, January. 

