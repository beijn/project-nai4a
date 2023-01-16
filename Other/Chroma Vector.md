## Pitch × time intensity
[^@fujishimaRealtimeChordRecognition1999]

A simple and efficiently computable reduction of music that captures information very closely related to #harmony and #chord s.

- The vanilla version is a vector that contains a 1 for every pitch class present at a respective timeslice, and a 0 else. 
- Pitch class is the pitch modulo the octave. Usage of it implies the inductive bias of octave-invariance: That all "C"s on a piano are the same. It is guided by western #music-theory, which models the fundamental concept of harmony mostly on it. Though, it is often an imperfect abstraction. And obviously regarding #melody this is counterproductive.

---
- Though it is apperently not used like this, continous values for each pitch class (paralleling loudness/intensity/velocity) could provide more guidance wether a moment in a highly polyphonic composition is in this or rather that harmony.

[^@fujishimaRealtimeChordRecognition1999]: Fujishima, Takuya. 1999. “Realtime Chord Recognition of Musical Sound: A System Using Common Lisp Music.” In.


