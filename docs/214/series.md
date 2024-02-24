---
lang: en
title: Series
viewport: width=device-width, initial-scale=1.0
---
## What they is...
The concept of a series is tightly coupled to sequences. They are simply the
summation of all of the terms of sequence.

$$
\begin{align*}
a_n = \{n\} && \text{a sequence} \\
\sum_{n=1}^\infty a_n && \text{a series}
\end{align*}
$$

## Properties
### Convergence
The idea of convergence foxr a series is different notion than convergence with
a sequence. The idea is best examined through the idea of partial sums. If
a series is the sum of all of the sequence terms, then a partial sum is the
sum of the first N terms $ S_N $. We can begin with the first partial sum, the
second partial sum, the third partial sum, and we can take that to the limit of
infinity. 



$$
\begin{align}
&S = \sum_{n=1}^\infty a_n && \\
&S_n = \sum_{n=1}^N a_n && \\
&\{ S_n \}^\infty_{N=1} && \\
&S = L = \lim_{n \to \infty} S_n
\end{align}
$$

!!! note ""

    1. a series
    2. a partial sum. The sum of the first N terms of $ \{ a_n \}$
    3. a sequence of partial sums where each $ S_n $ is the sum of the first 
    n terms of the original sequence $ \{ a_n \}$
    4. the sum is the limit from n to $ \infty $ of the sequence of partial 
    sums $ \{ S_n \} $. In #2,     $ S_n $ is a partial sum, but when written 
    here, we are referring to the previous sentences understanding. 
Imagine that we have pebbles and that we add them one by one to a scale and 
record the weight as we add each one (the $ S_N $ value). If as we record the 
weight it settles to a number, then we say that the series converges. 
(analogy idea from ChatGPT)

### Absolute Convergence

A series that is the sum of all of the **absolute** terms of its sequence 
( $ \sum | a_n | $ ), and is convergent, is so called **absolutely** 
convergent.

If a series is absolutely convergent, then it is also convergent. 

### Conditional Convergence
If the series is convergent, but the absolute series is not, then it is called 
**conditionally** convergent. 


## Tests
### Divergency Test
### Integral Test
### Comparison Test
### Limit Comparison Test
### Alternating Series Test
### Ratio Test

### Root Test

## General Test Strategy
### Check for divergence
### Check for type of series
#### Harmonic series
#### Hyperharmonic (p-series) 
#### Geometric series
#### Telescoping series
### Descending and positive
### Evaluate limit of ratio or root
### Rational function
### Alternating series
### Remember the comparison test