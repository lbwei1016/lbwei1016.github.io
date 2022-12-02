---
layout: page
title: Algebraic Extension
usemathjax: true
tag: Abstract Algebra, Polynomial, Field, Linear Algebra
time: 2022/12/02
---

**Table of Content**

---

## Vector Space
### Definition (vector space over a field)
> Let $$F$$ be a field. A **vector space over $$F$$** is an *additive group* $$V$$, together with scalar multiplication by element of $$F$$, satisfying
>
> $$
\begin{align*}
&a\alpha \in V,  \tag{1} \\
&(ab)\alpha = a(b\alpha), \tag{2} \\ 
&(a+b)\alpha = a\alpha + b\alpha,  \tag{3} \\
&a(\alpha+\beta) = a\alpha + a\beta,  \tag{4} \\
&1\alpha = \alpha, \tag{5}
\end{align*}
> $$
>
> for all $$a, b\in F$$ and all $$\alpha,\beta \in V$$.

> $$\alpha, \beta \in V$$ 之間的乘法沒有定義喔！

#### Lemma (extension field is a vector space)
> Let $$E$$ be an **extension field** of a field $$F$$. Then $$E$$ is a **vector space**  over $$F$$.

> 顯然。

### Definition (linear independence)
> 見 [Linear Independence](../../Linear-Algebra/4-0_Linear-Independence)。

### Theorem (basis for $$F(\alpha)$$)
> Let $$\alpha\in E$$, where $$E$$ is a field extension of $$F$$.
>
> 1. If $$\alpha$$ is **algebraic over $$F$$** with $$\deg(\alpha, F) = n$$, then $$F(\alpha)$$ is a **finite-dimensional vector space over $$F$$**, with basis $$\{1, \alpha, \cdots, \alpha^{n-1} \}$$. This means that $$\dim(F(\alpha)) = n$$. 
> 2. If $$\alpha$$ is **not algebraic** over $$F$$, then $$F(\alpha)$$ is an **infinite**-dimensional vector space over $$F$$.

**Proof**

If $$\alpha$$ is algebraic over $$F$$, then by [this theorem](../P-field-extension/#theorem-unique-expression), $$\{1, \alpha, \cdots, \alpha^{n-1} \}$$ is indeed a basis for $$F(\alpha)$$.

If $$\alpha$$ is transcendental over $$F$$, then the vectors $$1, \alpha, \alpha^2, \cdots$$ are linealy independent. Thus, $$F(\alpha)$$ is not finite-dimensional. ◼

---

## Definition (algebraic extension)
> An extension field $$E$$ of a field $$F$$ is an **algebraic extension of $$F$$** is **every** element in $$E$$ is algebraic over $$F$$.

### Exercise
> Show that $$F(\alpha)$$ is an algebraic extension of $$F$$, when $$\alpha$$ is algebraic over $$F$$.

**Solution**

By [this corollary](../N-zeros-of-polynomials/#corollary-the-multiplicative-group-of-a-field) and [this theorem](#theorem-basis-for-falpha), we know that $$F^\times(\alpha)$$ is cyclic and finite. Now, for any non-zero $$g(\alpha) \in F(\alpha)$$, let $$\text{ord}(g(\alpha)) = d $$. Then we have $$f(x) = x - x^{d+1} \in F[x]$$ such that 

$$
f\big(g(\alpha)\big) = g(\alpha) - \big(g(\alpha)\big)^{d+1} = 0.
$$

Therefore, the statement has been proved. ◼