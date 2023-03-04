---
layout: page
title: Algebraic Closures
usemathjax: true
tag: Abstract Algebra, Field
time: 2022/12/09
---

**Table of Content**
- [Theorem (still algebraic)](#theorem-still-algebraic)
  - [Lemma (finite degree implies algebraic)](#lemma-finite-degree-implies-algebraic)
  - [Corollary (algebraic closure)](#corollary-algebraic-closure)
  - [Corollary (all algebraic numbers)](#corollary-all-algebraic-numbers)
- [Definition (algebraically closed)](#definition-algebraically-closed)
  - [Remark](#remark)
- [Definition (algebraic closure)](#definition-algebraic-closure)
  - [Example](#example)
  - [Theorem (algebraic numbers)](#theorem-algebraic-numbers)
  - [Theorem (every field has an algebraic closure)](#theorem-every-field-has-an-algebraic-closure)

---

## Theorem (still algebraic)
> Let $$E$$ be an extension field of a field $$F$$. If $$\alpha, \beta \not = 0 \in E$$ are **algebraic over** $$F$$, then **so are $$\alpha+\beta$$ and $$\alpha/\beta$$**.

**Proof**

It suffices to prove that $$F(\alpha, \beta)$$ is a finite extension of $$F$$. 

Regarding $$f(x) = \text{Irr}(\beta, F)$$ as a polynomial in $$F(\alpha)[x]$$, we see that $$\beta$$ is algebraic over $$F(\alpha)$$. This implies that $$F(\alpha, \beta) = F(\alpha)(\beta) $$ and we have

$$
[F(\alpha, \beta):F] = [F(\alpha)(\beta):F(\alpha)][F(\alpha):F] < \infty.
$$

Therefore, $$F(\alpha, \beta)$$ is a finite extension of $$F$$. ◼

### Lemma (finite degree implies algebraic)
> For all $$\alpha \in E$$, $$\alpha$$ is algebraic over $$F$$ iff $$[F(\alpha):F] < \infty$$.

> $$F(\alpha)(\beta)$$ 就是 $$\big(F(\alpha) \big)(\beta)$$：先放 $$\alpha$$ 再放 $$\beta$$。

### Corollary (algebraic closure)
> Let $$E$$ be an extension field of $$F$$. Then the set 
>
> $$
>\overline{F}_E = \{\alpha\in E\mid \alpha \text{ is algebraic over } F \}
> $$
>
> is a **subfield** of $$E$$, the **algebraic closure of $$F$$ in $$E$$**.

### Corollary (all algebraic numbers)
> THe set $$\overline{\Bbb Q}$$ of all algebraic numbers forms a **field**.

---

## Definition (algebraically closed)
> A field $$F$$ is **algebraically closed** if **every** nonconstant polynomial in $$F[x]$$ has a **zero** in $$F$$.

### Remark

An **algebraically closed** field $$F$$ can be characterized by the property that every polynomail $$f(x)$$ in $$F[x]$$ factors into a product if **linear factors** over $$F$$. 

> 用 division algorithm 驗證 linear factor 的存在性！

This means that if $$F$$ is algebraically closed, then we will **not** get anything new by **joining zeros** of polynomials in $$F[x]$$ to $$F$$.

> 所以才說 **closed**！

## Definition (algebraic closure)
> An **algebraic closure** $$\overline F$$ of a field $$F$$ is an algebraic extension of $$F$$ that is **algebraic closed**.

> An algebraic closure of a field $$F$$ can be thought of as the **largest field** one may obtain by **algebraic means**.

### Example

- The field $$\Bbb C$$ is an algebraic closure of $$\Bbb R$$ (Fundamental theorem of algebra).
- The set $$\overline{\Bbb Q}$$ of algebraic numbers is an algebraic closure of $$\Bbb Q$$.

### Theorem (algebraic numbers)
> The set $$\overline{\Bbb Q}$$ of **algebraic numbers** is an **algebraic closure** of $$\Bbb Q$$.

**Proof**

By definition, $$\overline{\Bbb Q}$$ is an [algebraic extension](../algebraic-extension/#definition-algebraic-extension) over $$\Bbb Q$$. It remains to prove that $$\overline{\Bbb Q}$$ is algebraically closed, i.e., if $$\alpha$$ is a zero of $$f(x) \in \overline{\Bbb Q}[x]$$, then $$\alpha$$ is in $$\overline{\Bbb Q}$$.

Suppose that $$\alpha$$ is a zero of $$a_nx^n + \cdots + a_0$$, where $$a_i \in \overline{\Bbb Q}$$. We shall show that $$[\Bbb{Q}(\alpha): \Bbb Q] < \infty$$, by [this lemma](#lemma-finite-degree-implies-algebraic).

We have 

$$
\begin{align*}
[\Bbb{Q}(\alpha): \Bbb Q] &\le [\Bbb Q(\alpha, a_0, \cdots, a_n): \Bbb{Q}] \\
&= [\Bbb Q(\alpha, a_0, \cdots, a_n): \Bbb{Q}(a_0, \cdots, a_n)][\Bbb{Q}(a_0, \cdots, a_n):\Bbb Q].
\end{align*}
$$

Since $$a_n(\alpha)^n + \cdots + a_0 = 0$$, $$\deg(\alpha, \Bbb{Q}(a_0, \cdots, a_n)) \le n$$, which implies that 

$$
[\Bbb Q(\alpha, a_0, \cdots, a_n): \Bbb{Q}(a_0, \cdots, a_n)] \le n.
$$

By using the same argument as in [this proof](#theorem-still-algebraic), we see that $$[\Bbb{Q}(a_0, \cdots, a_n):\Bbb Q] < \infty$$.

Therefore, $$[\overline{\Bbb Q}(\alpha): \Bbb Q] < \infty$$ and $$\alpha$$ is algebraic over $$\Bbb Q$$. ◼

### Theorem (every field has an algebraic closure)
> Every field has an algebraic closure.

> A field may have several algebraic closures, but they are all **isomorphic**.