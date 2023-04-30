---
layout: page
title: Galois Extensions
usemathjax: true
tag: Abstract Algebra, Automorphism, Galois theory
time: 2023/04/26
---

**Table of Content**
- [Primitive Element Theorem](#primitive-element-theorem)
  - [Definition (separable polynomials)](#definition-separable-polynomials)
  - [Theorem (who is separable?)](#theorem-who-is-separable)
  - [Theorem (Primitive Element Theorem)](#theorem-primitive-element-theorem)
- [Galois Extensions](#galois-extensions)
  - [Definition (embedding)](#definition-embedding)
    - [Remark](#remark)
  - [Definition (the set of embeddings)](#definition-the-set-of-embeddings)
  - [Theorem (now all zero come)](#theorem-now-all-zero-come)
  - [Theorem (like transitive)](#theorem-like-transitive)
    - [Corollary (set size upper bound)](#corollary-set-size-upper-bound)
    - [Remark](#remark-1)
  - [Definition (Galois extension)](#definition-galois-extension)
  - [Theorem (the action of Galois groups)](#theorem-the-action-of-galois-groups)

---

## Primitive Element Theorem
### Definition (separable polynomials)
> A polynomial $$f(x)\in F[x]$$ is called **separable** if it has **no repeated zeros** in **$$\bar F$$**.

### Theorem (who is separable?)
> Every *irreducible* polynomial of a **finite field** or a field with **characteristic zero** is **separable**. 
>
> In particular, if $$F$$ is an infinite field with $$\text{char}F \not = 0$$, $$f(x)\in F[x]$$ may have repeated zeros.

### Theorem (Primitive Element Theorem)
> Every *finite* extension $$E$$ over a field $$F$$ of **characteristic zero** is a **simple** extension.

> [Wiki reference](https://en.wikipedia.org/wiki/Simple_extension#Definition)

> primitive element 這個詞有好幾個不同意思，見 [wiki](https://en.wikipedia.org/wiki/Primitive_element)。

**Proof**

[Cornell](https://pi.math.cornell.edu/~kbrown/6310/primitive.pdf)

---

## Galois Extensions
### Definition (embedding)
> Let $$F$$ be a field and let $$\alpha \in \bar F\backslash F$$. Then $$\rho$$ is called a **$$F$$-embedding** of $$F(\alpha)$$ whenever $$\rho$$ is an **injective** ring homomorphism from $$F(\alpha)$$ into $$\bar F$$, which fixes $$F$$.

#### Remark

Consider the case when $$F=\Bbb Q$$ and $$\alpha=\sqrt[3]{2}$$. Note that the other zeros of $$\text{Irr}(\sqrt[3]{2}, \Bbb Q)(x)$$ are $$\sqrt[3]{2}\omega$$ and $$\sqrt[3]{2}\omega^2$$, which are non-real. This means the only one zero of $$\text{Irr}(\sqrt[3]{2}, \Bbb Q)(x)$$ lies in $$\Bbb Q(\sqrt[3]{2})$$. From [this theorem](../more-on-automorphism/#theorem-transitive-action-on-roots), we can conclude that 

$$
\text{Aut}\Big(\Bbb Q(\sqrt[3]{2}/\Bbb Q) \Big) = \{e\}.
$$

There is nothing useful in the automorphism group. Instead, consider the following field isomorphism:

$$
\Bbb Q(\sqrt[3]{2}) \cong \Bbb Q[x]/\langle x^3-2\rangle \cong \Bbb Q(\sqrt[3]{2}\omega)\subset \bar{\Bbb Q}.
$$

We now have 

$$
\begin{align*}
    \rho: \Bbb Q(\sqrt[3]{2}) &\to \bar{\Bbb Q}, \\
    a+b\sqrt[3]{2} &\mapsto a+b\sqrt[3]{2}\omega,
\end{align*}
$$

which is an injective ring homomorphism. $$\rho$$ is called an embedding!

> 好像沒有說得很清楚，再想想。

### Definition (the set of embeddings)
> Let $$E/F$$ be a finite extension. Define $$\text{Emb}(E/F)$$ be the **set of $$F$$-embeddings of $$E$$ into $$\bar F$$**. In particular, $$\text{Aut}(E/F)\subseteq \text{Emb}(E/F)$$.

> $$\text{Emb}(E/F)$$ 只是個**集合**！

### Theorem (now all zero come)
> Let $$E/F$$ be a field extension, and let $$\alpha$$ be a zero of $$f(x)$$ in $$E$$. Then, for all $$\rho\in \text{Emb}(E/F)$$, **$$\rho(\alpha)$$ is a zero of $$f(x)$$ in $$\bar F$$**.

**Simplified Proof**

Let $$f(x) = \sum_i a_ix^i$$ and $$\alpha$$ be one of its zeros. Since $$\rho$$ is a ring homomorphism, we have 

$$
\begin{align*}
    f(\rho(\alpha)) &= \sum_i a_i\rho(\alpha)^i \\
    &= \sum_i a_i \rho(\alpha^i) \\
    &= \rho\Big(\sum_i a_i \alpha^i\Big) = 0.
\end{align*}
$$

This prove that $$\rho(\alpha)$$ is a zero of $$f(x)$$. ◼

### Theorem (like transitive)
> Let $$E/F$$ be a finite field extension, and let $$f(x)=\text{Irr}(\alpha, F)(x)$$ in $$E$$. Let $$\beta$$ be a zero of $$f(x)$$ in $$\bar F$$. Then there **exists** some $$\rho\in\text{Emb}(E/F)$$ such that $$\rho(\alpha)=\beta$$.

#### Corollary (set size upper bound)
> $$\vert \text{Emb}(E/F)\vert \le [E:F]$$.

> $$\vert \text{Emb}(E/F)\vert$$: number of **distinct** zeros of $$\text{Irr}(\alpha, F)(x)$$ in $$\bar F$$.

#### Remark

Let $$\beta$$ be another zero of $$\text{Irr}(\alpha, F)$$ in $$E = F(\alpha) $$, and let $$\beta = \rho(\alpha)$$. Then,

$$
\beta\in E \implies \rho \in \text{Aut}(E/F) \tag{1}
$$

$$
\beta\not\in E \implies \rho \in \text{Emb}(E/F)\backslash\text{Aut}(E/F)\tag{2}
$$

### Definition (Galois extension)
> Let $$E/F$$ be a field extension. If 
>
> $$
> \begin{align*}
> \text{Aut}(E/F) &= \text{Emb}(E/F) \tag{1} \\
> \vert\text{Emb}(E/F)\vert &= [E:F]   \tag{2}
>  \end{align*}
> $$
>
> are satisfied, then $$E/F$$ is called a **Galois extension**. Moreover, $$\text{Aut}(E/F)$$ is called the **Galois group** of $$E/F$$, denoted by **$$\text{Gal}(E/F)$$**.

> 第一式代表所有 zero 都在 $$E$$；第二式代表沒有重根（separable）！

### Theorem (the action of Galois groups)
> Let $$E/F$$ be a finite Galois extension with Galois group $$G$$. Suppose $$E = F(\alpha)$$. Then **$$G$$ acts transitively** on the set of zeros of the irreducible polynomial $$\text{Irr}(\alpha, F)(x)$$ of $$\alpha$$. Moreover, 
>
> $$
> \prod_{g\in G}(x-g(\alpha)) = \text{Irr}(\alpha, F)(x).
> $$

> $$G$$ 其實就是 $$\text{Aut}(E/F)$$ 呦！