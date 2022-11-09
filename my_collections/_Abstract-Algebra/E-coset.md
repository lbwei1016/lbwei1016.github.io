---
layout: page
title: Coset
usemathjax: true
tag: Abstract Algebra, Group Theory
time: 2022/10/13
---

**Table of Content**
- [Coset](#coset)
  - [Definition (coset)](#definition-coset)
  - [Theorem (left coset)](#theorem-left-coset)
  - [Example $$\rm I$$](#example-rm-i)
  - [Example $$\rm II$$](#example-rm-ii)

---

## Coset
### Definition (coset)
> Given a subgroup $$H$$ of a group $$G$$, for $$a \in G$$, the set 
>
> $$ aH = \{ah: h \in H\}$$
>
> is called the **left coset** of $$H$$ containing $$a$$, and $$Ha$$ is called the **right coset** of $$H$$ containing $$a$$. The set of left cosets of $$H$$ in $$G$$ is denoted by $$G/H$$, and the set of right cosets of $$H$$ in $$G$$ is denoted by $$H\backslash G$$.

Right coset 的 notation $$H\backslash G$$ 怎麼看？和「$$G$$ 除以 $$H$$（$$G/H$$ ）」的 quotient 想法相同（注意除號的方向），只是把 $$G$$ 擺在右邊而已！

### Theorem (left coset)

For two left cosets $$aH$$ and $$bH$$, the following hold:

1. $$\vert aH \vert = \vert bH \vert = \vert H \vert$$.
2. If $$aH \bigcap bH$$ is non-empty, then $$aH = bH$$.
3. $$aH = bH \iff a^{-1}b \in H$$.
4. $$G$$ can be written as a disjoint union of left cosets of $$H$$, i.e.
  
$$G = \bigsqcup_{gH \in G/H} gH.$$

由於 coset 的 disjoint 性質，coset 其實隱含了一 equivalence relation：

$$
g_1 \sim g_2, \text{ if } g_1 \text{ and } g_2 \text{ are in the same left coset.} 
$$

**Proof**

1 . By [Cayley's Theorem](../C-Cayley-thm) we konw $$\lambda_a$$ is a bijection. Since $$aH = \lambda_a(H)$$, 

2 . Suppose $$ah_1 = bh_2$$ for some $$h1,h_2 \in H$$. Since $$hH = H$$ for all $$h \in H$$, $$H$$ and $$aH$$ have the same cardinality.

$$aH = ah_1H = bh_2H = bH.$$

3 . Suppose $$aH = bH$$, we have $$ah=be=b$$ for some $$h \in H$$. ... Conversely, if $$a^{-1}b=h$$ for some $$h \in H$$. ...

4 . For all $$g \in G$$, we have $$g \in gH$$. Therefore, every element is contained in some left cosets. Together with (2), this can be proved. 

> (2) implies *disjoint*.

> right coset 的 properties 自行想像。

### Example $$\rm I$$

Let $$G=\mathbb{Z}_{12}$$ and $$H = \{\bar 0, \bar 3\}$$. We have

$$
\begin{align*}
G  &= \{\bar 0, \bar 3\} \sqcup \{\bar 1, \bar 4, \bar 7, \bar 10\} \sqcup \{\bar 2, \bar 5, \bar 8, \bar 11\} \\
&= H \sqcup (\bar 1 + H) \sqcup (\bar 2 + H).
\end{align*}
$$

> 因為 $$+$$ 可交換，所以 left coset 和 right coset 相同。

> 要找出所有 left coset，首先寫出 $$H$$，再找出一個 $$g$$ 使得 $$g\in G$$ 但 $$g \not \in H$$，然後乘上 $$H$$；重複直到全部找出來。

### Example $$\rm II$$

$$
\begin{align*}
\mathbb{Z}_n &= \mathbb{Z}/n\mathbb{Z}, \\
\mathbb{Z} &= n\mathbb{Z} \bigsqcup (1 + n\mathbb{Z})\bigsqcup  \cdots \bigsqcup((n-1)+ n\mathbb{Z}) \\
&= \bar 0 \bigsqcup \bar 1 \bigsqcup \cdots \bigsqcup \overline{n-1}.
\end{align*}
$$