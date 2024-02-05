---
lang: en
title: Random
viewport: width=device-width, initial-scale=1.0
---
To generate keys, salts, and other cryptographic features we often need access
to randomness to be able to create them in a non-deterministic way. To do so,
we need cryptographically secure pseudo random number generators. 

```
                # pseudo random generator (not secure)
S = g(seed)     # get a seed
(U, S') = f(S)  # random number function generates num U and new seed state S'
S = S'          # seed is updated to new state
return U        # return random value
```

The problem with the above code is that the seeds will cycle. At some point
there is some \(S' == S_0 \), and then the sequence will cycle. Give the best
performane of the f function, you would see a cycle after \( 2^{seed bits}\).

To break this cycle we need to introduce a source of true randomness. Often
we may need to combine several sources to create a random pool that we can
draw from. We can gather them from some proprietary random-purpose hardware
device, from the mouse, the keyboard, or from disk i/o and trying to gather
noisy data from those sources. 

# Extra random numbers (hash chaining)
The pool of random numbers can be exhausted and one of the ways to extend it
is to hash previously produced values. Since the hash produces a fixed size
output we can feed it a smaller input to extend our random bits. 