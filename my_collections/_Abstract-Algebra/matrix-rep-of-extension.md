---
layout: page
title: Matrix Representation of Field Extensions
usemathjax: true
tag: Abstract Algebra, Field, Linear Algebra
time: 2022/12/05
---

**Table of Content**
- [Theorem (injective ring homomorphism)](#theorem-injective-ring-homomorphism)
  - [Proof](#proof)
  - [Corollary (isomorphic; subring)](#corollary-isomorphic-subring)
  - [Conversion between polynomial and matrix](#conversion-between-polynomial-and-matrix)
  - [Remark](#remark)
- [Reference](#reference)

---

Let $$E$$ be a field extension over $$F$$ of degree $$n$$. Let 

$$
\mathcal{L}(E/F) = \{T:E\to E\mid T \text{ is a } F \text{-linear transformation} \},
$$

which is a ring. Especially, if $$\alpha$$ is a basis of $$E$$, then $$T\to [T]_\alpha$$ defines a **ring isomorphism** from $$\mathcal{L}(E/F)$$ to $$M_n(F)$$.

For all $$a \in E$$, define

$$
L_a(x) = ax,
$$

which is an element of $$\mathcal{L}(E/F)$$.

> **$$F$$-linear** means that it is a linear transformation over $$E$$ where we view [$$E$$ as a vector space over $$F$$](../algebraic-extension/#lemma-extension-field-is-a-vector-space).

> 換句話說，不用理他。

## Theorem (injective ring homomorphism)
> The map $$\rho: E\to \mathcal{L}(E/F)$$ defined by $$\rho(a) = [L_a]_\alpha$$ is an **injective ring homomorphism** from $$E$$ to $$M_n(F)$$.

### Proof

**homomorphism**

$$
L_{a+b}(x) = (a+b)x = ax + bx = L_a(x) + L_b(x), \\
L_{ab}(x) = (ab)x = a(bx) = L_a(L_b(x)) = L_aL_b(x). 
$$

**one-to-one**

For all $$a\in \text{ker}(\rho)$$, 

$$
\rho(a) = 0 = L_a(x) = ax, \forall x \in E.
$$

which implies that $$a=0$$ and $$\rho$$ is injective. ◼

> $$E$$ is a field and has no zero divisors!


### Corollary (isomorphic; subring)
> **Every** field extension $$E$$ over $$F$$ of degree $$n$$ is isomorphic to some **subring** of $$M_n(F)$$.

> 於是所有 field extension 的計算可以用矩陣完成！

### Conversion between polynomial and matrix

Let $$\alpha$$ be a zero of $$x^3+x+1$$. Find $$(\alpha^2-\alpha+1)^{-1}$$.

**Solution**

Let $$\beta = \{1, \alpha, \alpha^2\}$$, we have

$$
\begin{align*}
[L_1]_\beta &= \begin{pmatrix}
  1&0&0 \\ 0&1&0 \\ 0&0&1
\end{pmatrix} \\
[L_\alpha]_\beta &= \begin{pmatrix}
  0&0&-1 \\ 1&0&-1 \\ 0&1&0  
\end{pmatrix} \\
[L_{\alpha^2}]_\beta &= \begin{pmatrix}
  0&-1&0 \\ 0&-1&-1 \\ 1&0&-1
\end{pmatrix}
\end{align*}
$$

and then

$$
[L_{\alpha^2-\alpha+1}]_\beta^{-1} = 
\big([L_{\alpha^2}]_\beta-[L_\alpha]_\beta+[L_1]_\beta \big)^{-1} = \begin{pmatrix}
  1&-1&1 \\ -1&0&0 \\ 1&-1&0
\end{pmatrix}^{-1} = \begin{pmatrix}
  0& \\ 0&\cdots \\ 1&
\end{pmatrix}.
$$

Since $$(\alpha^2-\alpha+1)^{-1}$$ is be a linear combination of the vectors in $$\beta$$, $$[L_{\alpha^2-\alpha+1}]_\beta^{-1}$$ must be a linear combination of $$[L_{\alpha^i}]_\beta$$ as well. Thus, from the first column of $$[L_{\alpha^2-\alpha+1}]_\beta^{-1}$$, which is $$(0, 0, 1)^T$$, we can easily identify that $$[L_{\alpha^2-\alpha+1}]_\beta^{-1} = [L_{\alpha^2}]_\beta$$. That is to say,

$$
(\alpha^2-\alpha+1)^{-1} = \alpha^2. ◼
$$

### Remark

首先，$$[L_{\alpha^i}]_\beta$$ 是怎麼算出來的？$$[L_1]_\beta$$ 就只是 $$n\times n$$ 單位矩陣。重點來了：因為我們定義 $$L_a(x) = ax$$，所以 $$L_\alpha(x) = \alpha x$$；也就是說，$$[L_{\alpha^{i+1}}]_\beta$$ 就僅僅是**將 $$[L_{\alpha^i}]_\beta$$ 中所有 column 往左移一單位，並在最右的空缺填上經由 $$\text{Irr}(\alpha, F)$$ 算出的係數**！

> $$[L_{\alpha^i}]_\beta$$ 的第一 column 對應 $$1\in \beta$$、第二 column 對應 $$\alpha\in \beta$$、第三對應 $$\alpha^2 \in \beta$$。

以 $$[L_\alpha]_\beta$$ 為例：前兩 column 可以輕鬆得出（$$L_\alpha(1) = \alpha, L_\alpha(\alpha) = \alpha^2$$），而最後一 column 則是，

$$
L_\alpha(\alpha^2) = \alpha^3 = -1-\alpha = (-1, -1, 0)^T，
$$

並且

$$
L_{\alpha^2}(\alpha) = L_\alpha(\alpha^2), \\
L_{\alpha^2}(\alpha^2) = \alpha^4 = \alpha(-1-\alpha) = (0, -1, -1)^T。
$$

利用上述這些等式，就能看出第一段所說的性質為何成立了！


此外，計算反矩陣時，利用 **Cramer's Rule**，**算第一 column 就夠了**，因為 $$n$$ 個矩陣的第一 column 組合起來正是單位矩陣。

**Note**

上述方法只適用於 *simple extension*，也就是當 basis 為 cyclic 的時候。如果是 $$\Bbb{Q}(\sqrt{2}, \sqrt{3})$$、 basis 為 $$\beta = \{1, \sqrt{2}, \sqrt{3}, \sqrt{6} \}$$，我們就只能一個一個算出 $$[L_1]_\beta, [L_\sqrt{2}]_\beta\cdots $$ 了！例如 

$$
[L_\sqrt{2}]_\beta = \begin{pmatrix}
  0 & 2 & 0 & 0 \\
  1 & 0 & 0 & 0 \\
  0 & 0 & 0 & 2 \\
  0 & 0 & 1 & 0
\end{pmatrix},
$$

因為左乘 $$\sqrt{2}$$ 後，

$$
\begin{align*}
  1 &\to \sqrt{2} \\
  \sqrt{2} &\to 2 \\
  \sqrt{3} &\to \sqrt{6} \\
  \sqrt{6} &\to 2\sqrt{3}.
\end{align*}
$$



---

## Reference

- [Set of all linear transformations](https://proofwiki.org/wiki/Definition:Set_of_All_Linear_Transformations)
- [Math StackExchange](https://math.stackexchange.com/a/106094)
