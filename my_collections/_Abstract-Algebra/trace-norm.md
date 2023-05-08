---
layout: page
title: Trace and Norm
usemathjax: true
tag: Abstract Algebra, Galois Theory
time: 2023/05/08
---

**Table of Content**



---

假設現在已經知道 Galois group $$G$$ 的某個 subgroup $$H$$，如何找出對應的 subfield $$E^H$$？法一：設 $$H=\langle a\rangle$$。根據定義，對於所有 $$x\in E^H$$，$$ax = x$$。由於 $$x$$ 也在 $$E$$ 中，我們可以將 $$x$$ 表示為 $$c_0 + c_1\alpha + \cdots$$ 的形式，再比較 $$ax$$ 和 $$x$$ 的各項係數就好！底下再提出另一種方法

## Definition (trace)
> Let $$E/F$$ be a field extension with Galois group $$G$$, and $$K$$ be an intermediate field. Define the **trace** of $$x\in E$$ on $$E/K$$:
>
> $$
> \text{tr}(x) = \sum_{h\in H}h(x),
> $$
>
> where $$H\le G$$.

### Properties (trace)
- $$\text{tr}: E\to E^H$$.
- $$\text{tr}$$ is a linear transformaition.
- $$\text{tr}$$ is surjective.

**Proof** (image is contained in $$E^H$$)

For all $$h'\in H$$, 

$$
\begin{align*}
h'(\text{tr}(x)) &= h'\big(\sum_{h\in H}h(x) \big) \\
&= \big(\sum_{h\in H}h'h(x) \big) \tag*{since $h'$ is an 
automorphism} \\
&= \sum_{h\in H}h(x) \tag*{left multiplication: permute} \\
&= \text{tr}(x). \tag*{$\blacksquare$}
\end{align*}
$$

> 左乘是個 bijective mapping！（試著證明）

### Example

Let $$\beta$$ be a basis of $$E$$ over $$F$$. Then $$E^H = \text{tr}(E)$$ is spanned by $$\text{tr}(\beta)$$.

> 然後再把 $$\beta$$ 中的元素代入 $$\text{tr}$$，解 $$E^H$$ 的 basis！

> 待補齊...


## Definition (norm)
> Define the norm of $$x\in E$$ on $$E/F$$:
>
> $$
> N_{E/F}(x) := \prod_{g\in G}g(x).
> $$

### Theorem (matrix represnetation)
> Let $$E/F$$ be a finite Galois extension with the Galois group $$G$$. For all $$\alpha\in E$$, we have $$N_{E/F}(\alpha) = \det(L_\alpha)$$ and $$\text{tr}_{E/F}(\alpha) = \text{tr}(L_\alpha)$$.

> [$$L_\alpha$$ 是左乘！](../matrix-rep-of-extension)

**Proof hint**

先明確寫出當 $$E = F(\alpha)$$ 的 trace 和 norm 看看。