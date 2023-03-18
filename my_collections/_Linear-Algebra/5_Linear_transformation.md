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
  - [Example $$\\rm I$$](#example-rm-i)
- [Injection and Surjection](#injection-and-surjection)
  - [Injection](#injection)
  - [Surjection](#surjection)
- [{Homo, Iso}morphism](#homo-isomorphism)
  - [Homomorphism](#homomorphism)
  - [Isomorphism](#isomorphism)
- [See also](#see-also)
- [Reference](#reference)

---

## Definition

> A **linear transformation** is a transformation $$T: \mathbb{R}^n \to \mathbb{R}^m$$ satisfying
>
>$$\begin{eqnarray}
    T(\vec{u}+\vec{v}) &=& T(\vec{u}) + T(\vec{v}) \tag{1}　\\
    T(c\vec{u}) &=& cT(\vec{u}) \tag{2}
>\end{eqnarray}$$
>
> for all vectors $$\vec{u}, \vec{v} \in \mathbb{R}^n$$ and all scalars $$c$$.

$$T(0) = 0$$ 是 **linear transformation** 的結論，可以用來快速檢驗某 transformation 是否 linear。於是任何有**常數**的 transformation 都不 linear；如 $$T(x) = x + 1$$ is non-linear for $$T(0) \not = 0$$.

> 加上平移叫做 **affine**。

> 問題：找出符合 *property of linearity* $$(1)$$ 但不符合 $$(2)$$ 的 transformation。（目前無解）

---

## The Matrix of a Linear Transformation

### Theorem (The matrix of a linear trans.)

>Let $$T: \mathbb{R}^n \to \mathbb{R}^m$$ be a *linear transformation*. Let $$A$$ be the $$m \times n$$ matrix
> 
>$$A = \Big(T(\vec{e_1})\ T(\vec{e_2})\ \cdots\ T(\vec{e_n})\Big).$$
>
>（$$\vec{e_i}$$ 是單位向量（standard vector）；$$T(\vec{e_i})$$ 是 column vector）
> Then $$T$$ is the *matrix transformation* associated with $$A$$, i.e. $$T(\vec{x}) = A\vec{x}$$.

**Proof**

$$\begin{eqnarray}
T\begin{pmatrix}
    x \\ y \\ z
\end{pmatrix} &:=& T\Big(x\begin{pmatrix}1 \\ 0 \\ 0\end{pmatrix} + y\begin{pmatrix}0 \\ 1 \\ 0\end{pmatrix} + z\begin{pmatrix}0 \\ 0 \\ 1\end{pmatrix}\Big) \\
&=& xT(\vec{e_1}) + yT(\vec{e_2}) + zT(\vec{e_3}) \\
&=& \Big(T(\vec{e_1})\ T(\vec{e_2})\ \cdots\ T(\vec{e_n})\Big)\begin{pmatrix}x \\ y \\ z\end{pmatrix} \\
&=& A\begin{pmatrix}x \\ y \\ z\end{pmatrix} \tag*{$\blacksquare$}
\end{eqnarray}$$

此處 $$A$$ 稱作 the **standard matrix** for $$T$$。從本 theorem 也可以看出，*matrix transformation 和 linear transformation 是等價的*。

> 見 [Rings and Fields](../../Abstract-Algebra/J-rings-and-fields/#example-rm-ii-1)。

---

## Find the Standard Matrix for $$T$$

### Example $$\rm I$$

Define $$T:\mathbb{R}^2 \to \mathbb{R}^3$$ by the formula

$$T\begin{pmatrix}x \\ y\end{pmatrix} = \begin{pmatrix}3x-y \\ y \\ x\end{pmatrix}$$.

已知 $$A = \Big(T(\vec{e_1})\ T(\vec{e_2})\ \cdots\ T(\vec{e_n})\Big)$$，因此我們只需依序對 $$T$$ 帶入 $$\vec{e_1}, \vec{e_2}$$，就能求出相應的 matrix $$A$$：

$$T(\vec{e_1}) = \begin{pmatrix}3(1)-0 \\ 0 \\ 1\end{pmatrix}$$

$$T(\vec{e_2}) = \begin{pmatrix}3(0)-1 \\ 1 \\ 0\end{pmatrix}$$

所以 $$A = \begin{pmatrix}3 & -1 \\ 0 & 1 \\ 1 & 0\end{pmatrix}$$。

> [更多範例](https://textbooks.math.gatech.edu/ila/linear-transformations.html)。

--- 

## Injection and Surjection

> 設 $$T: \mathbb{R}^n \to \mathbb{R}^m,\ T(x) = Ax,\ A \in \mathbb{R}^{m \times n}$$

### Injection

若 $$A$$ 符合以下等價條件：

- $$A$$ 是 *full column rank*，即 $$\dim(N(A)) = 0$$。
- $$\forall b \in \mathbb{R}^m$$，$$T(x) = \vec{b}$$ 只有**一個以下**的解。

則 $$T$$ is *injective*。 

> $$\text{dim(N(A))} = 0$$ 相當於 $$\text{ker}(T) = \{I\}$$。

進一步解釋：*Full column rank* 代表 $$A$$ 的 columns 是 linearly independent，所以 $$A\vec{x} = A\vec{y} \iff \vec{x} = \vec{y}$$；這就是 *one-to-one*。然後，**wide matrices** ($$m < n$$) 不可能造就 *one-to-one* transformation，也就是「大打到小」不可能 *one-to-one*。

### Surjection

若 $$A$$ 符合以下等價條件：

- range = codomain
- $$Ax = b$$ 必有解。
- $$A$$ 是 *full row rank*。

進一步解釋：**tall matrices** ($$m > n$$) 不可能造就 *onto* transformation，也就是「小打到大」不可能 *onto*。

> 若 $$A$$ 是 square ($$m = n$$)，則 $$T$$ is *one-to-one* **if only if** it is *onto*.

---

## {Homo, Iso}morphism

> 見 [Homomorphism & Normal Subgroups](../../Abstract-Algebra/H-homomorphism-and-normal-groups)。

### Homomorphism

> "Homomorphism" comes from the greek homo (same) and morphus (form or shape).<br>
> So a "homomorphism" is a map that "preserves the shape" or **"preserves the structure."** --[StackExchange](https://math.stackexchange.com/questions/29944/difference-between-linear-map-and-homomorphism)（很棒的參考！）

*Linear transformation* 本身就 *preserve the vector space structure*（參照 [Vector Spaces and Subspaces](../4-1_Vector-Spaces-and-Subspaces) 和 [linear trans. 的定義](#definition)）；*homomorphisms of vector spaces* 和 *linear trans.* 其實意義相同！

> 更多 **homomorphism** 見 [StackExchange](https://math.stackexchange.com/questions/29944/difference-between-linear-map-and-homomorphism)。

### Isomorphism

> The word *isomorphism* derives from the Greek iso, meaning "equal," and morphosis, meaning "to form" or "to shape."

> The term isomorphism is mainly used for *algebraic structures*. In this case, mappings are called homomorphisms, and **a homomorphism is an isomorphism if and only if it is bijective**. --[Wiki](https://en.wikipedia.org/wiki/Isomorphism)

也就是說，Two algebraic structures are **isomorphic** if there exist:

1. a **bijective function**
2. **homomorphism**

between them.

因為是 *bijective*，所以存在 **inverse mapping** between two structures，這正是 *isomorphism* 和 *homomorphism* 的不同之處。

> 再次注意：*homomorphism* 是 *isomorphism* 的必要條件

就線性代數而言：
> A linear map $$T$$ is called an **isomorphism** if $$T$$ is **bijective**. 
 
為什麼這裡沒看到 **homomorphism**？因為[這裡](#homomorphism)已經說明，linear map 本身就是 **homomorphism**！

> 見 [Isomorphism](../../Algebra/Isomorphism)。

---

## See also
- [Change of basis](https://hackmd.io/@William1016/HJ1vC47e2)

## Reference
- [StackExchange](https://math.stackexchange.com/questions/29944/
difference-between-linear-map-and-homomorphism)
- [Interactive Linear Algebra -- one-to-one and onto](https://textbooks.math.gatech.edu/ila/one-to-one-onto.html)
- [Interactive Linear Algebra -- linear transformation](https://textbooks.math.gatech.edu/ila/linear-transformations.html)
- [LibreTexts](https://math.libretexts.org/Bookshelves/Linear_Algebra/A_First_Course_in_Linear_Algebra_(Kuttler)/05%3A_Linear_Transformations/5.06%3A_Isomorphisms)
- [Wolfram MathWorld](https://mathworld.wolfram.com/Isomorphism.html)
- [Wiki](https://en.wikipedia.org/wiki/Isomorphism)