---
layout: page
title: Homomorphism
usemathjax: true
tag: Abstract Algebra, Group Theory
time: 2022/10/20
---

**Table of Content**


---

## Properties

Let $$\phi$$ be a homomorphism of a group $$G$$ into a group $$G'$$.

- $$\phi(e) = e'$$.
- $$\phi(a^{-1})=\phi{(a)}^{-1} \text{ for all } a \in G$$.
- If $$H$$ is a subgroup of $$G$$, then $$phi(H)$$ is a subgroup of $$G'$$.

> $$\phi(H)$$ is the **image** of $$H$$.

- If $$H'$$ is a subgroup of $$G'$$, then $$phi^{-1}(H')$$ is a subgroup of $$G$$.

> $$\phi^{-1}(H)$$ is the **preimage** of $$H'$$.

> 請嘗試證明，尤其是 subgroup 的部分。

### Corollary (injective homomorphism)
> Let $$\phi: G\to G'$$ be a group homomorphism. If $$phi$$ is **one-to-one** then $$G$$ and $$\phi(G)$$ are **isomorphic**. 

> 顯然 $$\phi: G \to \phi(G) $$ 已經 onto。

---

## Kernel
### Definition
> The *subgroup* $$\phi^{-1}(\{e'\}) $$ is called the **kernel** of $$\phi$$, denoted by **$$\text{ker}(\phi)$$**.

也就是說，對於任意在 domain $$X$$ 的 $$x$$，只要 $$\phi(x) = e'$$，那麼 $$x$$ 就在 $$\text{ker}(\phi)$$ 中！

**Example**

