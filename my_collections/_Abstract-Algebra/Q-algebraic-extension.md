---
layout: page
title: Algebraic Extension
usemathjax: true
tag: Abstract Algebra, Polynomial, Field, Linear Algebra
time: 2022/12/02
---

**Table of Content**
- [Vector Space](#vector-space)
  - [Definition (vector space over a field)](#definition-vector-space-over-a-field)
    - [Lemma (extension field is a vector space)](#lemma-extension-field-is-a-vector-space)
  - [Definition (linear independence)](#definition-linear-independence)
  - [Theorem (basis)](#theorem-basis)
- [Definition (algebraic extension)](#definition-algebraic-extension)
  - [Exercise](#exercise)
- [Definition (finite extension; degree)](#definition-finite-extension-degree)
  - [Remark](#remark)
  - [Theorem (finite to algebraic)](#theorem-finite-to-algebraic)
  - [Theorem (series of finite extension)](#theorem-series-of-finite-extension)
    - [Corollary (more series)](#corollary-more-series)
    - [Corollary (degree divides)](#corollary-degree-divides)
    - [**Corollary (degree constriants)**](#corollary-degree-constriants)
  - [Exercise 1](#exercise-1)
  - [**Exercise 2**](#exercise-2)
    - [Remark](#remark-1)


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

### Theorem (basis)
> Let $$\alpha\in E$$, where $$E$$ is a field extension of $$F$$.
>
> 1. If $$\alpha$$ is **algebraic over $$F$$** with $$\deg(\alpha, F) = n$$, then $$F(\alpha)$$ is a **finite-dimensional vector space over $$F$$**, with basis $$\{1, \alpha, \cdots, \alpha^{n-1} \}$$. This means that $$\dim(F(\alpha)) = n$$. 
> 2. If $$\alpha$$ is **not algebraic** over $$F$$, then $$F(\alpha)$$ is an **infinite**-dimensional vector space over $$F$$.

**Proof**

If $$\alpha$$ is algebraic over $$F$$, then by [this theorem](../P-field-extension/#theorem-unique-expression), $$\{1, \alpha, \cdots, \alpha^{n-1} \}$$ is indeed a basis for $$F(\alpha)$$.

If $$\alpha$$ is transcendental over $$F$$, then the vectors $$1, \alpha, \alpha^2, \cdots$$ are linealy independent. Thus, $$F(\alpha)$$ is not finite-dimensional. ◼

---

## Definition (algebraic extension)
> An extension field $$E$$ of a field $$F$$ is an **algebraic extension of $$F$$** if **every** element in $$E$$ is algebraic over $$F$$.

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

#### **Corollary (degree constriants)**
> Assume that $$E=F(\alpha, \beta)$$ is an algebraic extension of $$F$$. Let $$n=\deg(\alpha, F)$$ and $$m=\deg(\beta, F)$$. Then
>
> - $$[E:F]\le mn$$,
> - $$\text{lcm}(m,n)\big\vert [E:F]$$.

**Proof**

[Here](https://math.stackexchange.com/questions/2405616/the-degree-of-a-field-extension-is-smaller-than-the-product-of-the-degrees-of-fi) goes two nice proofs.

### Exercise 1

We have $$x^3 - 2 = (x-\sqrt[3]{2})(x-\sqrt[3]{2}\omega)(x - \sqrt[3]{2}\omega^2) $$, where $$\omega=e^{2\pi i\over 3}$$ is a zero of $$x^2+x+1$$. Then apparently, $$[\Bbb Q(\sqrt[3]{2}): \Bbb Q] = [\Bbb Q(\sqrt[3]{2}\omega):\Bbb Q] = 3$$. How about $$[\Bbb Q(\sqrt[3]{2}\omega, \sqrt[3]{2}):\Bbb Q(\sqrt[3]{2})]$$? 

First notice that $$\Bbb Q(\sqrt[3]{2}\omega, \sqrt[3]{2}) = \Bbb Q(\sqrt[3]{2}, \omega)$$. Since we have already know $$\deg(\omega, \Bbb Q(\sqrt[3]{2})) = 2$$, the desired value is therefore $$2$$.

> 因為 $$\omega^2+\omega+1 = 0$$，所以能得到上述 degree 為 $$2$$ 的結果。

### **Exercise 2**

**2.1**

Let $$F = [\Bbb Q(\sqrt{2}, \sqrt{3})]$$. We can see that $$[\Bbb Q(\sqrt{2}): \Bbb Q] = [\Bbb Q(\sqrt{3}): \Bbb Q] = 2 $$, but what about $$[F:\Bbb Q(\sqrt{2})]$$?

Note that by this [corollary](#corollary-degree-constriants), $$[F:\Bbb Q]=2$$ or $$4$$. Suppose $$[F:\Bbb Q] = 2$$; this means that $$[F:\Bbb Q(\sqrt{2})] = 1$$, and that there exists $$a_0$$ and $$a_1$$ in $$\Bbb Q$$ such that 

$$
\sqrt{3} = a_0 + a_1\sqrt{2}, 
$$

which is impossible. Therefore, $$[F:\Bbb Q]=4$$ and $$[F:\Bbb Q(\sqrt{2})] = 2$$.

**2.2**

> Let $$\alpha =\sqrt{2} + \sqrt{3}$$. Show that $$\Bbb Q(\sqrt{2}, \sqrt 3) = \Bbb Q(\alpha)$$.

It is clear that $$\Bbb Q(\alpha)\subset \Bbb Q(\sqrt 2, \sqrt 3) $$, so it remains to show that $$\Bbb Q(\alpha) \supset \Bbb Q(\sqrt 2, \sqrt 3) $$, or equivalently, $$[\Bbb Q(\alpha): \Bbb Q]=4$$.

**Solution $$\rm I$$**: show that $$\deg(\alpha, \Bbb Q) = 4$$.

Note that 

$$
3 = (\alpha-\sqrt{2})^2 = \alpha^2 - 2\sqrt{2}\alpha + 2, \\
(2\sqrt{2}\alpha)^2 = (\alpha^2-1)^2, \\
\alpha^4 - 10\alpha^2 + 1 = 0.
$$

Thus we only need to show that $$x^4 - 10x^2 + 1$$ is irreducible.

**Solution $$\rm II$$**: show that $$\{1, \alpha, \alpha^2, \alpha^3\}$$ are linearly independent, i.e., $$[\Bbb Q(\alpha): \Bbb Q]\ge 4$$.

Note that a basis of $$\Bbb Q(\sqrt 2, \sqrt 3)$$ is 

$$
\beta = \{1, \sqrt 2\} \cdot \{1, \sqrt 3\} = \{1, \sqrt 2, \sqrt 3, \sqrt 6\}.
$$

Then

$$
\begin{align*}
[1]_\beta^T &= (1, 0, 0, 0), \\
[\alpha]^T_\beta &= [\sqrt{2} + \sqrt{3}]_\beta = (0, 1, 1, 0), \\
[\alpha^2]_\beta^T &= [5 + 2\sqrt 6]_\beta = (5, 0, 0, 6), \\
[\alpha^3]_\beta^T &= [11\sqrt 2 + 9\sqrt 3]_\beta = (0, 11, 9, 0).
\end{align*}
$$

We now have a matrix and 

$$
\det \begin{pmatrix}
   1 & 0 & 5 & 0 \\
   0 & 1 & 0 & 11 \\
   0 & 1 & 0 & 9 \\
   0 & 0 & 6 & 0 \\ 
\end{pmatrix} \not = 0.
$$

Thus $$\{1, \alpha, \alpha^2, \alpha^3\}$$ are linearly independent. 

> 以 $$\{1, \sqrt{2}, \sqrt{3}, \sqrt{6}\}$$ 為基底，驗證 $$\{1, \alpha, \alpha^2, \alpha^3\}$$ 是否線性獨立。因為 $$\Bbb Q(\alpha) \subset \Bbb Q(\sqrt{2}, \sqrt{3})$$，因此我們可以用 $$\Bbb Q(\sqrt{2}, \sqrt{3})$$ 的基底來表示 $$\Bbb Q(\alpha)$$ 的元素。

> 知道 $$\{1, \alpha, \alpha^2, \alpha^3\}$$ 線性獨立後，我們[也就知道](../Q-algebraic-extension/#theorem-basis) $$\Bbb Q(\alpha)$$ over $$\Bbb Q$$ 的 degree 至少是 $$4$$！

**2.3**

> Let $$\gamma = \sqrt{2} + \sqrt{3} - \sqrt{6}$$. Find $$\text{Irr}(\gamma, \Bbb Q)$$.

**Solution $$\rm I$$**

There is no easy way to directly *see* a possible $$f(x)\in \Bbb Q$$ such that $$f(x) = \text{Irr}(\gamma, \Bbb Q)$$, unlike the case when $$\alpha = \sqrt 2 + \sqrt 3$$. Thus, we regard $$\gamma$$ as a vector of $$\Bbb Q(\sqrt 2, \sqrt 3)$$ over $$\Bbb Q$$. Then we have

$$
a_0 + a_1\gamma + \cdots + a_n\gamma^n \iff a_0[1]_\beta
 + a_1[\gamma]_\beta + \cdots + a_n[\gamma^n]_\beta = \vec{0},
$$

and

$$
\begin{align*}
[1]_\beta^T &= (1, 0, 0, 0), \\
[\gamma]^T_\beta &= (0, 1, 1, -1), \\
[\gamma^2]^T_\beta &= (11, -6, -4, 2), \\
[\gamma^3]_\beta^T &= (-36, 29, 27, -21), \\
[\gamma^4]_\beta^T &= (265, 180, -136, 92).
\end{align*}
$$

Note that $$\det[1, \gamma, \gamma^2, \gamma^3] \not = 0$$, and

$$
[\gamma^4]_\beta = 23[1]_\beta - 48[\gamma]_\beta + 22[\gamma^2]_\beta.
$$

Therefore, 

$$
\text{Irr}(\gamma, \Bbb Q) = x^4 - 22x^2 + 48 - 23.
$$

> 找到最大的 $$n$$ 使得 $$\{1, \cdots, \gamma^n\}$$ 線性獨立，而 $$\text{Irr}$$ 就可以從第 **$$n+1$$ 個向量的線性組合**得到！

> 這種方法得到的 polynomail 一定 irreducible，不須再檢查。

**Solution $$\rm II$$**

$$
\begin{align*}
&\gamma + \sqrt{6} = \sqrt{2} + \sqrt{3} \\
\implies &\gamma^2 + 2\sqrt{6}\gamma + 6 = 5 + 2\sqrt 6 \\ 
\implies &(\gamma^2 + 1)^2 = (2\sqrt{6}(1 - \gamma))^2
\end{align*}
$$

This way, we can obtain a quartic polynomial, but we still need to check whether it is **irreducible**.

#### Remark

如果要找 $$a_i$$ 使得

$$
a_0 + a_1\gamma + \cdots + a_n\gamma^n = 0，
$$

不如將 $$\gamma$$ 視為向量，檢查

$$
a_0[1]_\beta
 + a_1[\gamma]_\beta + \cdots + a_n[\gamma^n]_\beta
$$

是否線性獨立。如此一來就有好多線性代數工具可以使用！

> **Q:** How to determine if a set of vectors are linearly independent?