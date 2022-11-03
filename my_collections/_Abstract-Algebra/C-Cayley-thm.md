---
layout: page
title: Cayley's Theorem
usemathjax: true
tag: Abstract Algebra, Group Theory
time: 2022/10/12
---

**Table of Content**
- [Theorem](#theorem)
  - [Example](#example)
  - [Proof](#proof)
- [Application](#application)

---


> $$S_G$$: $$G$$ 的 permutation group。
>
> We have $$S_G \cong S_{\vert G\vert }$$.

## Theorem

> 參考 [Generalized Cayley Theorem](../I-more-on-normal-subgroups/#normal-subgroup-and-homomorphism)。

Every group is isomorphic to a [group of permutation](../9-Groups-of-Permutation). More percisely, every group $$G$$ is isomorphic to **a subgroup of $$S_G$$** given by:
 
$$
\begin{align*}
\lambda_a &: G \to G, \text{ defined by } \lambda_a(g) = ag, \tag{1} \\
  \phi &: G \to S_G, \text{ defined by } \phi(g) =  \lambda_g, \tag{2}
\end{align*}
$$

for all $$a, g \in G$$. Since $$\phi$$ is **injective**, $$G$$ must be isomorphic to a subgroup of $$S_G$$.

**Remark**

$$\lambda_a$$ 在 $$(1)$$ 作為一個 mapping，其實也是一 permutation（底下會證明 $$\lambda_a$$ 是 permutation）。permutation 本來就是一 image 和 preimage 相同的 one-to-one、onto mapping！（想想 permutation 總是以 composition 進行運算。）

### Example

Let $$G=\mathbb{Z}^{\times}_8 = \{\bar 1, \bar 3, \bar 5, \bar 7 \}.$$ Then

$$
\lambda_{\bar 3} = \begin{pmatrix}
  \bar 1 & \bar 3 & \bar 5 & \bar 7 \\
  \bar 3 & \bar 1 & \bar 7 & \bar 5
\end{pmatrix}.
$$

> 全部元素乘上 $$\bar 3$$。 $$\lambda_{\bar 3}(\bar 5) = \bar 3\cdot\bar 5 = \bar 7$$。

Cayley's theorem states that $$G\cong \{\lambda_{\bar 1},\lambda_{\bar 3},\lambda_{\bar 5},\lambda_{\bar 7}\} \le S_G$$.

### Proof

To prove this theorem, we first claim that 

- $$\lambda_a$$ is a permutation of $$G$$,
- $$\lambda_a \circ \lambda_b = \lambda_{ab}$$.

Suppose the above are true. Let $$\hat G = \{\lambda_a:a\in G \}$$. We then claim that

- $$\hat G$$ is a subgroup of $$S_G$$.
- $$\phi: G \to \hat G$$ defined by $$\phi(a)=\lambda_a$$ is an isomorphism.

**Proof of claim 1.**

We need to show that for each $$a \in G$$, $$\lambda_a$$ is one-to-one and onto.

- one-to-one

For all $$g,h \in G$$, if $$\lambda_a(g) = \lambda_a(h)$$, then $$ag = ah$$. By the cancellation law, we have $$g = h$$.

- onto

For all $$h \in G$$, let $$g=a^{-1}h$$. Then $$\lambda_a(g) = a(a^{-1}h) = h$$.

**Proof of claim 2.**

$$\lambda_a \circ \lambda_b(g) = \lambda_a(\lambda_b(g)) = \lambda_a(bg) = a(bg)$$. By associativity, this is equal to $$(ab)g = \lambda_{ab}(g)$$.

> 代 $$g$$ 進來才好證。

**Proof of claim 3.**

To prove this, the following three conditions must be satisfied.

- closedness

Since for all $$a, b\in G$$, we have $$ab \in G$$; this is proved by **claim 2.**

- identity

Since $$\lambda_e(g) = g$$ for all $$g \in G$$, $$\lambda_e$$ is the identity of $$S_G$$, which is contained in $$\hat G$$.

- inverse

By **claim 2,** we have $$\lambda_{g^{-1}} \circ \lambda_g = \lambda_{g^{-1}g} = \lambda_e$$ and likewise $$\lambda_{g} \circ \lambda_{g^{-1}} = \lambda_{gg^{-1}} = \lambda_e$$. Thus $$\lambda_{g^{-1}}$$ is the inverse of $$\lambda_g$$, which is contained in $$\hat G$$.

**Proof of claim 4.**

We need to verify that the function $$\phi:G \to \hat G$$ defined by $$\phi(a) = \lambda_a$$ satisfies three coonditions below:

- one-to-one

For all $$a,b\in G$$, if $$\phi(a)=\phi(b)$$, we have $$\lambda_a = \lambda_b$$. Then $$\lambda_a(g) = \lambda_b(g)$$ for all $$ g \in G$$; in particular, $$\lambda_a(e) = \lambda_b(e)$$. From this we can conclude that $$a=b$$.

- onto

For all $$\lambda_a \in \hat G$$, we have $$a \in G$$ such that $$\phi(a) = \lambda_a$$.

- homomorphism

We need to show that $$\phi(ab) = \phi(a) \circ \phi(b)$$, that is $$\lambda_{ab} = \lambda_a \circ \lambda_b$$, which is already proved in **claim 2**. ◼

---

## Application

若要研究 group $$G$$ such that

$$|G|=n,$$

我們可以只針對 $$S_n$$ 的 subgroups 來縮小研究範圍。又已知 [the order of an element of $$G$$ divides \|$$G$$\|](../5-More-on-Groups/#remark-order-divides-order)，於是我們可以從找出 order 為 $$d,\ d \vert n$$ 的 element 開始，進而找出所有 subgroups of order $$n$$。