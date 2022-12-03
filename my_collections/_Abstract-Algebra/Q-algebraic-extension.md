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

By [this theorem](#theorem-basis-for-falpha) and [this corollary](../N-zeros-of-polynomials/#corollary-the-multiplicative-group-of-a-field), we know that $$F(\alpha)$$ is finite and $$F^\times(\alpha)$$ is cyclic. Now, for any non-zero $$g(\alpha) \in F(\alpha)$$, let $$\text{ord}(g(\alpha)) = d $$. Then we have $$f(x) = x - x^{d+1} \in F[x]$$ such that 

$$
f\big(g(\alpha)\big) = g(\alpha) - \big(g(\alpha)\big)^{d+1} = 0.
$$

Therefore, the statement has been proved. ◼

---

## Definition (finite extension; degree)
> If an extension field $$E$$ of a field $$F$$ is of **finite dimension $$n$$**, then $$E$$ is a **finite extension of degree $$n$$ over $$F$$**. We let $$[E:F]$$ denote the degree of $$E$$ over $$F$$.

### Remark 

定義中的 **finite** 指的是 *dimension* 有限，也就是 $$\deg(\alpha, E)$$ 有限，而非 $$E$$ 是 finite field。例如，$$\mathbb{Q}[i]$$ is a finite extension of degree $$2$$ of $$\mathbb{Q}$$，但 $$\mathbb{Q}[i]$$ 有無限多個元素。

### Theorem (finite to algebraic)
> A **finite extension** $$E$$ of a field $$F$$ is an **algebraic extension**.

**Proof**

Let $$\alpha \in E$$, and assume $$[E:F]=n$$. Then the $$n+1$$ vectors $$1,\alpha,\cdots,\alpha^n$$ are linearly dependent over $$F$$. Thus, there are elements $$a_i$$, not all zero, such that $$a_0+a_1\alpha+\cdots+a_n\alpha^n = 0$$, which implies that $$\alpha$$ is algebraic over $$F$$. ◼ 

### Theorem (series of finite extension)
> If $$E$$ is a finite extension of a field $$F$$, and $$K$$ is a finite extension of $$E$$, then $$K$$ is a finite extension of $$F$$ and $$[K:F] = [K:E][E:F]$$.

**Proof**

Let $$\{\alpha_1,\cdots,\alpha_m \}$$ be a basis for $$E$$ over $$F$$, and $$\{\beta_1,\cdots,\beta_n \}$$ be a basis fo r$$K$$ over $$E$$. It suffices to prove that 

- Every element of $$K$$ is a linear combination of $$\{\alpha_i\beta_j\}$$, for $$i=1,\cdots,m, j=1,\cdots,n$$, with coefficients in $$F$$, and
- $$\{\alpha_i\beta_j\}$$ are linearly independent over $$F$$.

Let $$\gamma \in K$$. Then $$\gamma =\sum_{i=1}^m e_i\alpha_i$$ for some $$e_i \in E$$ since $$\{\alpha_i\}$$ is a basis for $$K$$ over $$E$$. Each $$e_i$$ can also be expressed as $$e_i = \sum_{j=1}^n f_{ij}\beta_j $$ since $$\{\beta_j\}$$ is a basis for $$E$$ over $$F$$. Thus, $$\gamma = \sum_{i,j}f_{ij}\alpha_i\beta_j$$, which implies that every element of $$K$$ is a linear combination of $$\{\alpha_i\beta_j\}$$ over $$F$$.

Now suppose that $$f_{ij}$$ are elements in $$F$$ such that $$\sum_{i,j}f_{ij}\alpha_i\beta_j = 0$$. Write it in the form

$$
\sum_{i=1}^m \Big(\sum_{j=1}^n f_{ij}\beta_j \Big)\alpha_i = 0,
$$

where $$\sum_{j=1}^n f_{ij}\beta_j \in E$$. Since $$\{\alpha_i\}$$ are linearly independent over $$E$$, $$\sum_{j=1}^n f_{ij}\beta_j$$ must be zero for all $$i$$. Then $$f_{ij}=0$$ for all $$j$$ since $$\{\beta_j\}$$ are linearly independent over $$F$$. ◼

#### Corollary (more series)
> If $$F_1\le \cdots\le F_n$$ is a series of finite extension of fields, then $$[F_n:F_1] = [F_n:F_{n-1}]\cdots[F_2:F_1]$$.

#### Corollary (degree divides)
> Let $$E$$ be an extension field of $$F$$ and $$\alpha \in E$$ is algebraic over $$F$$. If $$\beta\in F(\alpha)$$, then $$\deg(\beta, F)$$ **divides** $$\deg(\alpha, F)$$.

**Proof**

Since $$\beta\in F(\alpha)$$, $$F(\alpha, \beta) = F(\alpha)$$. Let $$E=F(\beta)$$ and $$K=F(\alpha, \beta)$$. Then by the above theorem, this corollary has been proved. ◼

## Corollary (degree constriants)
> Assume that $$E=F(\alpha, \beta)$$ is an algebraic extension of $$F$$. Let $$n=\deg(\alpha, F)$$ and $$m=\deg(\beta, F)$$. Then
>
> - $$[E:F]\le mn$$,
> - $$\text{lcm}(m,n)\big\vert [E:F]$$.