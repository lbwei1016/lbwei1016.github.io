---
layout: page
title: Extended Euclidean Algorithm
usemathjax: true
tag: Number Theory, Group Theory
---

**Table of Contents**
- [Solution $$\rm I$$](#solution-rm-i)
- [Solution $$\rm II $$ (matrix)](#solution-rm-ii--matrix)

---

> Given $$ax+by=\gcd(a,b)$$, find a solution $$(x,y) = (x_0, y_0)$$.

## Solution $$\rm I$$
**Step $$\rm I$$**:

$$\begin{eqnarray}
    a &=& q_1\color{#5DADE2}{b} + \color{#E74C3C}{r_1} \\
    \color{#5DADE2}{b} &=& q_2\color{#E74C3C}{r_1} + \color{#A569BD}{r_2} \\
    \color{#E74C3C}{r_1} &=& q_3\color{#A569BD}{r_2} + \color{#17A589}{r_3} \\
    &\cdots& \\
    r_{m-3} &=& q_{m-1}r_{m-2} + r_{m-1} \\ 
    r_{m-2} &=& q_mr_{m-1} + 0 \\
\end{eqnarray}$$

$$\Rightarrow r_{m-1} = \gcd(a, b).$$

**Step $$\rm II$$**:

$$\begin{eqnarray} 
\gcd(a, b) &=& r_{m-3} - q_{m-1}\color{#A569BD}{r_{m-2}}      \\
&=& r_{m-3} - q_{m-1}\color{#A569BD}{(r_{m-4} - q_{m-2}r_{m-3})} 
\end{eqnarray}$$

(直到代換出 $$a, b$$)

$$\gcd(a,b) = ax_0+by_0 \tag*{$\blacksquare$}$$ 

**e.g.**
> Solve $$47x + 21y = \gcd(47,21) = 1$$.

**Step $$\rm I$$**:

$$\begin{eqnarray}
    47 &=& 2\times\color{#5DADE2}{21} + \color{#E74C3C}{5} \\ 
    \color{#5DADE2}{21} &=& 4\times\color{#E74C3C}{5} + \color{#A569BD}{1} \\ 
    \color{#E74C3C}{5} &=& 5\times \color{#A569BD}{1} + \color{#17A589}{0}
\end{eqnarray}$$

**Step $$\rm II$$**:

$$\begin{eqnarray}
    \boldsymbol{1} &=& 21 - 4\times\color{#A569BD}{5} \\
    \boldsymbol{1} &=& 21 - 4\times\color{#A569BD}{(47 - 2\times 21)} \\
    \boldsymbol{1} &=& 47\times (-4) + 21 \times 9
\end{eqnarray}$$

$$\Rightarrow (x,y) = (-4,9) \tag*{$\blacksquare$}$$

--- 

## Solution $$\rm II $$ (matrix)

We know that to find $$(x_0, y_0)$$, we have to solve recurrences in the form: 

$$r_{m-1} = r_mq_m + r_{m+1}.$$

Fortunately, one can express this by matrices:

$$\begin{eqnarray}
    \begin{pmatrix} r_{n-2} \\ r_{n-1} \end{pmatrix} &=& \begin{pmatrix} 0 & 1 \\ 1 & -q_{n-2} \end{pmatrix}\begin{pmatrix} r_{n-3} \\ r_{n-2} \end{pmatrix} \\
    &=& \begin{pmatrix} 0 & 1 \\ 1 & -q_{n-2} \end{pmatrix} \cdots \begin{pmatrix} 0 & 1 \\ 1 & -q_1 \end{pmatrix} \begin{pmatrix} r_0 \\ r_1 \end{pmatrix}.
\end{eqnarray}$$

Therefore, if we let

$$\begin{pmatrix} x & y \\ z & w \end{pmatrix}
= \begin{pmatrix} 0 & 1 \\ 1 & -q_{n-2} \end{pmatrix} \cdots \begin{pmatrix} 0 & 1 \\ 1 & -q_1 \end{pmatrix},$$

then the above equations show that 

$$\gcd(a, b) = r_{n-1} = az + bw. \tag*{$\blacksquare$}$$

> Let $$a = r_0, b = r_1.$$
 