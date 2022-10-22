---
layout: page
title: Homomorphism
usemathjax: true
tag: Abstract Algebra, Group Theory
time: 2022/10/20
---

**Table of Content**
- [Properties](#properties)
  - [Corollary (injective homomorphism)](#corollary-injective-homomorphism)
- [Facts](#facts)
  - [fact $$\rm I$$](#fact-rm-i)
  - [fact $$\rm II$$](#fact-rm-ii)
- [Kernel](#kernel)
  - [Definition (kernel)](#definition-kernel)
  - [Theorem (kernel and coset)](#theorem-kernel-and-coset)
  - [Corollary (one-to-one)](#corollary-one-to-one)
- [Normal Subgroups](#normal-subgroups)
  - [Definition (normal subgroup)](#definition-normal-subgroup)
  - [Corollary (kernel is normal)](#corollary-kernel-is-normal)
  - [Proposition](#proposition)

---

## Properties

Let $$\phi$$ be a homomorphism of a group $$G$$ into a group $$G'$$.

- $$\phi(e) = e'$$.
- $$\phi(a^{-1})=\phi{(a)}^{-1} \text{ for all } a \in G$$.
- If $$H$$ is a subgroup of $$G$$, then $$phi(H)$$ is a subgroup of $$G'$$.

> $$\phi(H)$$ is the **image** of $$H$$.

- If $$H'$$ is a subgroup of $$G'$$, then $$\phi^{-1}(H')$$ is a subgroup of $$G$$.

> $$\phi^{-1}(H)$$ is the **preimage** of $$H'$$.

> 請嘗試證明，尤其是 subgroup 的部分。

### Corollary (injective homomorphism)
> Let $$\phi: G\to G'$$ be a group homomorphism. If $$\phi$$ is **one-to-one** then $$G$$ and $$\phi(G)$$ are **isomorphic**. 

> 顯然 $$\phi: G \to \phi(G) $$ 已經 onto。

## Facts

Let $$\phi: G\to G'$$ be a group homomorphism.

### fact $$\rm I$$

For $$a \in G$$, suppose its order is $$n$$. Since $$\phi$$ is homomorphism, we have

$$
\phi(a^n) = \phi(e) = e' = \phi(a)^n,
$$

and thus 

$$
\text{ord}(\phi(a))\big\vert n.
$$

### fact $$\rm II$$

If $$\gcd(\vert G \vert, \vert G' \vert) = 1$$, for all $$g$$ in $$G$$, we let $$n = \text{ord}(\phi(g))$$ and $$m = \text{ord}(g)$$.

By Lagrange's Theorem, we have 

$$
n \big\vert \vert G' \vert,\ m \big\vert \vert G \vert.
$$

Moreover, by the definition of order, we have

$$
\phi(g^m) = e',
$$

which implies that $$\phi(g)^m$$ is identity and the order of $$\phi(g)$$ divides $$m$$. From this result, we can further observe that

$$
n \big\vert \vert G \vert, \\
\Rightarrow n \big\vert \gcd(\vert G \vert, \vert G' \vert) = 1,
$$

which means that $$n$$ is one. Thus for all $$\phi(g)$$ in $$G'$$, the order of them are one, i.e. $$\phi$$ is a **trivial homomorphism**.



---

## Kernel
### Definition (kernel)
> The **subgroup** $$\phi^{-1}(\{e'\}) $$ is called the **kernel** of $$\phi$$, denoted by **$$\text{ker}(\phi)$$**.

也就是說，對於任意在 domain $$X$$ 的 $$x$$，只要 $$\phi(x) = e'$$，那麼 $$x$$ 就在 $$\text{ker}(\phi)$$ 中！

**Example**

We know that 

$$
\text{sgn: }S_n \to \{\pm 1\}
$$

is a group homomorphism, and therefore $$A_n = \text{ker(sgn)}$$ is a **subgroup** of $$S_n$$.

> $$A_n$$ 是 [even permutation 形成的 subgroup！](../D-transpositions/#corollary-even-permutation)

### Theorem (kernel and coset)

Let $$\psi: G\to G'$$ be a group homomorphism, and let $$H = \text{ker}(\psi)$$. Let $$a\in G$$. Then the set

$$
\{x \in G: \psi(x)=\psi(a) \} = \psi^{-1}(\{\psi(a) \})
$$

is the **left coset $$aH$$**, and is also the **right coset $$Ha$$**.

> $$\psi^{-1}(\{\psi(a) \})$$ 是 $$\psi(a)$$ 的 preimage！（$$\psi(a)$$ 來的地方。）

### Corollary (one-to-one)

> A group homomorphism $$\psi: G \to G'$$ is **one-to-one** iff $$\text{ker}(\psi) = \{e\}$$.

One-to-one 本來就會使 $$\text{ker}(\psi) = \{e\}$$；而當 $$\text{ker}(\psi) = \{e\}$$ 時，對於任意 $$a \in G$$，他的 preimage 都是 $$aH = a$$，也就證明了 one-to-one。

**Proof of the theorem** 

We first show that $$aH \subseteq \psi^{-1}(\{\psi(a)\})$$: Let $$x=ah\in H$$. Since $$\psi$$ is a homomorphism, we ahve $$\psi(x) = \psi(a)\psi(h) = \psi(a)e' = \psi(a)$$. Therefore, $$x \in \psi^{-1}(\{\psi(a)\})$$.

Then, we are to show that $$\psi^{-1}(\{\psi(a)\}) \subseteq aH$$ : Suppose that $$x \in \psi^{-1}(\{\psi(a)\})$$. We have $$\psi(x) = \psi(a)$$, and thus $$\psi(a)^{-1}\psi(x) = e'$$. Then $$\psi(a^{-1})\psi(x) = \psi(a^{-1}x) = e'$$, which implies that $$a^{-1}x \in H$$. We see that $$x \in aH$$.

The proof for the right coset is similar. ◼

**Example**

Let $$\psi: \mathbb{Z} \to \mathbb{Z}_n $$ defined by $$\psi(a) = \bar a$$; then $$\text{ker}(\psi) = n\mathbb{Z}$$. For each $$\bar b \in \mathbb{Z}_n$$, its preimage $$\psi^{-1}(\{\bar b\}) = \{\cdots,b-n,b,b+n,\cdots \} = b + n\mathbb{Z}$$ is indeed a coset. 

---

## Normal Subgroups
### Definition (normal subgroup)

> A subgroup $$H$$ of a group $$G$$ is **normal** if its left cosets and right cosets concide, that is, if 
>
>$$
> gH = Hg,\ \text{for all } g \in G.
>$$
> If $$H$$ is a normal subgroup of $$G$$, we denoted it as $$H \triangleleft G $$.

### Corollary (kernel is normal)
> If $$\psi: G\to G'$$ is a group homomorphism, then $$\text{ker}(\psi)$$ is a normal subgroup.

> From [this theorem](#theorem-kernel-and-coset).

### Proposition

> Let $$N$$ be **a subgroup of [index](../F-Lagrange-thm/#index) two** of $$G$$. Then $$N$$ is normal.

**Proof**

For $$g \in G$$, if $$g \in N$$, then $$gN = N = Ng$$. If $$g \not \in N$$, then $$G=N \bigsqcup gN = N \bigsqcup Ng$$, and therefore $$gN = G\backslash N = Ng$$. We now have $$gN = Ng$$. ◼