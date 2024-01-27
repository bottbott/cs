---
lang: en
title: Sequences
viewport: width=device-width, initial-scale=1.0
---

# General

Sequences are ordered lists of numbers that may be finite or infinite.
When we study Series, they are the sums of the terms of the sequence.

A sequence may be described as a function that maps natural numbers to
the real number system.

$$
\begin{align*}
    f: \mathbb{N} \to \mathbb{R} \quad & \text{leads to} \\
    a_n = f(n)&
\end{align*}
$$

The sequence may start at any integer.

$$ 
\begin{align*}
    \{{2n}\}^\infty_{n=-3} = a_{-3},a_{-2}, ... = \\
    -6, -4, -2, ...
\end{align*}
$$

# Properties
## Increasing or Decreasing
Will a sequence continually rise in value as you go to the next term, or will it get lower? We can examine the relative adjacent terms to try to discover whether a sequence is "increasing" or "decreasing". We can also perform a first derivative test and and examine the values there to see if they are +'ve or -'ve. 

An increasing sequence should have terms such that:

$$a_n < a_{n+1} $$

A decreasing sequence should have terms such that:

$$a_n > a_{n+1} $$

### Strategies
Use the first derivative test to inspect where the function is decreasing/increasing.

Compare the nth term to the n+1th term. 

Compare the ratio of the n+1th term to the nth term which follows from. The setup below is for a decreasing examination.
$$
a_n \ge a_{n+1} \\
a_{n+1} \le a_n \\
\frac{a_{n+1}}{a_n} \ge 1
$$

## Monotonocity
A function will be monotonic if it has the property of entirely increasing or decreasing for all elements in the domain.

## Bounding
A sequence may never surpass a certain value, or it may never be lower than a certain value, or it may be contained between two numbers. If any of those are true, then the sequence may be "bounded above", "bounded below", "bounded between", or "not bounded". 

$$
\begin{align*}
    If a_n \leq M  \quad &\textbf{Bounded Above}. \\
    If a_n \geq m  \quad &\textbf{Bounded Below}. \\
    If m \leq a_n \leq M  \quad &\textbf{Bounded}. \\
\end{align*}
$$

## Limit

## Convergence