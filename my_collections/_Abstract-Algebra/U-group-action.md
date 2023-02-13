---
layout: page
title: Group Action
usemathjax: true
tag: Abstract Algebra, Group
time: 2023/02/13
---

**Table of Content**
- [Definition (Group action)](#definition-group-action)
  - [Remark](#remark)
  - [Proposition (Group actions as permutations)](#proposition-group-actions-as-permutations)
    - [Remark](#remark-1)
  - [Examples](#examples)
- [Definition (orbit)](#definition-orbit)
- [Definition (faithful and transitive)](#definition-faithful-and-transitive)

---

## Definition (Group action)
> Let $$X$$ be a set and $$G$$ a group. An **action** of $$G$$ on $$X$$ is a map $$*: G\times X\to X$$ such that 
>
> 1. $$*(e, x) = x$$ for all $$x\in X$$, where $$e$$ is the identity element of $$G$$.
> 2. $$*(g_1, *(g_2, x)) = *(g_1g_2, x)$$ for all $$x\in X$$ and all $$g_1, g_2 \in G$$.
>
> We write $$*(g, x)$$ as **$$gx$$** for simplicity. Thus the above two conditions can be rephrased as:
> 1. $$ex = x$$ for all $$x\in X$$.
> 2. $$g_1(g_2x) = (g_1g_2)x$$ for all $$x\in X$$ and all $$g_1, g_2 \in G$$.

### Remark

- Here, $$X$$ is referred to as a **$$G$$-set**.
- We say *$$G$$ acts on $$X$$*.
- The second condition has **nothing** to do with *associativity*, since $$g_i$$ and $$x$$ belong to different sets.

### Proposition (Group actions as permutations)
> Suppose that a group $$G$$ acts on a set $$X$$. Then for a given $$g\in G$$, **the function $$X\to X$$ represented by $$g$$** is **one-to-one** and **onto**, that is:
> 
> 1. If $$gx_1 = gx_2$$, then $$x_1 = x_2$$.
> 2. For all $$y\in X$$, there exists $$x\in X$$ such that $$gx = y$$.

**Proof** (Ignored.)

#### Remark

[回想起來](../C-Cayley-thm)，permutation 是一 **one-to-one** 且 **onto** 的 mapping，與此處的 group action 不謀而和。也就是說，以上的定理可以如下表示：

Let $$S_X$$ be the set of permutations on $$X$$. A group action $$*$$ of $$G$$ on $$X$$ can be regarded as **a group homomorphism** $$\rho: G\to S_X$$ such that

$$
*(g, x) = gx = \rho(g)x,
$$

where $$\rho(g) \in S_X$$ and hence $$\rho(g): X\to X$$. 

於是

$$\text{An action of } G \text{ on } X \iff \text{a group homomorphism from } G \text{ to } S_X.$$

注意，我們討論的是 $$X$$ 的 permutation，是否存在 $$\rho(g_i) = \rho(g_j), i\not =j$$ 並不重要！

> 相當於問 $$g_ix$$ 是否等於 $$g_jx$$。

底下證明 $$\rho$$ 是 group homomorphism：

**Proof**

For all $$g_1, g_2\in G$$, 

$$
\begin{align*}
  *(g_1, *(g_2, x)) &= \rho(g_1)\big(\rho(g_2)x\big) \\
  &= \big(\rho(g_1)\rho(g_2)\big)x \\
  &= *(g_1g_2, x) = \rho(g_1g_2)x. \tag*{$\blacksquare$} \\
\end{align*}
$$

### Examples

Below $$G$$s act on $$X$$s, repsectively.

- Let $$G$$ be a group of symmetries of an object $$X$$.
- Let $$G=S_n$$, $$X=\{1, 2,\cdots, n\}$$.
  - $$S_n$$ acts on $$X$$ by $$\sigma x = \sigma(x)$$.
- Let $$G=\text{GL}(n, \Bbb{R}), X=\Bbb{R}^n$$.
  - $$\text{GL}(n, \Bbb{R})$$ acts on $$X$$ by $$(M, v) \mapsto Mv$$.
- Let $$X=G$$; $$(g, x)\mapsto gx$$. 
  - See [Cayley's theorem](../C-Cayley-thm).
- Let $$X=G/H$$; $$(g, aH) \mapsto (ga)H$$.
  - See [generalized Cayley's theorem](../I-more-on-normal-subgroups/#normal-subgroup-and-homomorphism).
- Let $$X$$ be a non-empty set and $$n$$ be a positive integer. Let $$G$$ be *any* subgroup of $$S_n$$.
  - $$S_n$$ acts on $$X^n$$ by $$(\sigma, (x_1, \cdots, x_n)) \mapsto (x_{\sigma(1)}, \cdots, x_{\sigma(n)})$$.
- The map $$*: G\times G\to G$$ given by $$*(g, x) = gxg^{-1}$$ is a group action, since $$\rho: G \to \text{Aut}(G)$$ is a group homomorphism.
  - See [remark](#remark-1) and [Normal Subgroup and Homomorphism](../I-more-on-normal-subgroups/#normal-subgroup-and-homomorphism).

---

## Definition (orbit)
> Let $$X$$ be a $$G$$-set. The $$G$$-orbit of $$x$$ is defined as 
>
> $$
> G(x) := \{gx\mid g\in G\}.
> $$

> See [Symmetry Groups on N-gons](../B-n-gons/#theorem-stabilizer--ordit). Note that $$G$$-orbit itself is a $$G$$-set.

---

## Definition (faithful and transitive)
> A group action $$*$$ by $$G$$ on $$X$$ is said to be **faithful** if $$e\in G$$ (identity) is the **only** element that leaves every element of $$X$$ unchanged. That is to say, **$$*$$ is faithful iff $$\text{ker}(\rho) = \{e\}$$**, where $$\rho: G\to S_X$$, by this [remark](#remark-1).
>
> Then, $$*$$ is called **transitive** if for all $$x_1,x_2\in X$$, there exists $$g\in G$$ such that $$gx_1 = x_2$$.