---
layout: page
title: Three Isomorphism Theorems
usemathjax: true
tag: Abstract Algebra, Group
time: 2023/02/18
---

**Table of Content**
- [The First Isomorphism Theorem](#the-first-isomorphism-theorem)
  - [Theorem (the first isomorphiam theorem)](#theorem-the-first-isomorphiam-theorem)
- [The Second Isomorphism Theorem](#the-second-isomorphism-theorem)
  - [Definition (join of two subgroups)](#definition-join-of-two-subgroups)
    - [Theorem (if $$N$$ is normal)](#theorem-if-n-is-normal)
    - [Remark](#remark)
  - [Theorem (the second isomorphism theorem)](#theorem-the-second-isomorphism-theorem)
    - [Remark](#remark-1)
    - [Theorem (unique product)](#theorem-unique-product)
- [The Third Isomorphism Theorem](#the-third-isomorphism-theorem)
  - [Theorem (the third isomorphism theorem)](#theorem-the-third-isomorphism-theorem)
  - [Example](#example)

---

## The First Isomorphism Theorem
### Theorem (the first isomorphiam theorem)
> Let $$\psi: G\to G'$$ be a group homomorphism with kernel $$N$$. Then $$G/N$$ and $$\psi(G)$$ are isomorphic. The **canonical isomorphism** $$\mu: G/N \to \psi(G) $$ is given by $$\mu(gN) = \psi(g)$$.

> See [here](../H-homomorphism-and-normal-groups/#theorem-the-first-isomorphism-theorem).

---

## The Second Isomorphism Theorem
### Definition (join of two subgroups)
> Let $$H$$ and $$N$$ be two subgroups of a group $$G$$. The **join $$\langle H, N\rangle$$** of $$H$$ and $$N$$ is the **smallest subgroup** of $$G$$ that contains both $$H$$ and $$N$$.
>
> Equivalently, $$\langle H, N\rangle$$ is the intersection of **all** subgroups of $$G$$ containing $$H$$ and $$N$$.

#### Theorem (if $$N$$ is normal)
> Let $$H$$ and $$N$$ be two subgroups of a group $$G$$. **If $$N$$ is normal**, then **$$\langle H,N\rangle = HN = NH$$**. Especially, $$HN$$ is a subugroup of $$G$$.

**Proof**

1. Show that $$HN$$ is a subgroup of $$G$$. (by [this](../H-homomorphism-and-normal-groups/#theorem-equivalent-conditions))
2. Show that $$\langle H,N\rangle = HN$$.

$$HN$$ clearly contains both $$H$$ and $$N$$. Thus $$\langle H, N\rangle\subset HN $$.

Any subgroup containing both $$H$$ and $$N$$ must also contain all elements of the form $$hn, h\in H, n\in N$$. In particular, we have $$HN \subset \langle H, N\rangle$$. ◼

#### Remark

兩個 finite subgroup 的 join 可能 infinite！

因為 $$H\cup N$$ 不見得是 subgroup，所以定義 join（$$H\cap N$$ 是 subgroup）。

另外，join 也可以如下表示：

$$
\langle H,N\rangle = HN \cup HNHN \cup \cdots = \bigcup^{\infty}_{i=1}(HN)^i。
$$

### Theorem (the second isomorphism theorem)
> Let $$H$$ be a subgroup of $$G$$ and $$N$$ be a **normal** subgroup of $$G$$. Then $$(HN)/N \cong H/(H\cap N) $$.

**Proof**

> 這種有 coset 又有 isomorphism 的，通常利用 [the first isomorphism theorem](#the-first-isomorphism-theorem)。

Define a function $$\phi: H\to (HN)/N$$ by $$\phi(h)=hN$$. We claim that,

**$$\phi$$ is a homomorphism**: 
 
This is obvious since $$N$$ is normal.

**$$\text{ker}(\phi) = H\cap N$$**: 

If $$h\in \text{ker}(\phi)$$, then $$hN = N$$ and thus $$h\in N$$. Since $$h$$ is in $$H$$ by definition, we have $$h\in H\cap N$$. Conversely, every element in $$H\cap N$$ is also in $$\text{ker}(\phi)$$. Thus $$\text{ker}(\phi) = H\cap N$$.

**$$\phi$$ is onto**:

Given $$hnN\in HN/N$$ with $$h\in H$$ and $$n\in N$$. Then $$\phi(h) = hN = hnN$$. Thus $$\phi$$ is onto.

By the first isomorphism theorem, $$(HN)/N \cong H/(H\cap N) $$. ◼

#### Remark

我們也可以構造 $$\rho: HN\to H/(H\cap N)$$ 來證明，但上述的 $$\phi$$ 比較方便（因為 $$H$$ 比較小）。

另一重點是，我們不需檢查 $$\phi$$ 是否 well-defined，因為 $$\phi$$ 定義在 $$H$$ 上，而非 [quotient group](../H-homomorphism-and-normal-groups/#theorem-quotient-group) 上。

從上述定理，我們可以得知當 $$\vert G\vert < \infty$$，

$$
\vert HN\vert = {\vert N\vert \vert H\vert \over \vert H\cap N\vert}。
$$

若 $$\vert H\cap N\vert =1$$，則 $$\vert HN\vert =\vert N\vert \vert H\vert$$，亦即所有 $$HN$$ 內的元素可以唯一被 $$x\in H$$ 和 $$y\in N$$ 的乘積表示。定理如下：

#### Theorem (unique product)
> Let $$G$$ be a finite group with a subgroup $$H$$ and a normal subgroup $$N$$. If **$$\vert H\cap N\vert = 1$$ and $$\vert G\vert = \vert N\vert \vert H\vert $$**, then **every element** of $$G$$ can be written as $$xy$$ for some **unique** $$x\in H$$ and $$y\in N$$. That is, $$G=NH$$.

> If $$\gcd(\vert H\vert ,\vert N\vert )=1$$, then we always have $$\vert H\cap N\vert = 1$$.

**Example**

Let $$G$$ be a group of order $$2p$$ where $$p$$ is an odd prime. By [Cauchy's Theorem](../V-more-group-action/#theorem-cauchys-theorem), there exists an element $$a$$ of order $$2$$ and an element $$b$$ of order $$p$$. Since $$\langle b\rangle$$ is of index $$2$$, [it is a normal subgroup](../H-homomorphism-and-normal-groups/#proposition-index-two). In this case, we have

$$
\langle a,b\rangle = \langle a\rangle\langle b\rangle = G.
$$

In other words,

$$
G = \{e, b, b^2, \cdots, b^{p-1}, a, ab, ab^2, \cdots, ab^{p-1}\}.
$$

---

## The Third Isomorphism Theorem
### Theorem (the third isomorphism theorem)
> Let $$H$$ and $$K$$ be normal subgroups of $$G$$ with $$K\leq H$$. Then $$G/H \cong (G/K)/(H/K)$$.

**Proof**

Define $$\phi:G/K \to G/H$$ by $$\phi(gK) = gH$$. We claim that

1. $$\phi$$ is **well-defined**.
2. $$\phi$$ is a homomorphism.
3. $$\text{ker}(\phi) = H/K$$.
4. $$\phi$$ is onto.

Then by [the first isomorphism theorem](#the-first-isomorphism-theorem), we have proved this theorem. ◼

### Example

> **Q:** Let $$G = \Bbb Z^2$$ and $$H=\langle(1, 2), (2, 1)\rangle$$. Find the structure of $$G/H$$.

**Solution $$\rm I$$**

Let $$K=\langle(3, 0),(0, 3)\rangle$$, which is a subgroup of $$H$$. It is easy to see that $$G/K \cong \Bbb Z_3 \times \Bbb Z_3 = \{K, [(0,1)+K], [(0,2)+K],\cdots,[(2,2)+K]\}$$. Moreover, we can see that 

$$
H/K = \{K, [(1,2)+K],[(2,1)+K] \} \cong \Bbb Z_3.
$$

By the above theorem, $$\vert G/H\vert = {\vert G/K\vert\over\vert H/K\vert} = 3$$, which implies that $$G/H\cong \Bbb Z_3$$.

**Solution $$\rm II$$**

change of basis ?