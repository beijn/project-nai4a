## Human expert composed samples from rich metadata [^@hyunComMUDatasetCombinatorial2022]

| Figure 8                  | Figure 2                  |
| ------------------------- | ------------------------- | 
| ![[ComMU - Figure 8.png]] | ![[ComMU - Figure 2.png]] |  |

The (12) metadata is prefixed as a token sequence to the note token sequence. The note sequence representation is an adapted form of [[REMI]].
See also [[ComMU]] (paper).

- *Correlations in data*, [^@hyunComMUDatasetCombinatorial2022], Section 3.4, shows, distributions of notes and metadata are highly interdependent (a *riff* has mostly short and mid-high nots)
	- hints that meaningful translations can be learned easily 

## Generation from humans
- composers tasked with extracting composing guidlines for specific industrial genres that use [[Combinatorial Music Generation#Homophonic Composition]].
- Composers tasked with composing short MIDI sequences that match this guidlines.
- Composed MIDI sequence and guidline (metadata) converted to [[REMI]]-like tokens.

## Metadata
- precise tokens: *bpm, key, instrument, time signature, pitch range, number of measure, min/max velocity, and rhythm*
	- tempo constant accross sequence
- ambiguous tokens: *genre*, *track role* and *chord progression*.
Comparison to other datasets regarding metadata given below.

## On other Datsets
![[ComMU - Table 1.png]]
See Table 1 of [[ComMU]] for an overview and Section 2 for a discussion.
- "[[Lakh MIDI Dataset]] [10], [[MAESTRO]] [12], and [[ADL Piano MIDI]] [14] have various meta-information such as genre, instrument, key, and time signature, but there is *no chord information* for the harmony of track-level composition."
- "[[MSMD]] [13], [[ GiantMIDI-Piano]] [15], and [[EMOPIA]] [23] have chord information that can infuse harmony, but *lack metadata* such as genre, and rhythm that can reflect the intention of composition."
- separates instruments from track role, other than "[10,28,29]"
	- in [[Symbolic Music Loop Generation]] both are the same as well

 [^@hyunComMUDatasetCombinatorial2022]: Hyun, Lee, Taehyun Kim, Hyolim Kang, Minjoo Ki, Hyeonchan Hwang, Kwanho Park, Sharang Han, and Seon Joo Kim. 2022. “ComMU: Dataset for Combinatorial Music Generation.” arXiv. [https://doi.org/10.48550/arXiv.2211.09385](https://doi.org/10.48550/arXiv.2211.09385).