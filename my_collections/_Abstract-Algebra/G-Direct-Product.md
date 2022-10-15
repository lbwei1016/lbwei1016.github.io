---
layout: page
title: Direct Product
usemathjax: true
tag: Abstract Algebra, Group Theory
time: 2022/10/15
---

**Table of Content**

---

## Direct Product

Let $$G_1,\cdots,G_n$$ be groups. For $$(a_1,\cdots,a_n)$$ and $$(b_1,\cdots,b_n)$$ in $$\prod_{i=1}^nG_i$$, define $$(a_1,\cdots,a_n)(b_1,\cdots,b_n) = (a_1b_1,\cdots,a_nb_n)$$.

> 定義 element-wise operation。

> The group $$\prod_{i=1}^nG_i = G_1 \times \cdots \times G_n$$ is called the **direct product** of the groups $$G_i$$.

### Theorem (cyclic abelian groups)
> The group $$\mathbb{Z}_m \times \mathbb{Z}_n$$ is **cyclic and isomorphic** to $$\mathbb{Z}_{mn}$$ *if and only if* $$m$$ and $$n$$ are **relatively prime**.

**Proof**

($$\Rightarrow$$)

Suppose $$\mathbb{Z}_m \times \mathbb{Z}_n$$ is cyclic and has a generator $$(\bar a, \bar b)$$, which is of order $$mn$$. Let $$k = \text{lcm}(m,n)$$. Then

$$
k(\bar a, \bar b) = (\overline{ka}, \overline{kb}) = (\bar 0, \bar 0).
$$

> $$Z_m$$ 的 generator is of order $$m$$。

Therefore $$mn \le k = \text{lcm}(m,n)$$, which means that $$m$$ and $$n$$ are relatively prime.

($$\Leftarrow$$)

Conversly, assume that $$m$$ and $$n$$ are relatively prime, which means $$\text{lcm}(m,n)=mn$$. Let the order of the element $$(\bar 1, \bar 1)$$ to be $$k$$. Then $$k \le mn$$ and

$$
(\bar 0,\bar 0) = k(\bar 1, \bar 1) = (\bar k, \bar k).
$$

Therefore, $$m \vert k$$ and $$n \vert k$$, which means $$\text{lcm}(m,n) \vert k$$. In particular, we have

$$
mn = \text{lcm}(m,n) \le k \le mn.
$$

We conclude that $$k = mn$$, $$(\bar 1, \bar 1)$$ is a generator, and $$\mathbb{Z}_m \times \mathbb{Z}_n$$ is cyclic. ◼

### Theorem (order of an element)
> Let $$(a_1,\cdots,a_n) \in \prod^n_{i=1}G_i$$. If $$a_i$$ is of finite order $$r_i$$ in $$G_i$$, then the order of $$(a_1,\cdots,a_n)$$ is equal to $$\text{lcm}(r_1,\cdots,r_n)$$.

### Note

用特定 element(s) 的 **order** 或 group 是否 **cyclic** 來判斷兩 groups 是否 **isomorphic**！

**e.g.**

max element order:

$$
\begin{align*}
\mathbb{Z}_8 &: 8 \\
\mathbb{Z}_{4}\times\mathbb{Z}_2 &: 4 \\
\mathbb{Z}_2\times\mathbb{Z}_2\times\mathbb{Z}_2 &: 2
\end{align*}
$$

所以以上三 groups 兩兩不 isomorphic。 
