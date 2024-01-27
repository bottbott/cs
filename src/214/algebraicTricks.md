---
lang: en
title: Algebraic Tricks
viewport: width=device-width, initial-scale=1.0
---

# Find limit of an equation without a denominator

Some of the equations that we need to find limits for can be difficult
to determine if there is no denominator since we can\'t easily apply
some of our existing tricks. We can use an equivalence to reinterpret
the equation so we can work with it.

$$
\begin{align*} 
    a - b = \frac{a^2-b^2}{a+b} && \text{the basic identity} \\
    \lim_{n \to \infty} \sqrt{n^2 + 5n} - \sqrt{n^2 -5n} \\ 
    a = \sqrt{n^2 + 5n} \\ 
    b = \sqrt{n^2 - 5n} \\ 
    \lim\_{n \to \infty} \frac{0}{\sqrt{n^2 + 5n} - \sqrt{n^2 - 5n}} && \text{after applying identity} 
\end{align*}
$$

# Factor out dominant terms
To find the limit of:
$$
\lim_{n \to \infty}\frac{\ln{2n}}{\ln{5n}}
$$

We can use rules about logarithms to rewrite it as a sum of the logs products.

$$
\frac{\ln{2} + ln{n}}{\ln{5} + \ln{n}}
$$

From there we can factor out the dominant term \(\ln{n} \)

$$
\frac{\ln{n}(\frac{\ln{2}}{\ln{n}} + 1)}{\ln{n}(\frac{\ln{5}}{\ln{n}} + 1)}
$$

Now it's easier to see what happens as n approaches infinity. 