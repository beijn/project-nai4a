## Faithfully fill-in missing parts of a sequence [^8]

![[The Piano Inpainting Application - Figure 1.png]]

- Given an incomplete sequence with wildly distributed blans, generate a complete sequence 
- adhering to a general distribution of the data
- while keeping *all constraints* given by the tokens in the incomplete conditioning sequence.

## Problem with previous [[Conditional Generation]]
- Generation from [[Autoregressive]] models doesn't easily enforce constraints 
- and [[Rejection Sampling]] becomes highly inefficient, given many constraints.

## Solution: [[Anticipation-RNN]]
see [^8]

## In [[The Piano Inpainting Application]]
- For each piece of information, breaking down to each note's attribute, a *fill-me-in* token has to be specified upfront. 


[^8]: G. Hadjeres and F. Nielsen. Anticipation-rnn: Enforcing unary constraints in sequence generation, with application to interactive music generation. Neural Computing and Applications, 32(4):995–1005, 2020.