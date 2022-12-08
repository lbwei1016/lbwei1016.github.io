---
layout: page
title: Algebraic Closures
usemathjax: true
tag: Abstract Algebra, Field
time: 2022/12/09
---

**Table of Content**


---

## Theorem (still algebraic)
> Let $$E$$ be am extension field of a field $$F$$. If $$\alpha, \beta \not = 0 \in E$$ are **algebraic over** $$F$$, then **so are $$\alpha+\beta$$ and $$\alpha/\beta$$**.

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