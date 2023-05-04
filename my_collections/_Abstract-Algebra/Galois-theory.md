---
layout: page
title: Galois Theory
usemathjax: true
tag: Abstract Algebra, Galois Theory
time: 2023/04/28
---

**Table of Content**
- [Theorem (the fundamental theorem of Galois theory)](#theorem-the-fundamental-theorem-of-galois-theory)
  - [Theorem (more properties)](#theorem-more-properties)


---

研究 field、subfield 時，往往牽涉到[複雜的計算](../algebraic-extension/#exercise-1)；相對於 field theory 來說，群的問題相對比較容易解決（像是找 subgroup，或是確認群的性質）。Galois theory 正可以把 field theory 的問題轉換為 group theory 的問題！

## Theorem (the fundamental theorem of Galois theory)
> Let $$E/F$$ be a finite Galois extension with Galois group $$G$$ and $$\text{char}F=0$$. Let $$H$$ be a subgroup of $$G$$ and let $$K$$ be an intermediate field between $$E$$ and $$F$$. The following holds:
>
> 1. $$\vert H\vert = [E : E^H]$$.
> 2. $$\vert G_K\vert = [E:K]$$.
> 3. **$$K/F$$ is Galois iff $$G_K$$ is normal**. In this case, $$\text{Gal}(K/F) = G/G_K$$.
>
> Consequently, there is a **bijection** between subgroups pf $$G$$ and intermediate fields between $$E$$ and $$F$$.

Note that 

$$
\begin{align*}
E^H &= \{a\in E\mid h(a) = a,\forall h\in H \}, \\
G_K &= \{g\in G\mid g(a) = a,\forall a\in K \}.
\end{align*}
$$

> 固定 field 中的元素！一個收集 field element，另一個收集 group element。想想 [automorphism 的定義](../more-on-automorphism/#definition-automorphism-groups)，正是固定 $$F$$ 的 mapping！

### Theorem (more properties)
> Let $$E/F$$ be a finite Galois extension and $$K_1$$ and $$K_2$$ be intermediate fields. Let $$H_1=\text{Gal}(E/K_1) $$ and $$H_2=\text{Gal}(E/K_2)$$.
>
> 1. If $$K_1\cap K_2 = F$$, then $$G=\langle H_1, H_2\rangle$$.
> 2. If $$\langle K_1, K_2\rangle = E$$, then $$H_1\cap H_2 = \{e\}$$.
> 3. If the above two cases **both** hold and either $$K_1/F$$ or $$K_2/F$$ is Galois, then $$G=H_1H_2$$, and $$G$$ is isomorphic to a [semidirect product](../NH/#theorem-determine-structure-of-g) of $$H_1$$ and $$H_2$$.

> 如果 $$K_1/F$$ 是 Galois，$$H_1$$ 就是 $$G$$ 的 **normal subgroup**！