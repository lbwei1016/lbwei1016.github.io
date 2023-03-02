---
layout: page
title: Sylow Theorem
usemathjax: true
tag: Abstract Algebra, Sylow Theorem
time: 2023/03/02
---

**Table of Content**

---

## Normal Subgroups with Small Indexes
### Theorem (smallest index; normal)
> Let $$G$$ be a finite group and $$p$$ be the smallest prime factor of $$\vert G\vert$$. Then every subgroup $$H$$ of **index $$p$$** is a **normal** subgroup.

> [This proposition](../H-homomorphism-and-normal-groups/#proposition-index-two) is a special case of this theorem.

#### Proof

Let $$X=G/H$$. Then $$\vert X\vert =p$$ and $$G$$ acts on $$X$$ by left multiplication, which induces a group homomorphism $$\rho: G\to S_X$$. We claim that $$H$$ is the **kernel** of $$\rho$$, which implies that $$H$$ is normal.

From [the first isomorphism theorem](../X-3-isomorphism/#the-first-isomorphism-theorem), we have 

$$
G/\text{ker}\rho \cong \rho(G) \leq S_X,
$$

which means that 

$$
[G:\text{ker}\rho] \mid p!
\implies [G:\text{ker}\rho]\mid \gcd(p!, \vert G\vert).
$$

> $$\vert G/\text{ker}\rho\vert = [G:\text{ker}\rho]$$; $$\vert S_X\vert = p!$$.

Since $$p$$ is the smallest prime divisor of $$\vert G\vert$$, $$[G:\text{ker}\rho] = 1$$ or $$p$$.

On the other hand, we have

$$
\text{ker}\rho = \bigcap_{xH\in X} \text{Stab}_G(xH) \subset \text{Stab}_G(H) = H.
$$

> For some $$xH\in X$$ and for all $$g\in \text{Stab}_G(xH), gxH = \rho(g)xH = xH$$.

> 然後取交集，對所有 $$xH\in X$$！

Comparing the indexes, we have

$$
[G : \text{ker}\rho] = [G : H][H : \text{ker}\rho] = p[H : \text{ker}\rho].
$$

Together with the result $$[G:\text{ker}\rho]=1$$ or $$p$$, we conclude that $$[G:\text{ker}\rho]=p$$ and $$[H:\text{ker}\rho]=1$$, which implies that $$H=\text{ker}\rho$$. ◼

### Corollary (two primes)
> If $$\vert G\vert = pq$$, where $$p>q$$ are two primes, then $$G$$ contains a normal subgroup of order $$p$$.

---

## Sylow Theorem

Sylow theorems can be used to find normal subgroups, and in turn [determine group structures](../Y-NH/#theorem-determine-structure-of-g)!

### **Theorem (Sylow theorems)**
> Suppose $$\vert G\vert=p^nm$$ where $$p$$ is a prime with $$p\not \mid m$$.
>
> 1. There exists a subgroup of order $$p^i$$ for $$1<i\leq n$$. Moreover, **every subgroup of order $$p^i$$ is normal in some subgroup of order $$p^{i+1}$$** when $$i<n$$.
> 2. Any two **Sylow $$p$$-subgroups** are **conjugated**.
> 3. Let **$$n_p$$** be the number of **Sylow p-subgroups**. Then $$n_p$$ satisfies the following **two conditions**:
>
> $$
> \begin{align*}
> &n_p \equiv 1 \pmod p, \tag{1}  \\
> &n_p \mid m. \tag{2}
> \end{align*}
> $$

> The subgroup $$H$$ of order $$p^n$$ is called a **Sylow $$p$$-subgroup**, which is exactly a maximal $$p$$-subgroup.

#### Corollary (contain; normal)
> 1. Every $$p$$-subgroup is contained in a Sylow $$p$$-subgroup.
> 2. **A Sylow $$p$$-subgroup is normal iff $$n_p = 1$$.**