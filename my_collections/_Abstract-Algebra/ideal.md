---
layout: page
title: Ideals
usemathjax: true
tag: Abstract Algebra, Ring
time: 2023/03/18
---

**Table of Content**

---

## Definition (ideal)
> An additive subgroup $$I$$ of a ring $$R$$ satisfiying $$aI\subset I, Ib\subset I$$ for all $$a,b\in R$$ is an **ideal** of $$R$$. Especially, $$I$$ is a **subring**.

> $$a$$ 和 $$b$$ 被 $$I$$ 吸收了！

### Proposition (kernel is an ideal)
> The kernel of a ring homomorphism is an ideal.

**Proof**

By this [lemma](../quaternion-and-ring-homomorphism/#lemma-kernel-element).

## Theorem (well-defined multi.)
> Let $$H$$ be a subring of a ring $$R$$. The map 
>
> $$
> \times:(a+H, b+H)\mapsto (ab)+H
> $$
>
> is a **well-defined** multiplication of **additive cosets** of $$H$$ **iff** $$H$$ is an ideal.

**Proof**

(待補)

### Corollary (additive coset; ring)
> Let $$I$$ be an ideal of a ring $$R$$. The **additive cosets** of $$I$$ form a ring $$R/I$$, with addition and multiplication given by 
>
> $$
> \begin{align*}
>  +:(a+I, b+I)\mapsto(a+b)+I, \\
> \times:(a+I,b+I)\mapsto(ab)+I.  
> \end{align*}
> $$

> $$R/I$$ 讀做 **the quotient ring (or factor ring) of $$R$$ by $$I$$**.

## Remark

對於 group 來說，任意 $$g\in G$$ 都能在 normal subgroup 左右移動；對於 ring 來說，任意 $$r\in R$$ 皆被 ideal 吸收。而且，group homomorphism 的 kernel 是 normal subgroup；ring homomorphism 的 kernel 正是 ideal！