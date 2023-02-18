---
layout: page
title: Burnside's Lemma
usemathjax: true
tag: Abstract Algebra, Group, Counting
time: 2023/02/18
---

**Table of Content**
- [Theorem (Burnside's Lemma)](#theorem-burnsides-lemma)
  - [Proof](#proof)
- [Painting Problem](#painting-problem)
  - [Example ($$k=6$$)](#example-k6)
  - [Remark](#remark)


---

Let $$G$$ be a finite group acting on a finite set $$X$$ and let $$X/G$$ denote the set of $$G$$-orbit in $$X$$.

## Theorem (Burnside's Lemma)
> $$
> \vert X/G\vert  = {1\over \vert G\vert }\sum_{g\in G}\vert X^g\vert .
> $$

### Proof

Consider the set $$S = \{(g, x)\mid g\in G, x\in X, gx = x \}$$. We will proceed with the double counting principle.

For each $$g\in G$$, there are $$\vert X^g\vert$$ elements in $$S$$ where $$g$$ is the first coordinate. Thus,

$$
\vert S\vert = \sum_{g\in G}\vert X^g\vert.
$$

On the other hand, for each $$x \in X$$, there are $$\vert\text{Stab}_G(x)\vert$$ elements in $$S$$ where $$x$$ is the second coordinate. Hence,

$$
\sum_{g\in G}\vert X^g\vert = \sum_{x\in X}\vert \text{Stab}_G(x)\vert = \vert G\vert \sum_{x\in X}{1\over \vert G_x\vert},
$$

where the last equality follows from [this theorem](../U-group-action/#theorem-the-orbit-stabilizer-theorem).

Let $$\mathcal{O}_1\cdots, \mathcal{O}_r$$ be the orbits, where $$r=\vert X/G\vert$$. We have

$$
\sum_{g\in G}\vert X^g\vert = \vert G\vert \sum_{x\in X}{1\over \vert G_x\vert} = \vert G\vert \sum_{i=1}^{r} \sum_{x\in \mathcal{O}_i} {1\over \vert G_x\vert},
$$

since [$$X$$ can be written as a disjoint union of $$G$$-orbits](../U-group-action/#corollary-disjoint-union-of-orbits).

When $$x\in \mathcal{O}_i$$, $$G_x = \mathcal{O}_i$$, and thus it follows that

$$
\sum_{g\in G}\vert X^g\vert = \vert G\vert \sum_{i=1}^{r} \sum_{x\in \mathcal{O}_i} {1\over \vert G_x\vert} = \vert G\vert\sum_{i=1}^r 1 = r\vert G\vert.
$$

Therefore,

$$
\vert X/G\vert = r = {1\over \vert G\vert }\sum_{g\in G}\vert X^g\vert. \tag*{$\blacksquare$}
$$

---

## Painting Problem

**Question**

Given a **regular $$k$$-gon and $$n$$ colors**, determine the number of ways to paint the frames, considering rotations and reflections as equivalent.

Let $$X$$ be the set of all possible ways to paint the frame, with $$\vert X\vert = n^k$$. Let $$G=D_k$$, the group of symmetries of the regular $$k$$-gon, consists of $$k$$ rotations and $$k$$ reflections. The group $$G$$ acts on $$X$$, and our task is to determine $$\vert X/G\vert$$.

> 為什麼是 $$\vert X/G\vert$$？因為[每個 orbit 都是一 cell](../U-group-action/#theorem-eq-relation)，而同一 orbit 中的兩種著色法可以經由旋轉或對稱而變成對方。

**Solution**

By [Burnside's lemma](#theorem-burnsides-lemma), 

$$
\vert X/G\vert  = {1\over \vert G\vert }\sum_{g\in G}\vert X^g\vert.
$$

We can **express $$G$$ as the group of permutations of $$k$$ edges**. If the cycle notation of $$g$$ consists of $$m_g$$ cycles, then

$$
\vert X^g\vert = n^{m_g} \text{, and} \\
\vert X/G\vert  = {1\over \vert G\vert }\sum_{g\in G}n^{m_g}.
$$

> 同一 cycle 中的邊得塗同一色。

### Example ($$k=6$$)

Below we discuss the elements in $$D_6$$.

| type                                  | ways to paint | count |
| ------------------------------------- | ------------- | ----- |
| identity                              | $$n^6$$       | $$1$$ |
| rotation of the form $$(123456)$$     | $$n$$         | $$2$$ |
| rotation of the form $$(135)(246)$$   | $$n^2$$       | $$2$$ |
| rotation of the form $$(14)(25)(36)$$ | $$n^3$$       | $$1$$ |
| reflection: fix two edges             | $$n^4$$       | $$3$$ |
| reflection: fix two vertices          | $$n^3$$       | $$3$$ |

Thus the number of possible colorings up to the action $$G$$ is:

$$
{1\over \vert D_6\vert}(n^6 + 3n^4 + (3+1)n^3 + 2n^2 + 2n) = {1\over 12}(n^6 + 3n^4 + 4n^3 + 2n^2 + 2n). \tag*{$\blacksquare$}
$$

### Remark

若 $$k = p$$ 是質數，則所有 rotation 必定是 order $$p$$；否則就存在 $$i\in \{1, \cdots,p\}$$、$$r\in \{1,\cdots,p-1\}$$ 使得

$$
i + jr = i \implies jr = 0, \ j < p.
$$

這相當於是說，除了單位元素之外，$$\Bbb Z_p$$ 中存在 order 不為 $$p$$ 的元素，顯然矛盾。

> 從 $$i$$ 出發，每條邊向前轉 $$r$$ 單位，共轉 $$j$$ 次。

鏡射軸也只能連一點一邊了，共 $$p$$ 種。於是可以推知，rotation 共 $$2p - p - 1 = p-1$$ 種！