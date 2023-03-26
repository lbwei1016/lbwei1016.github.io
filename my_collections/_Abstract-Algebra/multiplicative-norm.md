---
layout: page
title: Multiplicative Norm
usemathjax: true
tag: Abstract Algebra, Norm
time: 2023/03/22
---

**Table of Content**
- [Definition (multiplicative norm)](#definition-multiplicative-norm)
  - [Theorem (properties)](#theorem-properties)
- [Multiplicative Norm as Euclidean Function](#multiplicative-norm-as-euclidean-function)
  - [**Example**](#example)


---

## Definition (multiplicative norm)
> Let $$D$$ be an integral domain. A **multiplicative norm** $$N$$ on $$D$$ is a function $$N: D\to \Bbb Z$$ such that 
>
> 1. $$N(\alpha)=0$$ iff $$\alpha=0$$,
> 2. $$N(\alpha\beta)=N(\alpha)N(\beta)$$ for all $$\alpha,\beta\in D$$.

### Theorem (properties)
> Let $$D$$ be an integral domain with a multiplicative norm $$N$$. Then
>
> 1. $$N(1)=1$$,
> 2. if $$u\in D$$ is a **unit**, then $$N(u)=\pm 1$$,
> 3. Assume that every $$\alpha\in D$$ satisfying $$N(\alpha)=\pm 1$$ is a unit. If $$\pi$$ is an element such that $$N(\pi) =\pm p$$ for some prime $$p\in \Bbb Z$$, then $$\pi$$ is an **irreducible** in $$D$$.

---

## Multiplicative Norm as Euclidean Function

For any multiplicative norm $$N(a)$$, let $$\nu(a) := \vert N(a)\vert$$. We can verify that [EF2](../UFD-PID-ED/#definition-ed) is satisfied. It remains to show that $$\nu$$ satisfies **EF1**. Consider the following example.

> Let $$D=\Bbb Z[\sqrt{2}]$$. Define a multiplicative norm on $$D$$ that is a Euclidean function.

Let us regard $$D$$ as a subring of $$\Bbb Q(\sqrt{2})$$. The [left multilplication](../matrix-rep-of-extension) by $$x=a+b\sqrt{2}\in\Bbb Q(\sqrt{2})$$, denoted by $$L_x$$, is a linear transformation on $$D$$, so that 

$$
[L_x]_\alpha = \begin{pmatrix}
  a & 2b \\ b & a
\end{pmatrix}.
$$

In this case, we can define the norm function as 

$$
N(x) = \det(L_x) = a^2 - 2b^2,
$$

which satisfies the property $$N(xy)=N(x)N(y)$$ for all $$x,y\in Q(\sqrt{2})$$. Moreover, since $$x\to L_x$$ is a ring homomorphism and every nonzero element in $$\Bbb Q(\sqrt{2})$$ is invertible (a field), $$\det(L_x)\not = 0$$ when $$x\not = 0$$. Therefore, $$N(x)=0$$ iff $$x=0$$. 

> $$\det$$ 保持乘法！

### **Example** 

> Show that $$D$$ is a Euclidean domain.

**Solution**

First, re-define the norm function as $$N(a+b\sqrt{2})=\vert a^2-2b^2\vert$$.

Since $$D$$ is a subring of $$\Bbb Q(\sqrt{2})$$ with unity, $$D$$ is an integral domain.

Let $$a, b\in D$$. In $$\Bbb Q(\sqrt{2})$$, write $$a/b = c_1+c_2\sqrt{2}$$, where $$c_1, c_2 \in \Bbb Q$$.

Choose $$q_1, q_2\in \Bbb Z$$ be the **cloest integers** to $$c_1$$ and $$c_2$$ respectively, such that $$\vert q_i-c_i\vert \le {1\over 2}$$ for $$i=1, 2$$. Let $$q=q_1+q_2\sqrt{2} \in D$$ and $$r=a-bq$$.

We are to show that either $$r=0$$ or $$N(r)<N(b)$$. Suppose $$r\not=0$$. Then

$$
\begin{align*}
N(r) &= N(a-bq) = N(b)N({a\over b}-q) \\
&= N(b)N\big((c_1+c_2\sqrt{2}) - (q_1+q_2\sqrt{2})\big) \\
&= N(b)\vert (c_1-q_1)^2 - 2(c_2-q_2)^2\vert \\
&\le N(b)\big(2\cdot ({1\over 2})^2\big) < N(b).
\end{align*}
$$

Thus, for any $$a, b\in D$$, there exist $$q, r\in D$$ such that $$a=bq + r$$ with $$r=0$$ or $$N(r)<N(b)$$. Since $$N$$ is a multiplicative norm, which already satisfies **EF2**, we now have proved $$D$$ is a Euclidean domain. ◼

> $$N(x)$$ 定義在 $$\Bbb Q(\sqrt{2})$$ 上，因此 $$N({a\over b}-q)$$ 是合法的。