---
layout: page
title: Coset
usemathjax: true
tag: Abstract Algebra, Group Theory
time: 2022/10/13
---

**Table of Content**

---

## Coset
### Definition (coset)
> Given a subgroup $$H$$ of a group $$G$$, for $$a \in G$$, the set 
>
> $$ aH = \{ah: h \in H\}$$
>
> is called the **left coset** of $$H$$ containing $$a$$, and $$Ha$$ is called the **right coset** of $$H$$ containing $$a$$. The set of left cosets of $$H$$ in $$G$$ is denoted by $$G/H$$, and the set of right cosets of $$H$$ in $$G$$ is denoted by $$H\backslash G$$.

### Theorem

For two left cosets $$aH$$ and $$bH$$, the following hold:

1. $$\vert aH \vert = \vert bH \vert = \vert H \vert$$.
2. If $$aH \bigcap bH$$ is non-empty, then $$aH = bH$$.
3. $$aH = bH \iff a^{-1}b \in H$$.
4. $$G$$ can be written as a disjoint union of left cosets of $$H$$, i.e.
  
$$G = \bigsqcup_{gH \in G/H} gH.$$

**Proof**

1 . By [Cayley's Theorem](../C-Cayley-thm)

2 . Suppose $$ah_1 = bh_2$$ for some $$h1,h_2 \in H$$. Since $$hH = H$$ for all $$h \in H$$, we have

$$aH = ah_1H = bh_2H = bH.$$

3 . Suppose $$aH = bH$$, we have $$ah=be=b$$ for some $$h \in H$$. ... Conversely, if $$a^{-1}b=h$$ for some $$h \in H$$. ...

4 . For all $$g \in G$$, we have $$g \in gH$$. Therefore, every element is contained in some left cosets. Together with (2), this can be proved. 

> (2) implies *disjoint*.