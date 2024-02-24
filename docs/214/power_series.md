---
lang: en
title: Power Series
viewport: width=device-width, initial-scale=1.0
---
## What they is...
The first thing that separates power series from what we have seen with 
sequences and series is the presence of a new variable $x$ (or something
like it). A power series has the general form of:

$$
\begin{align*}
\sum_{n=0}^\infty a_n (x-c)^n = a_1 + a_2 (x-c)^1 + a_2 (x-c)^2 + ... + a_n (x-c)^n + ...
\end{align*}
$$

We say that the above is a power series in $x$ centered at $c$. 

The presence of $x$ here is what makes a power series a function and you can
see that is has this sort of neverending polynomial format as $ n \to \infty $.

When we discuss convegence of power series we will find that the series may
only converge for certain values of x and for other values the series would
diverge. 

### Interval of Convergence
This defines the values of x for which the power series will converge. The 
bounds themselves need a convergence test to indicate if they will converge, 
but all points in between will converge for the given interval.

### Radius of Convergence
The radius defines the bound within which the power series will converge: 
$ | x-a | < R $