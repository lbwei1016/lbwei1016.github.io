---
layout: page
title: Galois Field
usemathjax: true
tag: Abstract Algebra, Field
time: 2022/12/14
---

**Table of Content**
- [Theorem (subfield)](#theorem-subfield)
  - [Corollary (product of irr. poly.)](#corollary-product-of-irr-poly)
  - [Remark](#remark)
- [Summary](#summary)

---

## Theorem (subfield)
> In $$\overline{\Bbb Z}_p$$, $$\Bbb{F}_{p^m}$$ is contained in $$\Bbb{F}_{p^n}$$ iff $$m\mid n$$.

**Proof**

Suppose $$\Bbb{F}_{p^m} \le \Bbb{F}_{p^n}$$. Then

$$
n = [\Bbb{F}_{p^n}:\Bbb{Z}_p]=[\Bbb{F}_{p^n}:\Bbb{F}_{p^m}][\Bbb{F}_{p^m}:\Bbb{Z}_p] = m[\Bbb{F}_{p^n}:\Bbb{F}_{p^m}].
$$

Thus $$m\mid n$$.

Conversely, assume that $$m \mid n$$. It suffice to prove that if $$\alpha\in \overline{\Bbb Z}_p $$ is a zero of $$x^{p^m}-x$$, then it is also a zero of $$x^{p^n}-x$$.

For all $$\alpha\in \Bbb{F}_{p^m}$$, we have $$\alpha^{p^m} = \alpha$$. Then

$$
\alpha^{p^n} = (\alpha^{p^m})^{p^{n-m}} = \alpha^{p^{n-m}} = \cdots.
$$

Since $$m\mid n$$, we eventually arrive at $$\alpha^{p^n}=\alpha$$. ◼

### Corollary (product of irr. poly.)
> The polynomial $$x^{p^n}-x$$ is equal to the **product of all monic irreducible polynomial** over $$\Bbb{Z}_p$$ with degree **$$d$$ dividing $$n$$**.

**Proof**

Let $$f(x)$$ be a monic irreducible polynomial of degree $$d$$ over $$\Bbb{Z}_p$$, with $$d\mid n$$ and $$\beta$$ be its zero in $$\overline{Z}_p$$. Since $$d\mid n$$, we have

$$
\Bbb{Z}_p(\beta) = \Bbb{F}_{p^d} \le \Bbb{F}_{p^n}.
$$

Therefore, $$\beta$$ is a zero of $$x^{p^n}-x$$, which implies that $$f(x)\mid x^{p^n}-x$$. 

Conversely, let $$f(x)$$ be a monic irreducible factor of $$x^{p^n}-x$$ of degree $$d$$, with a zero $$\beta$$ in $$\overline{\Bbb Z}_p$$. Since $$\beta$$ is also a zero of $$x^{p^n}-x$$, we have $$\beta \in \Bbb{F}_{p^n}$$. Thus, 

$$
\Bbb{F}_{p^d} = \Bbb{Z}_p(\beta) \le \Bbb{F}_{p^n},
$$

and then we conclude that $$d\mid n$$. ◼

> 先證所有 $$d\mid n$$ 都是 factor，再證所有 factor 都 $$d\mid n$$！

### Remark

在[這裡](../P-field-extension/#remark-2)，我們說明了對於 field extension，加入 generator 是比較好的。但是如何找到 a zero $$\alpha$$ of an irreducible polynomial $$f(x)$$，使得 $$\alpha$$ 是 generator？

如果 $$\alpha$$ 是 generator，則 $$\alpha$$ 的 order 必須是 $$p^n-1$$，等同於，$$\alpha$$ 是 $$\Phi_{p^n-1}(x)$$ 的 zero 之一；也就是說，$$f(x)$$ 必須是 $$\Phi_{p^n-1}(x)$$ 的不可約因式之一。例如：

Let $$\alpha$$ be a zero of $$x^2+1$$ over $$\Bbb Z_3[x]$$ in $$\overline{\Bbb Z_3}$$. We can see that $$\vert \Bbb Z_3(\alpha)^\times\vert = 3^2-1 = 8$$, and 

$$
\Phi_8(x) = {x^8-1\over (x-1)(x+1)(x^2+1)} = x^4 + 1.
$$ 

Let's guess that $$\alpha+1$$ is a generator, so that $$(\alpha+1)^4 + 1$$ must equal to zero. To verify it, 

$$
\begin{align*}
(\alpha+1)^4 + 1 &= \alpha^4 + 4\alpha^3 + 6\alpha^2 + 4\alpha + 1 + 1 \\
&= \alpha^2(\alpha^2+1) + 5\alpha^2 + 4\alpha(\alpha^2+1) + 2 \\
&= 2\alpha^2 + 2 = 0.
\end{align*}
$$

Indeed, $$\alpha+1$$ is a generator of $$\Bbb Z_3(\alpha)^\times$$. However, should we always make a guess, or is there a better way that leads to an answer? Can we [**factorize** cyclotomic polynomials over finite fields](../T-finite-field/#question)?

---

## Summary


