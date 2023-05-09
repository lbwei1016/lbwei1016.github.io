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
  - [**Theorem (Primitive Element Theorem)**](#theorem-primitive-element-theorem)
- [Galois Extensions](#galois-extensions)
  - [**Definition (embedding)**](#definition-embedding)
    - [Remark](#remark)
  - [Definition (the set of embeddings)](#definition-the-set-of-embeddings)
  - [Theorem (now all zero come)](#theorem-now-all-zero-come)
  - [Theorem (like transitive)](#theorem-like-transitive)
    - [Corollary (set size upper bound)](#corollary-set-size-upper-bound)
    - [Remark](#remark-1)
  - [Definition (Galois extension)](#definition-galois-extension)
  - [Theorem (the action of Galois groups)](#theorem-the-action-of-galois-groups)
    - [Corollary (intermediate fields)](#corollary-intermediate-fields)
  - [Remark](#remark-2)

---

## Primitive Element Theorem
### Definition (separable polynomials)
> A polynomial $$f(x)\in F[x]$$ is called **separable** if it has **no repeated zeros** in **$$\bar F$$**.

### Theorem (who is separable?)
> Every *irreducible* polynomial of a **finite field** or a field with **characteristic zero** is **separable**. 
>
> In particular, if $$F$$ is an infinite field with $$\text{char}F \not = 0$$, $$f(x)\in F[x]$$ may have repeated zeros.

### **Theorem (Primitive Element Theorem)**
> Every *finite* extension $$E$$ over a field $$F$$ of **characteristic zero** is a **simple** extension.

> [Wiki reference](https://en.wikipedia.org/wiki/Simple_extension#Definition)

> primitive element 這個詞有好幾個不同意思，見 [wiki](https://en.wikipedia.org/wiki/Primitive_element)。

**Proof**

[Cornell](https://pi.math.cornell.edu/~kbrown/6310/primitive.pdf)

---

## Galois Extensions
### **Definition (embedding)**
> Let $$E$$ and $$F$$ be two fields. If $$\rho: F\to E$$ is an **injective** homomorphism of $$F$$ into $$E$$, then $$\rho$$ is called an **embedding of $$F$$ into $$E$$**.

> $$F$$-embedding: $$\rho(x) = x$$ for all $$x\in F$$.

> $$F$$-embedding 代表 $$F$$ 被固定住！

#### Remark

Consider the case when $$F=\Bbb Q$$ and $$\alpha=\sqrt[3]{2}$$. Note that other zeros of $$\text{Irr}(\sqrt[3]{2}, \Bbb Q)(x)$$ are $$\sqrt[3]{2}\omega$$ and $$\sqrt[3]{2}\omega^2$$, which are non-real. This means the only one zero of $$\text{Irr}(\sqrt[3]{2}, \Bbb Q)(x)$$ lies in $$\Bbb Q(\sqrt[3]{2})$$. From [this theorem](../more-on-automorphism/#theorem-transitive-action-on-roots), we can conclude that 

$$
\text{Aut}\Big(\Bbb Q(\sqrt[3]{2})/\Bbb Q \Big) = \{e\}.
$$

There is nothing useful in the automorphism group. Instead, consider the following field isomorphism:

$$
\Bbb Q(\sqrt[3]{2}) \cong \Bbb Q[x]/\langle x^3-2\rangle \cong \Bbb Q(\sqrt[3]{2}\omega)\subset \bar{\Bbb Q}.
$$

We now have 

$$
\begin{align*}
    \rho: \Bbb Q(\sqrt[3]{2}) &\to \bar{\Bbb Q}, \\
    a_0+a_1\sqrt[3]{2}+a_2\sqrt[3]{4} &\mapsto a_0+a_1\sqrt[3]{2}\omega + a_2\sqrt[3]{4}\omega^2,
\end{align*}
$$

which is an injective ring homomorphism that fixes $$\Bbb Q$$. Thus $$\rho$$ is a $$\Bbb Q$$-embedding of $$\Bbb Q(\sqrt[3]{2})$$!

> 好像沒有說得很清楚，再想想。(2023/5/9 更新)

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

**Proof**

Consider

$$
\begin{gather}
\rho: E=&F(\alpha)& \cong &F[x]/\langle f(x)\rangle& \cong 
&F(\beta)& \\

&g(\alpha)& \  &\longrightarrow& \  &g(\beta)&
\end{gather}
$$

where $$\rho$$ is a composition of two field isomorphisms, which is also a field isomorphism. ◼

> $$g(x) \in F[x]$$!

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

> 第一式代表所有 zero 都在 $$E$$（splitting）；第二式代表沒有重根（separable）！

### Theorem (the action of Galois groups)
> Let $$E/F$$ be a finite Galois extension with Galois group $$G$$. Suppose $$E = F(\alpha)$$. Then **$$G$$ acts transitively** on the set of zeros of the irreducible polynomial $$\text{Irr}(\alpha, F)(x)$$ of $$\alpha$$. Moreover, 
>
> $$
> \prod_{g\in G}(x-g(\alpha)) = \text{Irr}(\alpha, F)(x).
> $$

> $$G$$ 其實就是 $$\text{Aut}(E/F)$$ 呦！

> $$G$$ acts on the set of zeros as **permutations**!

**Proof**

For all $$k\in E$$, $$k$$ can be written as 

$$
k = a_0 + a_1\alpha + \cdots + a_{n-1}\alpha^{n-1}
$$

with $$a_i \in F$$. Then for some $$g\in G$$, 

$$
g(k) = a_0 + a_1g(\alpha) + \cdots + a_{n-1}g(\alpha)^{n-1},
$$

which means that $$g$$ is uniquely determined by $$g(\alpha)$$, i.e., there is a one-to-one correspondence between $$g$$ and $$g(\alpha)$$ for all $$g\in G$$. Moreover, since $$\vert G\vert = [E:F] = n$$ and $$g(\alpha)$$ is also a zero of $$\text{Irr}(\alpha, F)(x)$$, we have proved the theorem! ◼


#### Corollary (intermediate fields)
> Let $$E/F$$ be a Galois extension with Galois group $$G$$. Let $$[E:F] = n$$ and $$[F(\alpha):F] = m$$, for some $$\alpha \in E$$. Then
>
> $$
> \prod_{g\in G}(x-g(\alpha)) = f(x)^{n/m}.
> $$

**Proof**

Let $$H = \text{Emb}(F(\alpha)/F)$$. We have $$[G:H] = [E:F(\alpha)] = n/m$$, and can write $$G$$ as the union of $$H$$ cosets:

$$
G = H \sqcup h_1H \sqcup \cdots \sqcup h_{n/m-1}H.
$$

Moreover, by [this theorem](#theorem-the-action-of-galois-groups), we can write $$f(x)$$ as

$$
\prod_{h\in H}(x-h(x)) = f(x).
$$

Equivalently, for any coset of $$H$$,

$$
\prod_{h' \in h_iH}(x-h'(x)) = \prod_{h\in H}(x-h_ih(x)) = \prod_{h\in H}(x-h(x)) = f(x),
$$

since left multiplication only permutes $$h$$s! Thus,

$$
\prod_{g\in G}(x-g(\alpha)) = \Big(\prod_{h\in H}(x-h(x))\Big)^{n/m} = f(x)^{n/m}. \tag*{$\blacksquare$}
$$


### Remark

任何二次擴張都是 Galois！有兩種觀點可以說明：根與係數和 normal subgroup。

假設在 $$F$$ 中加入 $$\alpha$$，因為 $$\text{Irr}(\alpha, F)(x) = (x-\alpha)(x-\alpha')$$ 的係數都在 $$F$$，利用根與係數的關係，可以發現 $$\alpha'$$ 由 $$\alpha$$ 生成。

再來，因為是二次擴張，所以 $$[\text{Aut}(F(\alpha)/F): G_{F(\alpha)}]=2$$，$$G_{F(\alpha)}$$ 是 [normal subgroup](../normalizer/#theorem-smallest-index-normal)。根據 [the fundamental theorem of Galois theory](../Galois-theory/#theorem-the-fundamental-theorem-of-galois-theory)，$$F(\alpha)/F$$ 就是 Galois！