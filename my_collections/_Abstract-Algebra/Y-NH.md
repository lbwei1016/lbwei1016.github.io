---
layout: page
title: Group Structure of NH
usemathjax: true
tag: Abstract Algebra, Group, direct product
time: 2023/02/24
---

**Table of Content**

---

## Group structure of $$NH$$

Can the structures of $$N$$ and $$H$$ be used to determine the structure of $$NH$$? First consider that **both subgroups are normal**.

### Theorem (two normal subgroups)
> Let $$N$$ and $$H$$ be two normal subgroups of $$G$$. Suppose $$N\cap H = \{e\}$$, then $$nh = hn$$ for all $$h\in H, n\in N$$ and $$NH \cong N \times H$$.

**Proof**

Since $$H$$ is normal, we have that for all $$n\in N$$, $$nhn^{-1} \in H$$. This also holds for $$N$$ and all $$h \in H$$. Then the element

$$
nhn^{-1}h^{-1} = (nhn^{-1})h^{-1} = n(hn^{-1}h^{-1})
$$

is contained in both $$N$$ and $$H$$. Therefore, $$nhn^{-1}h^{-1} = e$$, which implies $$nh = hn$$.

Now consider the map $$\rho:N\times H\to NH$$ given by $$\rho(n, h) = nh$$. We can prove that $$\rho$$ is an isomorphism. (Here we only show that $$\text{ker}(\rho) = \{(e, e) \}$$.)

Suppose $$(n,h)\in\text{ker}(\rho)$$, i.e., $$\rho(n, h) = nh = e$$. This implies that $$n = h^{-1} \in N\cap H$$. Therefore, $$n=h=e$$. ◼

### Semi-direct product

Now, suppose $$N$$ is normal and $$N\cap H = \{e\}$$. By [this theorem](#theorem-unique-product), the elements in $$NH$$ can be uniquely represented as $$nh$$ for some $$n\in N$$ and $$h\in H$$. Moreover. the product of two elements $$n_1h_1$$ and $$n_2h_2$$ can be written as

$$
n_1h_1n_2h_2 = n_1(h_1n_2h_1^{-1})h_1h_2 = n_1\rho_{h_1}(n_2)h_1h_2,
$$

where $$\rho_{h_1}(x) := h_1xh_1^{-1}$$ is an [inner automorphism](../I-more-on-normal-subgroups/#inner-automorphism) on $$N$$.

> $$\rho: H\to \text{Aut}(N)$$, given by $$h_1\mapsto \rho_{h_1}$$.

Then, consider the binary structure **$$N \rtimes_{\rho} H$$** defined on $$N\times H$$ given by

$$
(n_1, h_1)*(n_2, h_2) = (n_1, h_1)(n_2, h_2) := (n_1\rho_{h_1}(n_2), h_1h_2).
$$

> 這是定義在 $$N\rtimes_{\rho} H$$ 上的乘法，而 $$N\rtimes_{\rho} H$$ 的 elements 和 $$N\times H$$ 一模一樣！

Let's first prove that $$(N\rtimes_{\rho}H, *)$$ is a group:

<u>associativity</u>

Expand everything.

<u>idnetity</u>

<u>inverse</u>


Then prove that $$(N\rtimes_{\rho}H, *) \cong (NH, \cdot)$$. Define $$\phi: NH\to N\rtimes_{\rho}H$$ given by $$nh\mapsto (n, h)$$. Here we only show that $$\phi$$ is a homomorphism:

$$
\begin{align*}
\phi(n_1h_1n_2h_2) &= \phi(n_1\rho_{h_1}(n_2)h_1h_2) \\
&= (n_1\rho_{h_1}(n_2), h_1h_2) \\
&= \phi(n_1h_1)\phi(n_2h_2). \tag*{$\blacksquare$}
\end{align*}
$$


Especially, the group $$N\rtimes_{\rho}H$$ is called the **semi-direct product** of $$N$$ and $$H$$ with respect to $$\rho$$.

#### Theorem (semi-direct product)
> Let $$H$$ and $$N$$ be two subgroups of a finite group $$G$$. Suppose $$N$$ is normal and $$H\cap N = \{e\}$$. Then **there exists some group homomorphism $$\rho:H\to \text{Aut}(N)$$ such that $$NH \cong N\rtimes_{\rho}H$$**.

#### Remark

The binary structure $$(N\rtimes_{\rho}H, *)$$ **only** involves *the group operation of $$N$$, the group operation of $$H$$, and the group homomorphism $$\rho$$.*


---

## Reference
- [代數導論(26)](https://hackmd.io/@0xff07/rkKJEpWuU)