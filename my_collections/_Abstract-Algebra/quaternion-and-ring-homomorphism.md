---
layout: page
title: Quaternion and Ring Homomorphism
usemathjax: true
tag: Abstract Algebra, Quaternion, Ring
time: 2023/03/17
---

**Table of Content**


---

## Hamiltonian Quaternion

Hamiltonian Quaternion $$\Bbb H$$ is a **four dimensional vector space** over $$\Bbb R$$ with the basis $$\{1,i,j,k\}$$, and its multiplication is characterized by

$$
\begin{align*}
i^2=j^2=k^2=-1, \\
ij=-ji=k, \\
jk=-kj=i, \\
ki=-ik=j.
\end{align*}
$$

> 有乘法的 vector space 叫做 **algebra**！

Let $$V$$ be the subspace of $$\Bbb H$$ spanned by $${i,j,k}$$. Let $$\Bbb R$$ be the subspace of $$Bbb H$$ spanned by $$1$$. Then we have

$$
\Bbb H = \Bbb R \oplus V
$$

> $$\oplus$$ 是 direct sum！

That is to say, every element of $$\Bbb H$$ can be written as **$$a+\vec u$$**, where $$a\in \Bbb R$$ and $$\vec u \in V$$.

### Theorem (vector multiplication)
> For $$\vec u, \vec v \in V$$, we have
>
> $$
> \vec u\vec v = -\vec u\cdot\vec v + \vec u\times \vec v.
> $$

**Proof**

展開即證明。

### Theorem (Quaternion rotation)
> Let $$T$$ be a **counter-clockwise rotation** of $$\theta$$-degree with respect to the $$\vec u$$-axis, where $$\vec u$$ is an unit vector in $$\Bbb{R}^3$$. Consider the quaternion
>
> $$
> q=\cos{\theta\over 2} + \sin{\theta\over 2}\vec u.
> $$
>
>Then for all $$\vec v \in \Bbb R$$, 
>
>$$
>T(\vec v) = q\vec v \bar q.
>$$

> $$q\bar q = 1$$.

**Proof**

Let $$T_q(z) = qz\bar q$$ be a map from $$\Bbb H$$ to $$\Bbb H$$. We can see that $$T_q$$ is a linear map.

> $$
\begin{align*}
> T_q(x+y) &= q(x+y)\bar{q} = qx\bar{q} + qy\bar{q}, \\
> T_q(ax) &= q(ax\bar{q}) = a(qx\bar{q}).
\end{align*}
> $$

We shall show that $$T_q(V)\subset V$$ and $$T_q\vert_V = T$$.

Note that $$\vec u,q,\bar q$$ all commute. Thus $$T_q(\vec u) = \vec uq\bar q = \vec u = T(\vec u)$$. Now choose $$\vec v\in V$$, such that $$\vec v\cdot \vec u = 0$$ and whise norm is $$1$$. Then $$\{\vec u, \vec v, \vec u\times \vec v \}$$ forms an orthonormal basis of $$V$$. It remains to show that $$T_q(\vec v) = T(\vec v)$$ and $$T_q(\vec u\times \vec v) = T(\vec u\times \vec v)$$.

> 轉 basis 中的 vector 就夠了！

First, note that 

$$
T(v) = \cos\theta\vec v + \sin\theta(\vec u\times \vec v).
$$

> 用平面來想：$$\vec v$$ 是 $$x$$ 軸，$$(\vec u\times \vec v)$$ 是 $$y$$ 軸。

Next, we have

$$
T_q(\vec v) = q\vec v \vec q = \cdots = T(\vec v).
$$

Replacing $$\vec v$$ by $$\vec u\times \vec v$$ leads to a similar result. ◼

#### Remark

比起用矩陣來表示旋轉，用四元數簡潔方便多了！

---

## Ring Homomoprhism

> See [rings and fields](../rings-and-fields#homomorphism).

### Theorem (factor rings)
> Let $$\phi:R\to R'$$ be a ring homomorphism with kernel $$K$$. Then **the additive cosets of $$H$$ form a ring $$R/K$$**, with addition and multiplication given by 
> 
> $$
> \begin{align*}
> +:(a+H, b+H) \mapsto (a+b)+H \\
> \times: (a+H, b+H) \mapsto (ab) + H.
> \end{align*}
> $$

**Proof**

We need to prove that 

1. addition: well-defined, and $$R/H$$ is an abelian group under addition
2. multiplication: well-defined and associatiive
3. distributive laws hold

#### Lemma (kernel element)
> The kernel $$H$$ above satisfies
>
> $$
> ah, hb \in H,
> $$
>
> for all $$a,b \in R$$ and $$h\in H$$.