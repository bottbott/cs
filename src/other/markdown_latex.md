---
author: Ashkan Mirzaee
description: An introduction for using Markdown and LaTeX
generator: pandoc
title: Markdown and LaTeX introduction
---

# Markdown

This resource is from [https://ashki23.github.io/markdown-latex.html]

The following provides a quick reference to the most commonly used
Markdown syntax.    

## Headers

### H3

#### H4

##### H5

###### H6

::: {#cb1 .sourceCode}
``` {.sourceCode .markdown}
# Markdown
The following provides a quick reference to the most commonly used Markdown syntax.

## Headers
### H3
#### H4
##### H5
###### H6
```
:::

## Emphasis

*Italic* and **Bold**

::: {#cb2 .sourceCode}
``` {.sourceCode .markdown}
*Italic* and **Bold**
```
:::

~~Scratched Text~~

::: {#cb3 .sourceCode}
``` {.sourceCode .markdown}
~~Scratched Text~~
```
:::

superscript^2^

::: {#cb4 .sourceCode}
``` {.sourceCode .markdown}
superscript^2^
```
:::

Markdown doesn't support underline, but we can use [HTML
Text]{.underline} instead. Also, **we** can *render* almost any
[HTML]{style="color:red;"} code that we [like]{.kbd} such as
superscript^2^.

::: {#cb5 .sourceCode}
``` {.sourceCode .html}
Markdown doesn't support underline, but we can use <u>HTML Text</u> instead. Also, <b>we</b> can <i>render</i> almost any <span style="color:red;">HTML</span> code that we &nbsp; <kbd>like</kbd> &nbsp; such as superscript<sup>2</sup>.
```
:::

For manual line or page breaks, we can use following HTML and CSS codes:

-   Line breaks:

::: {#cb6 .sourceCode}
``` {.sourceCode .html}
<br />
```
:::

-   Print breaks:

::: {#cb7 .sourceCode}
``` {.sourceCode .css}
<p style="page-break-after:always;"></p>
```
:::

## Lists

-   Item 1
-   Item 2
    -   Item 2a
    -   Item 2b
        -   Item 2b-1
        -   Item 2b-2

::: {#cb8 .sourceCode}
``` {.sourceCode .markdown}
- Item 1
- Item 2
    - Item 2a (2 tabs)
    - Item 2b
        - Item 2b-1 (4 tabs)
        - Item 2b-2
```
:::

1.  Item 1
2.  Item 2
3.  Item 3
    -   Item 3a
    -   Item 3b

::: {#cb9 .sourceCode}
``` {.sourceCode .markdown}
1. Item 1
2. Item 2
3. Item 3
    - Item 3a
    - Item 3b
```
:::

## Links

[Github](http://www.github.com/)

::: {#cb10 .sourceCode}
``` {.sourceCode .markdown}
[Github](http://www.github.com/)
```
:::

## Images

![logo](https://www.raspberrypi.org/app/uploads/2018/03/RPi-Logo-Reg-SCREEN-199x250.png "fig:Raspberry pi")

::: {#cb11 .sourceCode}
``` {.sourceCode .markdown}
<p align="center">
![logo](https://www.raspberrypi.org/app/uploads/2018/03/RPi-Logo-Reg-SCREEN-199x250.png "Raspberry pi")
</p>
```
:::

Note that here we used an HTML code to align center the image. Also, we
can use HTML to add more styles, for example:

::: {#cb12 .sourceCode}
``` {.sourceCode .html}
<p align="center">
<img src="https://www.raspberrypi.org/app/uploads/2018/03/RPi-Logo-Reg-SCREEN-199x250.png" alt="Raspberry pi" style="width:20%; border:0;">
</p>
```
:::

## Quotes

> Imagination is more important than knowledge.
>
> Albert Einstein

::: {#cb13 .sourceCode}
``` {.sourceCode .markdown}
> Imagination is more important than knowledge.
>
> Albert Einstein
```
:::

## Hlines

Use three dashes `---` to draw an horizontal line like:

------------------------------------------------------------------------

::: {#cb14 .sourceCode}
``` {.sourceCode .markdown}
---
```
:::

## Tables

::: {style="margin-bottom: 1rem; overflow-x: auto;"}
  1st Header      2nd Header      3rd Header
  ------------ ---------------- ------------
  col 1 is       left-aligned              1
  col 2 is      center-aligned             2
  col 3 is      right-aligned              3
:::

::: {#cb15 .sourceCode}
``` {.sourceCode .markdown}
1st Header|2nd Header|3rd Header
---|:---:|---: 
col 1 is|left-aligned|1
col 2 is|center-aligned|2
col 3 is|right-aligned|3
```
:::

Note that we can use HTML styles to hide tables' overflow by putting
them in a division like:

::: {#cb16 .sourceCode}
``` {.sourceCode .html}
<div "margin-bottom: 1rem; overflow-x: auto;">
...
</div>
```
:::

Also, we can use `overflow-x: scroll` to always scroll or
`overflow-x: hidden` to hide them compeletely.

## Code blocks

In Markdown, we can simply add plain code blocks to display (not
evaluating) by inserting triple back quote i.e. ```` ``` ````. For
example:

::: {#cb17 .sourceCode}
``` {.sourceCode .r}
norm = function(x) {
  sqrt(x%*%x)
}
norm(1:4)
```
:::

::: {#cb18 .sourceCode}
``` {.sourceCode .markdown}
` ``r
norm <- function(x) {
  sqrt(x%*%x)
}
norm(1:4)
` ``
```
:::

For inline plain codes use single back quote before and after the code,
for example we defined `this codes here` in this way.

## YAML header

At the top of a Markdown document, we can insert the following meta data
such that:

::: {#cb19 .sourceCode}
``` {.sourceCode .markdown}
---
title: "Page Title"
subtitle: "Page sub-title"
author: "Author name"
description: "This is a test"
institute: "MU"
date: "20/02/2020"
abstract: "YAML"
keywords: 
  - key1
  - key2
tags:
  - tag1
  - tag2
---
```
:::

## Mathematical formula

We can use LaTeX to write mathematical equations in Markdown. To write
inline LaTeX formula use a single `$` before and after the equation and
use a double `$` to display equations.

------------------------------------------------------------------------

# LaTeX

The following provides a quick reference of the most commonly used LaTeX
syntax. You may find a more extensive references about mathematical
formulas at [LaTeX
Wikibooks](https://en.wikibooks.org/wiki/LaTeX/Mathematics).

## LaTeX equations

Inline equation: [\\(equation\\)]{.math .inline}

::: {#cb20 .sourceCode}
``` {.sourceCode .markdown}
Inline equation: $equation$
```
:::

Display equation: [\\\[equation\\\]]{.math .display}

::: {#cb21 .sourceCode}
``` {.sourceCode .markdown}
Display equation: $$equation$$
```
:::

## Operators

-   [\\(x + y\\)]{.math .inline}
-   [\\(x - y\\)]{.math .inline}
-   [\\(x \\times y\\)]{.math .inline}
-   [\\(x \\div y\\)]{.math .inline}
-   [\\(\\dfrac{x}{y}\\)]{.math .inline}
-   [\\(\\sqrt{x}\\)]{.math .inline}

::: {#cb22 .sourceCode}
``` {.sourceCode .markdown}
- $x + y$
- $x - y$
- $x \times y$ 
- $x \div y$
- $\dfrac{x}{y}$
- $\sqrt{x}$
```
:::

## Symbols

-   [\\(\\pi \\approx 3.14159\\)]{.math .inline}
-   [\\(\\pm \\, 0.2\\)]{.math .inline}
-   [\\(\\dfrac{0}{1} \\neq \\infty\\)]{.math .inline}
-   [\\(0 \< x \< 1\\)]{.math .inline}
-   [\\(0 \\leq x \\leq 1\\)]{.math .inline}
-   [\\(x \\geq 10\\)]{.math .inline}
-   [\\(\\forall \\, x \\in (1,2)\\)]{.math .inline}
-   [\\(\\exists \\, x \\notin \[0,1\]\\)]{.math .inline}
-   [\\(A \\subset B\\)]{.math .inline}
-   [\\(A \\subseteq B\\)]{.math .inline}
-   [\\(A \\cup B\\)]{.math .inline}
-   [\\(A \\cap B\\)]{.math .inline}
-   [\\(X \\implies Y\\)]{.math .inline}
-   [\\(X \\impliedby Y\\)]{.math .inline}
-   [\\(a \\to b\\)]{.math .inline}
-   [\\(a \\longrightarrow b\\)]{.math .inline}
-   [\\(a \\Rightarrow b\\)]{.math .inline}
-   [\\(a \\Longrightarrow b\\)]{.math .inline}
-   [\\(a \\propto b\\)]{.math .inline}

::: {#cb23 .sourceCode}
``` {.sourceCode .markdown}
- $\pi \approx 3.14159$
- $\pm \, 0.2$
- $\dfrac{0}{1} \neq \infty$
- $0 < x < 1$
- $0 \leq x \leq 1$
- $x \geq 10$
- $\forall \, x \in (1,2)$
- $\exists \, x \notin [0,1]$
- $A \subset B$
- $A \subseteq B$
- $A \cup B$
- $A \cap B$
- $X \implies Y$
- $X \impliedby Y$
- $a \to b$
- $a \longrightarrow b$
- $a \Rightarrow b$
- $a \Longrightarrow b$
- $a \propto b$
```
:::

-   [\\(\\bar a\\)]{.math .inline}
-   [\\(\\tilde a\\)]{.math .inline}
-   [\\(\\breve a\\)]{.math .inline}
-   [\\(\\hat a\\)]{.math .inline}
-   [\\(a\^ \\prime\\)]{.math .inline}
-   [\\(a\^ \\dagger\\)]{.math .inline}
-   [\\(a\^ \\ast\\)]{.math .inline}
-   [\\(a\^ \\star\\)]{.math .inline}
-   [\\(\\mathcal A\\)]{.math .inline}
-   [\\(\\mathrm a\\)]{.math .inline}
-   [\\(\\cdots\\)]{.math .inline}
-   [\\(\\vdots\\)]{.math .inline}
-   [\\(\\#\\)]{.math .inline}
-   [\\(\\\$\\)]{.math .inline}
-   [\\(\\%\\)]{.math .inline}
-   [\\(\\&\\)]{.math .inline}
-   [\\(\\{ \\}\\)]{.math .inline}
-   [\\(\\\_\\)]{.math .inline}

::: {#cb24 .sourceCode}
``` {.sourceCode .markdown}
- $\bar a$
- $\tilde a$
- $\breve a$
- $\hat a$
- $a^ \prime$
- $a^ \dagger$
- $a^ \ast$
- $a^ \star$
- $\mathcal A$
- $\mathrm a$
- $\cdots$
- $\vdots$
- $\#$
- $\$$
- $\%$
- $\&$
- $\{ \}$
- $\_$
```
:::

## Space

-   Horizontal space: `\quad`
-   Large horizontal space: `\qquad`
-   Small space: `\,`
-   Medium space: `\:`
-   Large space: `\;`
-   Negative space: `\!`

## Greek alphabets

::: {style="margin-bottom: 1rem; overflow-x: auto;"}
  Small Letter                                  Capital Letter                                Alternative
  --------------------------------------------- --------------------------------------------- ---------------------------------------------------
  [\\(\\alpha\\)]{.math .inline} `\alpha`       [\\(A\\)]{.math .inline} `A`                  
  [\\(\\beta\\)]{.math .inline} `\beta`         [\\(B\\)]{.math .inline} `B`                  
  [\\(\\gamma\\)]{.math .inline} `\gamma`       [\\(\\Gamma\\)]{.math .inline} `\Gamma`       
  [\\(\\delta\\)]{.math .inline} `\delta`       [\\(\\Delta\\)]{.math .inline} `\Delta`       
  [\\(\\epsilon\\)]{.math .inline} `\epsilon`   [\\(E\\)]{.math .inline} `E`                  [\\(\\varepsilon\\)]{.math .inline} `\varepsilon`
  [\\(\\zeta\\)]{.math .inline} `\zeta`         [\\(Z\\)]{.math .inline} `Z`                  
  [\\(\\eta\\)]{.math .inline} `\eta`           [\\(H\\)]{.math .inline} `H`                  
  [\\(\\theta\\)]{.math .inline} `\theta`       [\\(\\Theta\\)]{.math .inline} `\Theta`       [\\(\\vartheta\\)]{.math .inline} `\vartheta`
  [\\(\\iota\\)]{.math .inline} `\zeta`         [\\(I\\)]{.math .inline} `I`                  
  [\\(\\kappa\\)]{.math .inline} `\kappa`       [\\(K\\)]{.math .inline} `K`                  [\\(\\varkappa\\)]{.math .inline} `\varkappa`
  [\\(\\lambda\\)]{.math .inline} `\lambda`     [\\(\\Lambda\\)]{.math .inline} `\Lambda`     
  [\\(\\mu\\)]{.math .inline} `\mu`             [\\(M\\)]{.math .inline} `M`                  
  [\\(\\nu\\)]{.math .inline} `\nu`             [\\(N\\)]{.math .inline} `N`                  
  [\\(\\xi\\)]{.math .inline} `\xi`             [\\(\\Xi\\)]{.math .inline} `\Xi`             
  [\\(\\omicron\\)]{.math .inline} `\omicron`   [\\(O\\)]{.math .inline} `O`                  
  [\\(\\pi\\)]{.math .inline} `\pi`             [\\(\\Pi\\)]{.math .inline} `\Pi`             [\\(\\varpi\\)]{.math .inline} `\varpi`
  [\\(\\rho\\)]{.math .inline} `\rho`           [\\(P\\)]{.math .inline} `P`                  [\\(\\varrho\\)]{.math .inline} `\varrho`
  [\\(\\sigma\\)]{.math .inline} `\sigma`       [\\(\\Sigma\\)]{.math .inline} `\Sigma`       [\\(\\varsigma\\)]{.math .inline} `\varsigma`
  [\\(\\tau\\)]{.math .inline} `\tau`           [\\(T\\)]{.math .inline} `T`                  
  [\\(\\upsilon\\)]{.math .inline} `\upsilon`   [\\(\\Upsilon\\)]{.math .inline} `\Upsilon`   
  [\\(\\phi\\)]{.math .inline} `\phi`           [\\(\\Phi\\)]{.math .inline} `\Phi`           [\\(\\varphi\\)]{.math .inline} `\varphi`
  [\\(\\chi\\)]{.math .inline} `\chi`           [\\(X\\)]{.math .inline} `X`                  
  [\\(\\psi\\)]{.math .inline} `\psi`           [\\(\\Psi\\)]{.math .inline} `\Psi`           
  [\\(\\omega\\)]{.math .inline} `\omega`       [\\(\\Omega\\)]{.math .inline} `\Omega`       
:::

## Equations

[\\\[\\mathbb{N} = \\{ a \\in \\mathbb{Z} : a \> 0 \\}\\\]]{.math
.display}

::: {#cb25 .sourceCode}
``` {.sourceCode .markdown}
$$\mathbb{N} = \{ a \in \mathbb{Z} : a > 0 \}$$
```
:::

[\\\[\\forall \\; x \\in X \\quad \\exists \\; y \\leq
\\epsilon\\\]]{.math .display}

::: {#cb26 .sourceCode}
``` {.sourceCode .markdown}
$$\forall \; x \in X \quad \exists \; y \leq \epsilon$$
```
:::

[\\\[\\color{blue}{X \\sim Normal \\; (\\mu,\\sigma\^2)}\\\]]{.math
.display}

::: {#cb27 .sourceCode}
``` {.sourceCode .markdown}
$$\color{blue}{X \sim Normal \; (\mu,\sigma^2)}$$
```
:::

[\\\[P \\left( A=2 \\, \\middle\| \\, \\dfrac{A\^2}{B}\>4
\\right)\\\]]{.math .display}

::: {#cb28 .sourceCode}
``` {.sourceCode .markdown}
$$P \left( A=2 \, \middle| \, \dfrac{A^2}{B}>4 \right)$$
```
:::

[\\\[f(x) = x\^2 - x\^\\frac{1}{\\pi}\\\]]{.math .display}

::: {#cb29 .sourceCode}
``` {.sourceCode .markdown}
$$f(x) = x^2 - x^\frac{1}{\pi}$$
```
:::

[\\\[f(X,n) = X_n + X\_{n-1}\\\]]{.math .display}

::: {#cb30 .sourceCode}
``` {.sourceCode .markdown}
$$f(X,n) = X_n + X_{n-1}$$
```
:::

[\\\[f(x) = \\sqrt\[3\]{2x} + \\sqrt{x-2}\\\]]{.math .display}

::: {#cb31 .sourceCode}
``` {.sourceCode .markdown}
$$f(x) = \sqrt[3]{2x} + \sqrt{x-2}$$
```
:::

[\\\[\\mathrm{e} = \\sum\_{n=0}\^{\\infty} \\dfrac{1}{n!}\\\]]{.math
.display}

::: {#cb32 .sourceCode}
``` {.sourceCode .markdown}
$$\mathrm{e} = \sum_{n=0}^{\infty} \dfrac{1}{n!}$$
```
:::

[\\\[\\prod\_{i=1}\^{n} x_i - 1\\\]]{.math .display}

::: {#cb33 .sourceCode}
``` {.sourceCode .markdown}
$$\prod_{i=1}^{n} x_i - 1$$
```
:::

[\\\[\\lim\_{x \\to 0\^+} \\dfrac{1}{x} = \\infty\\\]]{.math .display}

::: {#cb34 .sourceCode}
``` {.sourceCode .markdown}
$$\lim_{x \to 0^+} \dfrac{1}{x} = \infty$$
```
:::

[\\\[\\int_a\^b y \\: \\mathrm{d}x\\\]]{.math .display}

::: {#cb35 .sourceCode}
``` {.sourceCode .markdown}
$$\int_a^b y \: \mathrm{d}x$$
```
:::

[\\\[\\log_a b = 1\\\]]{.math .display}

::: {#cb36 .sourceCode}
``` {.sourceCode .markdown}
$$\log_a b = 1$$
```
:::

[\\\[\\min(P) = \\max\_{i:S_i \\in S} S_i\\\]]{.math .display}

::: {#cb37 .sourceCode}
``` {.sourceCode .markdown}
$$\max(S) = \max_{i:S_i \in S} S_i$$
```
:::

[\\\[\\dfrac{n!}{k!(n-k)!} = \\binom{n}{k}\\\]]{.math .display}

::: {#cb38 .sourceCode}
``` {.sourceCode .markdown}
$$\dfrac{n!}{k!(n-k)!} = \binom{n}{k}$$
```
:::

[\\\[\\small \\text{\$\\dfrac{b}{a+b}=3, \\:\$ therefore we can set
\$\\: a=6\$}\\\]]{.math .display}

::: {#cb39 .sourceCode}
``` {.sourceCode .markdown}
$$\text{$\dfrac{b}{a+b}=3, \:$ therefore we can set $\: a=6$}$$
```
:::

## Functions

[\\\[ f(x)= \\begin{cases} 1/d\_{ij} & \\quad \\text{when \$d\_{ij}
\\leq 160\$}\\\\ 0 & \\quad \\text{otherwise} \\end{cases} \\\]]{.math
.display}

::: {#cb40 .sourceCode}
``` {.sourceCode .markdown}
$$
f(x)=
\begin{cases}
1/d_{ij} & \quad \text{when $d_{ij} \leq 160$}\\ 
0 & \quad \text{otherwise}
\end{cases}
$$
```
:::

## Matrices

[\\\[ \\begin{matrix} 1 & 2 & 3 \\\\ 4 & 5 & 6 \\\\ 7 & 8 & 9
\\end{matrix} \\\]]{.math .display}

::: {#cb41 .sourceCode}
``` {.sourceCode .markdown}
$$
\begin{matrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{matrix}
$$
```
:::

[\\\[ M = \\begin{bmatrix} \\frac{5}{6} & \\frac{1}{6} & 0 \\\\\[0.3em\]
\\frac{5}{6} & 0 & \\frac{1}{6} \\\\\[0.3em\] 0 & \\frac{5}{6} &
\\frac{1}{6} \\end{bmatrix} \\\]]{.math .display}

::: {#cb42 .sourceCode}
``` {.sourceCode .markdown}
$$
M = 
\begin{bmatrix}
\frac{5}{6} & \frac{1}{6} & 0 \\[0.3em]
\frac{5}{6} & 0 & \frac{1}{6} \\[0.3em]
0 & \frac{5}{6} & \frac{1}{6}
\end{bmatrix}
$$
```
:::

[\\\[ M = \\begin{bmatrix} 1 & 0 \\\\ 0 & 1 \\end{bmatrix}
\\begin{bmatrix} 1 & 0 \\\\ 0 & 1 \\end{bmatrix} \\\]]{.math .display}

::: {#cb43 .sourceCode}
``` {.sourceCode .markdown}
$$ 
M =
\begin{bmatrix}
1 & 0 \\
0 & 1
\end{bmatrix}
\begin{bmatrix}
1 & 0 \\
0 & 1
\end{bmatrix}
$$
```
:::

[\\\[ M = \\begin{pmatrix} 1 & 0 \\\\ 0 & 1 \\end{pmatrix}
\\begin{pmatrix} 1 & 0 \\\\ 0 & 1 \\end{pmatrix} \\\]]{.math .display}

::: {#cb44 .sourceCode}
``` {.sourceCode .markdown}
$$ 
M =
\begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix}
\begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix}
$$
```
:::

[\\\[ A\_{m,n} = \\begin{pmatrix} a\_{1,1} & a\_{1,2} & \\cdots &
a\_{1,n} \\\\ a\_{2,1} & a\_{2,2} & \\cdots & a\_{2,n} \\\\ \\vdots &
\\vdots & \\ddots & \\vdots \\\\ a\_{m,1} & a\_{m,2} & \\cdots &
a\_{m,n} \\end{pmatrix} \\\]]{.math .display}

::: {#cb45 .sourceCode}
``` {.sourceCode .markdown}
$$
A_{m,n} = 
\begin{pmatrix}
a_{1,1} & a_{1,2} & \cdots & a_{1,n} \\
a_{2,1} & a_{2,2} & \cdots & a_{2,n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{m,1} & a_{m,2} & \cdots & a_{m,n} 
\end{pmatrix}
$$
```
:::

## Font sizes

[\\(\\Huge Hello!\\)]{.math .inline}\
[\\(\\huge Hello!\\)]{.math .inline}\
[\\(\\LARGE Hello!\\)]{.math .inline}\
[\\(\\Large Hello!\\)]{.math .inline}\
[\\(\\large Hello!\\)]{.math .inline}\
[\\(\\normalsize Hello!\\)]{.math .inline}\
[\\(\\small Hello!\\)]{.math .inline}\
[\\(\\scriptsize Hello!\\)]{.math .inline}\
[\\(\\tiny Hello!\\)]{.math .inline}\

::: {#cb46 .sourceCode}
``` {.sourceCode .markdown}
$\Huge Hello!$
$\huge Hello!$
$\LARGE Hello!$
$\Large Hello!$
$\large Hello!$
$\normalsize Hello!$
$\small Hello!$
$\scriptsize Hello!$
$\tiny Hello!$
```
:::

Example: [\\\[\\small \\text{Font size is small, eg. \$\\sum{x_i =
10}\$}\\\]]{.math .display}

::: {#cb47 .sourceCode}
``` {.sourceCode .markdown}
$$\small \text{Font size is small, eg. $\sum{x_i = 10}$}$$
```
:::
:::

::: {.d-none .d-xl-block .col-xl-2 .bd-toc}
-   -   [Markdown](#markdown)
        -   [Headers](#headers)
        -   [Emphasis](#emphasis)
        -   [Lists](#lists)
        -   [Links](#links)
        -   [Images](#images)
        -   [Quotes](#quotes)
        -   [Hlines](#hlines)
        -   [Tables](#tables)
        -   [Code blocks](#code-blocks)
        -   [YAML header](#yaml-header)
        -   [Mathematical formula](#mathematical-formula)
    -   [LaTeX](#latex)
        -   [LaTeX equations](#latex-equations)
        -   [Operators](#operators)
        -   [Symbols](#symbols)
        -   [Space](#space)
        -   [Greek alphabets](#greek-alphabets)
        -   [Equations](#equations)
        -   [Functions](#functions)
        -   [Matrices](#matrices)
        -   [Font sizes](#font-sizes)

:::
