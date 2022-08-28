---
layout: page
title: Binomial Coefficient
usemathjax: true
tag: Concrete Mathematics, Binomial
time: 2022/08/26
---

**Table of Content**

---

## Definition
$$
{r\choose k} =
\begin{cases}
{r^{\underline{k}} / k!},\  k \in \mathbb{N} \\
0,\ k \in \mathbb{Z}^-
\end{cases}
$$
> $$k$$ 必為整數，$$r$$ 為任意實數

> 參考 [Finite Calculus](../Finite-Calculus)

## Identities

- Symmetry

$${n \choose k}= {n \choose n-k},\ n \in \mathbb{Z}^+$$ 

> $$n$$ 一定不能是負的！詳見 *Concrete Math p.156*

- Absorption

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

- Addition
  
$${r \choose k} = {r-1 \choose k} + {r-1 \choose k-1},\ k \in \mathbb{Z}$$

- 上下差 $$r$$

$$\sum_{k \leq n}{r+k \choose k} = {r+n+1 \choose n},\ n \in \mathbb{Z}$$

- 上 $$k$$

$$\sum_{0 \leq k \leq n}{k \choose m} = {n+1 \choose m+1},\ m, n \in \mathbb{N}$$

- Binomial Theorem

$$(x+y)^r = \sum_k{r \choose k}x^ry^{r-k},\ r \in \mathbb{N} \lor \bigl| x/y \bigr| < 1$$

> 如果 $$r$$ 是任意實數，就要符合第二個條件

可以推廣至複數（設 $$z = x/y$$）：

$$(1+z)^r = \sum_k{r \choose k}z^k,\ \left| z \right| < 1$$