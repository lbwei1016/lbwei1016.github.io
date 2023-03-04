---
layout: page
title: Sylow Theorem
usemathjax: true
tag: Abstract Algebra, Sylow Theorem
time: 2023/03/02
---

**Table of Content**
- [**Theorem (Sylow theorems)**](#theorem-sylow-theorems)
  - [Corollary (contain; normal)](#corollary-contain-normal)

---

Sylow theorems can be used to find normal subgroups, and in turn [determine group structures](../Y-NH/#theorem-determine-structure-of-g)!

## **Theorem (Sylow theorems)**
> Suppose $$\vert G\vert=p^nm$$ where $$p$$ is a prime with $$p\not \mid m$$.
>
> 1. There exists a subgroup of order $$p^i$$ for $$1<i\leq n$$. Moreover, **every subgroup of order $$p^i$$ is normal in some subgroup of order $$p^{i+1}$$** when $$i<n$$.
> 2. Any two **Sylow $$p$$-subgroups** are **conjugated**.
> 3. Let **$$n_p$$** be the number of **Sylow p-subgroups**. Then $$n_p$$ satisfies the following **two conditions**:
>
> $$
> \begin{align*}
> &n_p \equiv 1 \pmod p, \tag{1}  \\
> &n_p \mid m. \tag{2}
> \end{align*}
> $$

> The subgroup $$H$$ of order $$p^n$$ is called a **Sylow $$p$$-subgroup**, which is exactly a maximal $$p$$-subgroup.

### Corollary (contain; normal)
> 1. Every $$p$$-subgroup is contained in a Sylow $$p$$-subgroup.
> 2. **A Sylow $$p$$-subgroup is normal iff $$n_p = 1$$.**