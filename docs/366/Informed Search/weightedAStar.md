---
lang: en
title: Weighted A*
viewport: width=device-width, initial-scale=1.0
---
In Weighted A\* we inflate the effect of the heuristic. Sometimes this algorithm
may expand less states than A\* or IDA*, and you can experiment to see if it
works well for your problem space. 

$$
\begin{aligned}
    & w > 1 \\
    & f(n) = g(n) + w \cdot h(n)
\end{aligned}
$$