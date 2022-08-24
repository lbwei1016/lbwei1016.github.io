---
layout: page
title: Finite Calculus
usemathjax: true
tag: Concrete Mathematics, Calculus
time: 2022/08/24
---

> 離散的微積分

**Table of Content**
- [Definitions](#definitions)
  - [Rising Factorial](#rising-factorial)
  - [Falling Factorial](#falling-factorial)
  - [Difference operator ($$\Delta$$)](#difference-operator-delta)
  - [Harmonic Number](#harmonic-number)
- [Operations](#operations)
  - [Law of Exponents (falling factorial)](#law-of-exponents-falling-factorial)
  - [Fundamental Theorem](#fundamental-theorem)
  - [Definite Sum](#definite-sum)
  - [Powers](#powers)
  - [Summation by parts](#summation-by-parts)

---

## Definitions
### Rising Factorial

$$\begin{eqnarray}
    x^{\bar n} &=& x(x+1)\cdots(x+n-1) \\
    &=& (x+n-1)^{\underline{n}}
\end{eqnarray}$$


### Falling Factorial

$$\begin{eqnarray}
    x^\underline{n} &=& x(x-1)\cdots(x-n+1) \\
    &=& (x-n+1)^{\bar n}
\end{eqnarray}$$


$$0^{\underline{n}} = 0 \iff n > 0$$

> 這比較常用

### Difference operator ($$\Delta$$)

$$\Delta f(x) \equiv f(x+1) - f(x)$$

> 類比於 $$Df(x) = lim_{h\to 0}{f(x+h) - f(x)\over h}$$

### Harmonic Number

$$H_n = 1 + {1\over 2} + \cdots + {1\over n}$$

> 類比 $$ln(x)$$

## Operations

### Law of Exponents (falling factorial)

$$x^{\underline{m+n}} = x^{\underline{m}}(x-m)^{\underline{n}} \tag{1}$$

$$x^{\underline{-n}} = {1\over (x+n)^{\underline{n}}}\tag{2}$$

$$\Delta(x^{\underline{m}}) = mx^{\underline{m-1}} \tag{3}$$

### Fundamental Theorem

$$g(x) = \Delta f(x) \iff \sum g(x)\delta x = f(x) + C$$

> $$C = p(x)$$ such that $$p(x+1) = p(x)$$; hence $$C$$ is canclled out after *difference*.

### Definite Sum

$$g(x) = \Delta f(x),$$

$$\begin{eqnarray}
\sum_{x=a}^{b}g(x)\delta x &=& f(x)\Big|_a^b \\
&=& f(b) - f(a) \\
&=& \sum_{k=a}^{b-1}g(k) \tag{4}
\end{eqnarray}$$

> 最後一個等式可由 induction 得到

> 可見少了 $$\delta x$$ **上界減 $$1$$**

$$\sum_a^b g(x)\delta x + \sum_b^c g(x)\delta x = \sum_a^c g(x)\delta x \tag{5}$$

$$\begin{eqnarray} 
\sum_{a\leq k < b}k^{\underline{m}} \\ &=&
\begin{cases}
{k^{\underline{m+1} }\over m+1} \Big |_a^b\ ,\ m \not = -1 \\
H_k \Big |_a^b , \ m = -1 \\
\end{cases} \tag{6}
\end{eqnarray}
$$

### Powers

$$\Delta(c^x) = c^{x+1} - c^x = (c-1)c^x \tag{7}$$

$$\sum_{a\leq k < b}c^k = \sum_a^b c^x\delta x = {c^x\over c-1}\Big |_a^b \tag{8}$$

> 當 $$c=2$$，$$\Delta(2^x) = 2^x$$；$$2^x$$ 類比 infinite calclus 的 $$e^x$$

### Summation by parts

$$\sum u\Delta v = uv - \sum Ev\Delta u \tag{9}$$

> $$E$$ 是 operator，$$E = \Delta + 1$$，也就是 $$Ef(x) = \Delta f(x) + f(x) = f(x+1)$$

**e.g.**

$$\sum_{k=0}^n k2^k = \sum_0^{n+1}x2^x\delta x = x2^x - 2^{x+1} \Big |_0^{n+1}$$

> *Note:* 和「微積分」相關的操作要用有 $$\delta x$$ 的 sum，否則上界會少一