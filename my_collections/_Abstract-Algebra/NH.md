---
layout: page
title: Group Structure of NH
usemathjax: true
tag: Abstract Algebra, Group, direct product
time: 2023/02/24
---

**Table of Content**
- [Group structure of $$NH$$](#group-structure-of-nh)
  - [Theorem (two normal subgroups)](#theorem-two-normal-subgroups)
  - [Semi-direct product](#semi-direct-product)
    - [**Theorem (semi-direct product)**](#theorem-semi-direct-product)
    - [Remark](#remark)
    - [Theorem (some properties)](#theorem-some-properties)
    - [Theorem (all group structures)](#theorem-all-group-structures)
      - [**Remark**](#remark-1)
    - [**Theorem (determine structure of $$G$$)**](#theorem-determine-structure-of-g)
      - [Remark](#remark-2)
    - [Theorem (groups of order $$2p$$)](#theorem-groups-of-order-2p)
- [Reference](#reference)

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

---

Then, consider one subgroup is **normal** and the other is arbitrary.

### Semi-direct product

Now, suppose $$N$$ is normal and $$N\cap H = \{e\}$$. By [this theorem](../3-isomorphism/#theorem-unique-product), the elements in $$NH$$ can be uniquely represented as $$nh$$ for some $$n\in N$$ and $$h\in H$$. Moreover. the product of two elements $$n_1h_1$$ and $$n_2h_2$$ can be written as

$$
n_1h_1n_2h_2 = n_1(h_1n_2h_1^{-1})h_1h_2 = n_1\rho_{h_1}(n_2)h_1h_2,
$$

where $$\rho_{h_1}(x) := h_1xh_1^{-1}$$ is an [inner automorphism](../more-on-normal-subgroups/#inner-automorphism) on $$N$$.

> $$\rho: H\to \text{Aut}(N)$$, given by $$h_1\mapsto \rho_{h_1}$$.

Then, consider the binary structure **$$N \rtimes_{\rho} H$$** defined on $$N\times H$$ given by

$$
(n_1, h_1)*(n_2, h_2) = (n_1, h_1)(n_2, h_2) := (n_1\rho_{h_1}(n_2), h_1h_2).
$$

> 這是定義在 $$N\rtimes_{\rho} H$$ 上的乘法，而 $$N\rtimes_{\rho} H$$ 的 elements 和 $$N\times H$$ 一模一樣！

Let's first prove that $$(N\rtimes_{\rho}H, *)$$ is a group:

<u>associativity</u>

Expand everything.

<u>identity</u>

$$(e_N, e_H)$$.

<u>inverse</u>

Let $$(n_2, h_2) = (n_1, h_1)^{-1}$$. Then $$(n_1, h_1)(n_2, h_2) = (e, e)$$, which means that $$n_1h_1n_2h_1^{-1} = e$$ and $$h_1h_2 = e$$. Thus we have 

$$
(n_1, h_1)^{-1} = (n_2, h_2) = (h_1^{-1}n_1h_1, h_1^{-1}). \tag*{$\blacksquare$}
$$


Then prove that $$(N\rtimes_{\rho}H, *) \cong (NH, \cdot)$$. Define $$\phi: NH\to N\rtimes_{\rho}H$$ given by $$nh\mapsto (n, h)$$. Here we only show that $$\phi$$ is a homomorphism:

$$
\begin{align*}
\phi(n_1h_1n_2h_2) &= \phi(n_1\rho_{h_1}(n_2)h_1h_2) \\
&= (n_1\rho_{h_1}(n_2), h_1h_2) \\
&= \phi(n_1h_1)\phi(n_2h_2). \tag*{$\blacksquare$}
\end{align*}
$$

Especially, the group $$N\rtimes_{\rho}H$$ is called the **semi-direct product** of $$N$$ and $$H$$ with respect to $$\rho$$.

> 因為 $$NH$$ 是 group，所以證明 $$NH$$ 和 $$N\rtimes_{\rho}H$$ 同構也就證明了 $$N\rtimes_{\rho}H$$ 是 group！

#### **Theorem (semi-direct product)**
> Let $$H$$ and $$N$$ be two subgroups of a finite group $$G$$. Suppose $$N$$ is **normal** and $$H\cap N = \{e\}$$. Then **there exists some group homomorphism $$\rho:H\to \text{Aut}(N)$$ such that $$NH \cong N\rtimes_{\rho}H$$**.

> 當其一 normal 且兩者交集只有 identity！

#### Remark

The binary structure $$(N\rtimes_{\rho}H, *)$$ **only** involves *the group operation of $$N$$, the group operation of $$H$$, and the group homomorphism $$\rho$$.*

因為 $$NH \leq G$$，所以如果 $$\vert NH\vert = \vert G\vert $$，則 $$NH=G$$。參考 [Three Isomorphism Theorems](../3-isomorphism/#theorem-unique-product)。

#### Theorem (some properties)
> Let $$H$$ and $$N$$ be two groups and $$\rho$$ is a group homomorphism from $$H$$ to $$\text{Aut}(N)$$. Then $$G_{\rho}=N\rtimes_{\rho}H$$ is a group satisfying the following conditions:
>
> - $$N'= N\times \{e_H\} \cong N$$, which is a normal subgroup of $$G_\rho$$.
> - $$H'= \{e_N\}\times H\cong H$$, which is a normal subgroup of $$G_\rho$$.
> - $$N' \cap H' = \{(e, e)\}$$ and $$G_{\rho} = N'H'$$.
> - For all $$n' = (n, e_H)\in N', h'=(e_N, h)\in H'$$, 
>
> $$
>   h'n'h'^{-1} = (\rho_h(n), e_H),
> $$
>
> where $$\rho_h(n) = hnh^{-1}$$.

#### Theorem (all group structures)
> Let $$H$$ and $$N$$ be two subgroups of a finite group $$G$$. Suppose
>
> - $$N$$ is normal;
> - $$\vert H\cap N\vert = 1$$;
> - $$\vert G\vert = \vert N\vert \vert H\vert $$,
>
> then
>
> $$
> \{N\rtimes_\rho H \mid \rho: H\to \text{Aut}(N)\}
> $$
>
> consists all possible group structures of $$G$$. 

##### **Remark**

- 也看看[這](../3-isomorphism/#theorem-unique-product)。
- $$\rho: H\to \text{Aut}(N)$$ 是 group homomorphism！
- It is possible that $$N\rtimes_\rho H\cong N\rtimes_{\rho'}H$$ for *distinct* $$\rho$$ and $$\rho'$$.
- When $$\rho$$ is the trivial homomorphism, $$N\rtimes_\rho H \cong N\times H$$.

#### **Theorem (determine structure of $$G$$)**

> Let $$G$$ be a group with a **normal** subgroup  $$N=\langle a\rangle$$ of order $$n$$ and a subgroup $$H=\langle b\rangle$$ of order $$m$$, where $$\gcd(n, m) = 1$$ and $$\vert G\vert=nm$$. Then **$$G$$ is isomorphic to $$N\rtimes_\rho H$$** where $$\rho_b(a) = a^k$$ for some $$k$$ satisfying $$k^m \equiv 1 \pmod n$$.

**Proof** (?)

##### Remark

這裡的 $$\rho$$ 一樣是 $$\rho: H\to \text{Aut}(N)$$。因為 $$\rho$$ 是 group homomorphism，所以一旦 $$\rho_b(a) = a^k$$ 決定了，$$\rho_{b^r}(a)$$ 必然是 $$(a^k)^r$$，於是 $$\rho_b$$ 唯一決定了 $$\rho$$（用 generator 就夠）。

又因為 $$b$$ 的 order 是 $$m$$，於是 $$\rho_{b^m}$$ 是 identity map，亦即 $$\rho_{b^m}(a) = a = (a^k)^m$$、對於某些滿足 $$k^m \equiv 1 \pmod n$$ 的 $$k$$。

然後：

$$
N\rtimes_\rho H = \langle a,b\mid a^n=b^m=e, bab^{-1}=a^k\rangle.
$$

> 想想 [Dihedral groups](../n-gons/#dihedral-group)！

**這個定理的意義在於**，如果 $$G$$ 可以找到兩個 cyclic subgroups（其中一個 normal），我們可以用只牽涉到該 subgroups 的 order 的同餘式，來明確的找出所有 $$G$$ 可能的結構！（用到[這個定理](#theorem-all-group-structures)。）

> Check [this](../3-isomorphism/#theorem-unique-product).

#### Theorem (groups of order $$2p$$)
> Let $$G$$ be a group of order $$2p$$ where $$p$$ is an odd prime. Then $$G\cong \Bbb Z_{2p}$$ or $$D_p$$.

**Proof**

By [Cauchy's theorem](../more-group-action/#theorem-cauchys-theorem), $$G$$ contains a subgroup $$N=\langle a\rangle$$ of order $$p$$ and a subgroup $$H=\langle b\rangle$$ of order $$2$$. Since $$[G:N]=2$$, $$N$$ is normal. Moreover, $$\vert G\vert =\vert N\vert \vert H\vert $$ and $$\vert N\cap H\vert =1$$. Therefore by [this theorem](#theorem-cyclic-subgroups), $$G$$ is isomorphic to $$N\rtimes_\rho H$$ where $$\rho_b(a) = a^k$$ for some $$k$$ with $$k^2\equiv 1\pmod p$$.

Since $$\Bbb Z_p$$ is a [field](../zeros-of-polynomials/#corollary-distinct-zeros), $$x^2=1$$ has at most $$2$$ distinct zeros; here, $$1$$ and $$-1$$.

When $$k=1$$, $$\rho$$ is the trivial homomorphism, which implies that 
  
$$
N\rtimes_\rho H \cong N\times H\cong \Bbb Z_p\times \Bbb Z_2 \cong \Bbb Z_{2p}.
$$

When $$k=-1$$, $$bab^{-1} = \rho_b(a) = a^{-1}$$, which implies that 

$$
N\rtimes_\rho H = \langle a, b\mid a^p=b^2=e, bab^{-1}=a^{-1}\rangle \cong D_p. \tag*{$\blacksquare$}
$$

---

## Reference
- [代數導論(26)](https://hackmd.io/@0xff07/rkKJEpWuU)