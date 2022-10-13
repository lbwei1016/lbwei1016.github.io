---
layout: page
title: "Interlude: Magic & Math"
usemathjax: true
tag: Abstract Algebra, Group Theory, Magic
time: 2022/10/04
---

**Table of Content**
- [Gilbreath Permutation](#gilbreath-permutation)
  - [Description](#description)
  - [Definition (Gilbreath permutation)](#definition-gilbreath-permutation)
  - [Theorem (Ultimate Gilbreath principle)](#theorem-ultimate-gilbreath-principle)
  - [Proof](#proof)
- [Perfect Shuffle](#perfect-shuffle)
  - [Definition](#definition)
  - [Theorem](#theorem)
  - [Proof](#proof-1)
  - [Note](#note)
- [Reference](#reference)

---

## Gilbreath Permutation

### Description
這個特殊的 permutation 在數學魔術中經常出現，可以用來變如「洗牌後，抽出連續十對皆為一黑一紅」的魔術。

關鍵字：Riffle shuffle；鴿尾式洗牌。

### Definition (Gilbreath permutation)
> If a permutation $$\sigma$$ satisfies 
> 
> $$
>\begin{eqnarray}
>&\sigma(i) > \sigma(j),\ \forall 1\le i < j \le k, \tag{1} \\
>&\sigma(i) < \sigma(j),\ \forall k < i < j, \tag{2}
>\end{eqnarray}
>$$
>
> for a given $$k$$ such that $$1 \le k \le n$$. Then $$\sigma$$ is a **Gilbreath permutation**.


### Theorem (Ultimate Gilbreath principle)
> Given a permutation $$\sigma$$ of $$\{1,2,\cdots,n\}$$, the following four properties are equivalent:
- $$\sigma$$ is a Gilbreath permutation
- For each $$j$$, the top $$j$$ cards $$\sigma(1),\cdots,\sigma(j)$$ are distinct modulo $$j$$.
- (...omitted...)


### Proof

以下證明第二個 property。

對於任一在給定 $$k，\ 1 \le k \le n$$ 時符合

$$
\begin{eqnarray}
&\sigma(i) > \sigma(j),\ \forall 1\le i < j \le k, \tag{1} \\
&\sigma(i) < \sigma(j),\ \forall k < i < j, \tag{2}
\end{eqnarray}
$$

的 order 為 $$n$$ 的排列 $$\sigma$$ ，我們首先將 $$\sigma$$ 分成兩堆，其一符合 $$(1)$$、另一堆符合 $$(2)$$，分別稱其為 $$A,B$$。假設每次自 $$\sigma$$ 前端取出 $$d$$ 個數。考慮將 $$A$$ 插入 $$B$$ 以獲得原排列。

假設有 $$m$$ 個來自 $$A$$ 的數：$$a_1,\cdots,a_m$$，分布在 $$\sigma$$ 的前 $$d$$ 個位置，於是我們取出的首 $$d$$ 個數字為

$$
\{a_1,\cdots,a_m,b_1,\cdots,b_{d-m}\}.
$$

再假設 $$a_1=p$$；由於 $$A,B$$ 各自的性質：$$a_i$$ 遞減而 $$b_j$$ 遞增，而且 $$\sigma$$ 是一排列，因此

$$
b_1 = p + 1, \\
\begin{align*}
\{a_1,\cdots,a_m,b_1,\cdots,b_{d-m}\} &= \{p,(p-1),\cdots,(p-m+1),(p+1),\cdots,(p+d-m)\} \\
&= \{(p-m+1),\cdots,(p-m+d)\}.
\end{align*}
$$

由於 $$\{a_1,\cdots,a_m,b_1,\cdots,b_{d-m}\}$$ 是連續的 $$d$$ 個正整數，在模 $$d$$ 之下必為 $$\{0,1,\cdots,(d-1)\}$$，符合我們所要證明的情形。

假設第二次取出，$$A$$ 的元素在目前 $$\sigma$$ 的前 $$d$$ 個數字中，佔 $$m'$$ 個位置，則取出的首 $$d$$ 個數字為

$$
\{(p-m),\cdots,(p-m-m'+1),\cdots,(p-m+d+1),\cdots,(p-m+d+d-m')\}. \\
$$

考慮模 $$d$$，則

$$
\begin{align*}
(p-m+d+1) &\equiv (p-m+1), \\
(p-m+d+2) &\equiv (p-m+2), \\
&\cdots \\
(p-m+2d-m') &\equiv (p-m-m'+d).
\end{align*}
$$

所以 $$\{a_1,\cdots,a_m,b_1,\cdots,b_{d-m}\}$$ 也是 $$d$$ 個連續的正整數，在模 $$d$$ 之下必為 $$\{0,1,\cdots,(d-1)\}$$。

以此類推，任一次取出 $$d$$ 個數，其在模 $$d$$ 之下必為 $$\{0,1,\cdots,(d-1)\}$$，得證。

---

## Perfect Shuffle

### Definition
> Let $$\sigma$$ be the **perfect shuffle**, which satisfies the following:
>
> $$\sigma(x) = \begin{cases}
> 2x-1,\ x \le n, \\
> 2(x-n),\ x > n,
> \end{cases}$$
> 
> when there are $$2n$$ cards. That is, we first equally divide the deck, then the **perfect shuffle** makes the cards of both sub-deck *perfectly* interlaced. (If the current card is from sub-deck $$A$$, then the neighboring ones are from sub-deck $$B$$, vice versa.)

### Theorem
> Let $$\sigma$$ be the **perfect shuffle** of $$2n$$ cards. Show that the order of $$\sigma$$ is equal to the order of $$2$$ in $$\mathbb{Z}^{\times}_{2n-1}.$$

### Proof

1. 將 $$\langle \bar 2 \rangle$$ 和以 $$2$$ 為開頭的 cycle $$C_2$$ 對應。
2. 將 $$C_2$$ 和其他 cycle 對應。（證明所有 cycle length 皆為 $$C_2$$ length 的因數）
3. 取 $$\text{lcm}$$。

> 多多利用二的次方操作；模 $$2n-1$$。

### Note
在 $$2n = 52$$ 時，$$\sigma$$ 的 order 是 $$8$$，也就是說，$$8$$ 次 **perfect shuffle** 相當於沒洗過！所以才會有[「洗七次」](https://math.hmc.edu/funfacts/seven-shuffles/)的說法。

---

## Reference
- [Wiki](https://en.wikipedia.org/wiki/Gilbreath_shuffle)
- [Su, Francis E., et al. “Seven Shuffles.” Math Fun Facts.](https://www.math.hmc.edu/funfacts)
  - [https://math.hmc.edu/funfacts/seven-shuffles/](https://math.hmc.edu/funfacts/seven-shuffles/)