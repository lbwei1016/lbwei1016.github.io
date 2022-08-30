---
layout: page
title: Binomial Coefficient I
usemathjax: true
tag: Concrete Mathematics, Binomial
time: 2022/08/26
---

**Table of Content**
- [Definition](#definition)
- [Basic Identities](#basic-identities)
  - [Symmetry](#symmetry)
  - [Absorption](#absorption)
  - [Addition](#addition)
  - [上下差 $$r$$](#上下差-r)
  - [上 $$k$$](#上-k)
  - [Binomial Theorem](#binomial-theorem)
  - [Negation](#negation)
  - [頂真](#頂真)
  - [Multinomial Coefficient](#multinomial-coefficient)
  - [Trinomial Theorem](#trinomial-theorem)
  - [Three Coefficients](#three-coefficients)
- [Vandermonde's Convolution](#vandermondes-convolution)
- [Some Tricks](#some-tricks)
  - [Going Halves](#going-halves)
  - [Difference](#difference)
  - [移動 k](#移動-k)
- [Newton Series](#newton-series)
- [Reference](#reference)

---

## Definition
$$
{r\choose k} =
\begin{cases}
{r^{\underline{k}} / k!},\  k \in \mathbb{N} \\
0,\ k \in \mathbb{Z}^-
\end{cases}
$$
> $$k$$ 必為整數，$$r$$ 為任意實數，甚至複數

> 參考 [Finite Calculus](../Finite-Calculus)

---

## Basic Identities

> 有些 Identity 可以用 *Induction* 證明

### Symmetry

$${n \choose k}= {n \choose n-k},\ n \in \mathbb{Z}^+$$ 

> $$n$$ 一定不能是負的！詳見 *CMath p.156*

### Absorption

$${r \choose k} = {r \over k}{r-1 \choose k-1},\ k \not = 0$$

利用 *Symmetry*，可以得到（保持 lower index 不變）

$$(r-k){r \choose k} = r{r-1 \choose k},\ k \in \mathbb{Z},\ r \in \mathbb{R}$$

等等，不是說 *Symmetry* 只能用在 upper index 為非負整數時嗎？但事實上這個 identity 適用於任意實數上標，因為以下闡述的 *polynomial argument*：

**Polynomial Argument**

> 設 $$f(x)$$ 和 $$g(x)$$ 皆為 $$d$$ 次多項式：若 $$f$$ 和 $$g$$ 在多於 $$d$$ 處皆相等，則 $$f = g$$。

**Proof**

設 $$f(\alpha_i) = g(\alpha_i) = \beta_i,\ i \in \{1, 2, \cdots, k\}$$，令 $$h(x) = f(x) - g(x)$$，則有 $$k$$ 個點使 $$h(x)$$ 為零。因為 $$h(x)$$ 至多為 $$d$$ 次多項式，根據代數基本定理，$$h(x) = 0$$ 至多有 $$d$$ 個解；如果 $$k > d$$ 代表 $$h(x) = 0$$ 恆成立，也就是 

$$f(x) = g(x) \tag*{$\blacksquare$}$$

套用到本性質：等號左右皆為 $$r$$ 的 $$k+1$$ 次多項式，而且對於所有 $$r \in \mathbb{Z}^+$$ 等號皆成立（也就是無限多個點上，兩多項式相等，符合 *polynomial argument*），因此多項式相等，$$r$$ 於是可推廣至實數。

### Addition
  
$${r \choose k} = {r-1 \choose k} + {r-1 \choose k-1},\ k \in \mathbb{Z}$$

### 上下差 $$r$$

$$\sum_{k \leq n}{r+k \choose k} = {r+n+1 \choose n},\ n \in \mathbb{Z}$$

### 上 $$k$$

$$\sum_{0 \leq k \leq n}{k \choose m} = {n+1 \choose m+1},\ m, n \in \mathbb{N}$$

### Binomial Theorem

$$(x+y)^r = \sum_k{r \choose k}x^ry^{r-k},\ r \in \mathbb{N} \lor \bigl| x/y \bigr| < 1$$

> 如果 $$r$$ 是任意實數，就要符合第二個條件

可以推廣至複數（設 $$z = x/y$$）：

$$(1+z)^r = \sum_k{r \choose k}z^k,\ \left| z \right| < 1$$

> $$z$$ 的限制是為了確保 *infinite sum* 收斂

### Negation

$${r \choose k} = (-1)^k{k-r-1 \choose k},\ k \in \mathbb{Z}$$

$$\sum_{k \leq m}{r \choose k}(-1)^k = (-1)^m{r-1 \choose m}$$ 

> 第二個公式可用 ***上下差 $$r$$*** 導出

### 頂真

$${r \choose m}{m \choose k} = {r \choose k}{r-k \choose m-k}$$

### Multinomial Coefficient

$${a_1 + a_2 + \cdots + a_m \choose a_1, a_2, \cdots, a_m} = {(a_1 + a_2 + \cdots + a_m)! \over a_1! a_2! \cdots a_m!}$$

### Trinomial Theorem

$$(x+y+z)^n = \sum_{0 \leq a,b,c \leq n \\ a+b+c=n} {a+b+c \choose a,b,c} x^ay^bz^c$$

### Three Coefficients

$$\sum_k {a+b \choose a+k}{b+c \choose b+k}{c+a \choose c+k}(-1)^k = {a+b+c \choose a,b,c}$$

---

## Vandermonde's Convolution

$$\sum_k {r \choose m+k}{s \choose n-k} = {r+s \choose m+n},\ m, n \in \mathbb{Z} \tag{1}$$

$$\sum_k{l \choose m+\boldsymbol{k}}{s \choose n+\boldsymbol{k}} = {l+s \choose l-m+n},\ l \in \mathbb{N}; m, n \in \mathbb{Z} \tag{2}$$

$$\sum_k{l \choose m+\boldsymbol{k}}{s+\boldsymbol{k} \choose n}(-1)^\boldsymbol{k} = (-1)^{l+m}{s-m \choose n-l},\ l \in \mathbb{N}; m, n \in \mathbb{Z} \tag{3}$$

$$\sum_{\boldsymbol{k \leq l}}{l-\boldsymbol{k} \choose m}{s \choose \boldsymbol{k}-n}(-1)^\boldsymbol{k} = (-1)^{l+m}{s-m-1 \choose l-m-n},\ l, m, n \in \mathbb{N} \tag{4} $$

$$\sum_{0 \leq k \leq l}{l-\boldsymbol{k} \choose m}{q+\boldsymbol{k} \choose n} = {l+q+1 \choose m+n+1},\ l, m, n, q \in \mathbb{N}; n \geq q \geq 0 \tag{5}$$

> 注意 sum 的下標和 $$k$$ 的位置 \\
> *CMath p.169*

---

## Some Tricks

### Going Halves

$$r^{\underline k}(r - {1 \over 2})^{\underline k} = (2r)^{\underline{2k}} / 2^{2k}$$

### Difference

$$\Delta^nf(x) = \sum_k{n \choose k}(-1)^{n-k}f(x+k),\ n \in \mathbb{N}$$

**Proof**

$$\Delta$$ 是 operator，$$\Delta = E - 1$$（見 [Finite Calculus](../Finite-Calculus/#summation-by-parts)）。利用 *binomal theorem*，

$$\Delta^n = (E-1)^n = \sum_k{n \choose k}E^k(-1)^{n-k}$$

又 $$E^kf(x) = f(x+k)$$，得證。

### 移動 k

用 [Symmetry](#symmetry) 和 [Negation](#negation)

> 把 $$k$$ 從下（上）標往上（下）移

---

## Newton Series

利用 [Stirling Numbers](../Stirling-numbers)，$$x^n$$ 可以用 *falling factorial* 表示，所以任意 polynomial 都可以用 *binomial coefficient* 表示（因為 $${x \choose k} = x^{\underline k}/k!$$）。*Newton Series* 就是

$$f(x) = c_d{x \choose d} + c_{d-1}{x \choose d-1} + \cdots + c_0{x \choose 0}$$

> $$f(x) = a_dx^d + \cdots + a_0 = b_dx^{\underline d} + \cdots + b_0,\ deg(f) = d$$

再根據這個小性質

$$\Delta\Big({x \choose k}\Big) = {x+1 \choose k} - {x \choose k} = {x \choose k-1}$$

可以得出 $$n$$-th difference（類比 $$n$$ 次微分）

$$\Delta^nf(x) = c_d{x \choose d-n} + c_{d-1}{x \choose d-1-n} + \cdots + c_0{x \choose -n}$$

而

$$\Delta^nf(0) = \begin{cases}
c_n,\ n \leq d; \\
0,\ n > d.
\end{cases}$$

所以 Newton Series 可以寫成

$$f(x) = \Delta^df(0){x \choose d} + \Delta^{d-1}f(0){x \choose d-1} + \cdots + f(0){x \choose 0}$$

再來看 [Difference](#difference)（$$n \leq d$$）

$$\begin{eqnarray}
\Delta^nf(0) &=& \sum_k{n \choose k}(-1)^{n-k}f(k) \\
&=& \sum_k{n \choose k}(-1)^{n-k}(c_0{k \choose 0} + c_{1}{k \choose 1} + \cdots + c_n{k \choose n}) \\
&=& c_n
\end{eqnarray}$$

又 Newton Series 和原 polynomial 的領導係數的關係是

$$c_n = n!a_n$$

於是可以得到

$$(-1)^nn!a_n = \sum_k{n \choose k}(-1)^{k}(a_0 + \cdots + a_nk^n)$$

> 這個 identity 的重點是 $$\sum{n \choose k}(-1)^k$$

將 Newton Series 推廣至 infinity，可以類比 *Taylor Series*

$$g(a+x) = \sum_n{\Delta^ng(a) \over n!}x^{\underline n}$$

## Reference
- Concrete Mathematics: A Foundation for Computer Science, by Ronald Graham, Donald Knuth, and Oren Patashni [CMath]

> note till p.203