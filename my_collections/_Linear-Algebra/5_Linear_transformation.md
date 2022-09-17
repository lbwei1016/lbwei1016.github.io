---
layout: page
title: Linear Transformation
usemathjax: true
tag: Linear Algebra, Linear Transformation
time: 2022/09/17
---

**Table of Content**
- [Definition](#definition)
- [The Matrix of a Linear Transformation](#the-matrix-of-a-linear-transformation)
  - [Theorem (The matrix of a linear trans.)](#theorem-the-matrix-of-a-linear-trans)
- [Find the Standard Matrix for $$T$$](#find-the-standard-matrix-for-t)
  - [Example $$\rm I$$](#example-rm-i)
- [Injection and Surjection](#injection-and-surjection)
  - [Injection](#injection)
  - [Surjection](#surjection)
- [{Homo, Iso}morphism](#homo-isomorphism)
  - [Homomorphism](#homomorphism)

---

## Definition

> A **linear transformation** is a transformation $$T: \mathbb{R}^n \to \mathbb{R}^m$$ satisfying
>
>$$\begin{eqnarray}
    T(\boldsymbol{u}+\boldsymbol{v}) &=& T(\boldsymbol{u}) + T(\boldsymbol{v}) \tag{1}　\\
    T(c\boldsymbol{u}) &=& cT(\boldsymbol{u}) \tag{2}
>\end{eqnarray}$$
>
> for all vectors $$\boldsymbol{u}, \boldsymbol{v} \in \mathbb{R}^n$$ and all scalars $$c$$.

$$T(0) = 0$$ 是 **linear transformation** 的結論，可以用來快速檢驗某 transformation 是否 linear。於是任何有**常數**的 transformation 都不 linear；如 $$T(x) = x + 1$$ is non-linear for $$T(0) \not = 0$$.

> 問題：找出符合 *property of linearity* $$(1)$$ 但不符合 $$(2)$$ 的 transformation。（目前無解）

---

## The Matrix of a Linear Transformation

### Theorem (The matrix of a linear trans.)

>Let $$T: \mathbb{R}^n \to \mathbb{R}^m$$ be a *linear transformation*. Let $$A$$ be the $$m \times n$$ matrix
> 
>$$A = \Big(T(\boldsymbol{e_1})\ T(\boldsymbol{e_2})\ \cdots\ T(\boldsymbol{e_n})\Big).$$
>
>（$$\boldsymbol{e_i}$$ 是單位向量（standard vector）；$$T(\boldsymbol{e_i})$$ 是 column vector）
> Then $$T$$ is the *matrix transformation* associated with $$A$$, i.e. $$T(\boldsymbol{x}) = A\boldsymbol{x}$$.

**Proof**

$$\begin{eqnarray}
T\begin{pmatrix}
    x \\ y \\ z
\end{pmatrix} &:=& T\Big(x\begin{pmatrix}1 \\ 0 \\ 0\end{pmatrix} + y\begin{pmatrix}0 \\ 1 \\ 0\end{pmatrix} + z\begin{pmatrix}0 \\ 0 \\ 1\end{pmatrix}\Big) \\
&=& xT(\boldsymbol{e_1}) + yT(\boldsymbol{e_2}) + zT(\boldsymbol{e_3}) \\
&=& \Big(T(\boldsymbol{e_1})\ T(\boldsymbol{e_2})\ \cdots\ T(\boldsymbol{e_n})\Big)\begin{pmatrix}x \\ y \\ z\end{pmatrix} \\
&=& A\begin{pmatrix}x \\ y \\ z\end{pmatrix} \tag*{$\blacksquare$}
\end{eqnarray}$$

此處 $$A$$ 稱作 the **standard matrix** for $$T$$。從本 theorem 也可以看出，*matrix transformation 和 linear transformation 是等價的*。

---

## Find the Standard Matrix for $$T$$

### Example $$\rm I$$

Define $$T:\mathbb{R}^2 \to \mathbb{R}^3$$ by the formula

$$T\begin{pmatrix}x \\ y\end{pmatrix} = \begin{pmatrix}3x-y \\ y \\ x\end{pmatrix}$$.

已知 $$A = \Big(T(\boldsymbol{e_1})\ T(\boldsymbol{e_2})\ \cdots\ T(\boldsymbol{e_n})\Big)$$，因此我們只需依序對 $$T$$ 帶入 $$\boldsymbol{e_1}, \boldsymbol{e_2}$$，就能求出相應的 matrix $$A$$：

$$T(\boldsymbol{e_1}) = \begin{pmatrix}3(1)-0 \\ 0 \\ 1\end{pmatrix}$$

$$T(\boldsymbol{e_2}) = \begin{pmatrix}3(0)-1 \\ 1 \\ 0\end{pmatrix}$$

所以 $$A = \begin{pmatrix}3 & -1 \\ 0 & 1 \\ 1 & 0\end{pmatrix}$$。

> [更多範例](https://textbooks.math.gatech.edu/ila/linear-transformations.html)

--- 

## Injection and Surjection

> 設 $$T: \mathbb{R}^n \to \mathbb{R}^m,\ T(x) = Ax,\ A \in \mathbb{R}^{m \times n}$$

### Injection

若 $$A$$ 符合以下等價條件：

- $$A$$ 是 *full column rank*，即 $$\dim(N(A)) = 0$$。
- $$\forall b \in \mathbb{R}^m$$，$$T(x) = \boldsymbol{b}$$ 只有**一個以下**的解。

則 $$T$$ is *injective*。 

進一步解釋：*Full column rank* 代表 $$A$$ 的 columns 是 linearly independent，所以 $$A\boldsymbol{x} = A\boldsymbol{y} \iff \boldsymbol{x} = \boldsymbol{y}$$；這就是 *one-to-one*。然後，**wide matrices** ($$m < n$$) 不可能造就 *one-to-one* transformation，也就是「大打到小」不可能 *one-to-one*。

### Surjection

若 $$A$$ 符合以下等價條件：

- range = codomain
- $$Ax = b$$ 必有解。
- $$A$$ 是 *full row rank*。

進一步解釋：**tall matrices** ($$m > n$$) 不可能造就 *onto* transformation，也就是「小打到大」不可能 *onto*。

> 若 $$A$$ 是 square ($$m = n$$)，則 $$T$$ is *one-to-one* **if only if** it is *onto*.

---

## {Homo, Iso}morphism

### Homomorphism

> "Homomorphism" comes from the greek homo (same) and morphus (form or shape).<br>
> So a "homomorphism" is a map that "preserves the shape" or **"preserves the structure."** --[StackExchange](https://math.stackexchange.com/questions/29944/difference-between-linear-map-and-homomorphism)（很棒的參考！）

*Linear transformation* 本身就 *preserve the vector space structure*（參照 [Vector Spaces and Subspaces](../4-1_Vector-Spaces-and-Subspaces) 和 linear trans. 的定義），所以 *homomorphisms of vector spaces* 和 *linear trans.* 其實意義相同！

> 更多 **homomorphism** 見 [StackExchange](https://math.stackexchange.com/questions/29944/difference-between-linear-map-and-homomorphism)



<br><br>

令 $$S_n = C_1 \cup \cdots \cup C_n$$。

原本的 axiom:

$$\lim_{n \to \infty}P(S_n) = \lim_{n \to \infty}\sum^n_{k=1}P(C_k) \tag{1}$$

強化版 axiom:

$$P(\lim_{n \to \infty}S_n) = \lim_{n \to \infty}\sum^n_{k=1}P(C_k) \tag{2}$$

我對 $$(1)$$ 的解讀是，把 $$P(C_k)$$ 看作集合的函數，所以左式是對「函數」取極限；而 $$(2)$$ 的左式則是對「集合的聯集」取極限。除非 $$P(C_k)$$ 是連續函數，否則 $$\lim$$ 沒辦法任意移動，兩者也就不一定相等。