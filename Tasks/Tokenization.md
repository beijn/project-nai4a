A comprehensive and recent overview of tokenization strategies is given in [[MidiTok]][^@fradetMidiTokPythonPackage2021] ([see overview (and source)](https://github.com/Natooz/MidiTok)). 

The nested nature of [[MIDI]] note-on and -off events (see [[Structured MIDI Encoding]]) is difficult to grasp for current probabilistic sequence models, which cannot garanty the complex syntactical validity. Thus, most representations focus on 

## Difference to Text and problems with Transformers
The en vogue [[Transformer]] architecture has been developed for 1-D sequences of tokens from a large vacublary with no a-priori internal structure (text). 
- This is not an intuitive representation for music, as the concept was developed without respect to time and the overlay of multiple interacting voices. 
- Furthermore, (even disregarding timbre, expression and so on, as most symbolic music models do) musical notes, can be modeled relatively well (in some music styles) as low dimensional combinations of low ranged features like pitch and volume. 
- A single note has mutliple of those attributes. Thus, even simple and short musical phrases become quite long. 
- The quadratic time complexity of the dot-product based attention mechanism of vanilla [[Transformer]]s thus severly limits sequence length, thus #context and thus #long-term-coherence .  Long term coherence in particular is a very important feature of music. 
- To mitigate this one can use [[Linear Transformer]]s, as is done in [[Compound Word Transformer]], to process longer sequences more efficiently.
--- 
- 
- Or use more efficient embeddings / deal more effiently with the embeddings. 
	- [[CP]] from [[Compound Word Transformer]] aggregates mutliple tokens in groups tagged with "family" types (e.g. everything relating to one particular note), vertically aligns the tokens by their type (e.g. pitch vs duration) and transformers the resulting parallel sequences relatively independently in parallel. The aproach is very extensible and flexible with token types and families.
	- [[Structured MIDI Encoding]] from [[The Piano Inpainting Application]] proposes a similar approach but limiting and fixing token types, but increasing their interaction compared to [[Compound Word Transformer]].

- Various tokenization strategies (see [[MidiTok]][^@fradetMidiTokPythonPackage2021]) implement this separability of note features as chains of tokens of different types. Yet most NN applications to date don’t explicitly deal with the types, but treat all tokens in the same way as text tokens \[\[Compound Word Transformer]]. Instead of implementing an inductive bias of multiple of those tokens forming a discrete unit, this fact is implicitly to be learned by the attention mechanism. A very simple monophonous musical phrase thus already becomes a long sequence. Due to the quadratic time complexity of the (dot product) attention mechanism of transformers, this implies a heavy impediment on the length of processable sequences. Several strategies exist recently to address this inductive bias, detailed in the respective papers section . Also the sequence length becomes less impeding with the invention of linear time attention (see [[Linear Transformer]]).

((STRATEGIES FOR DEALING WITH THIS

*   Compound Word Transformer

))

nested processing? One system generates latent vectors for parts of a composition, so that they are linked, a subnet generates more low level latents from these and so on… Hirarchical Abstraction implemented as nested iterative latent expansion. Should also implement a mechanism for generated structures in lower levels to refer to similar substructures in sibling levels. In overall one wants a tree for hirarchical abstraction, but also interrelatedness for substructures depending on their latent relatedness atleast on the same level. And an iterative process of dialog between parts and levels until things agree / rough and random initial ideas have been polished.

2D transformer like ViT for music? pitch×time or per voice per time a pitch·velocity


## MidiTok 
### A python package for MIDI file tokenization [^@fradetMidiTokPythonPackage2021]
[source with great overview of all tokenization schemes](https://github.com/Natooz/MidiTok)

[TLDR] MidiTok is a Python package to encode MIDI files into sequences of tokens to be used with sequential Deep Learning models like Transformers or Recurrent Neural Networks to encode datasets with various strategies built around the idea that they share common parameters.

A Python library summarizing multiple methods to tokenize MIDI files for usage with sequential Deep Learning models like Transformers or Recurrent Neural Networks. Enables easy swapping between and fair comparison of tokenization methods.

[^@fradetMidiTokPythonPackage2021]: Nathan Fradet, Amal El Fallah Seghrouchni, Jean-Pierre Briot. 2021. “MidiTok: A Python Package for MIDI File Tokenization.” In _Extended Abstracts for the Late-Breaking Demo Session of the 22nd International Society for Music Information Retrieval Conference_.

