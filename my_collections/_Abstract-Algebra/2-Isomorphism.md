---
layout: page
title: Isomorphism
usemathjax: true
tag: Abstract Algebra
time: 2022/09/19
---

**Table of Content**
- [Well-definedness](#well-definedness)
- [Isomorphism](#isomorphism)
  - [Example $$\rm I$$](#example-rm-i)
  - [Example $$\rm II$$](#example-rm-ii)
  - [Example $$\rm III$$](#example-rm-iii)
- [Something on Homomorphism](#something-on-homomorphism)
- [Morphisms and Closed Subset](#morphisms-and-closed-subset)
  - [Theorem](#theorem)

---

## Well-definedness

In general, when we define a function or an operator on
equivalence classes, if the expression of the function or the operator **depends on the representatives of equivalence classes**, then one have to show the result is indeed *independent* of the choice of representatives. This is so called the **well-definedness**.

> 和 representative 無關

**e.g.**

For $$\bar a, \bar b \in \mathbb{Z}_n$$, define 

$$\bar a + \bar b := \overline{a+b}.$$

It can be shown that $$+$$ is **well-defined**. (Let $$\bar c = \bar a$$ and $$\bar d = \bar b$$, and show $$\overline{c+d} = \overline{a+b}$$.)

---

## Isomorphism

The function $$\phi: S \to S'$$ is an isomorphism between $$(S, *)$$ and $$(S', *')$$ if

1. $$\phi$$ is **one-to-one**; (If $$\phi(x) = \phi(y)$$, then $$x = y$$.)
2. $$\phi$$ is **onto**; ($$\forall y \in S',\ \exists x \in S$$ such that $$\phi(x) = y$$.)
3. $$\phi$$ is **homomorphism**. ($$\phi(x*y) = \phi(x) *' \phi(y)$$)

若這樣的 $$\phi$$ 存在，則 $$(S, *) \cong (S', *')$$（或說 $$S \cong S'$$）。

> 讀：$$\phi$$ is an isomorphism.

> 見 [Linear Transformation](../../Linear-Algebra/5_Linear_transformation/#homo-isomorphism)

### Example $$\rm I$$

> Prove taht the binary structure $$(\mathbb{R}, +)$$ is isomorphic to $$(\mathbb{R}_{>0}, \dot{})$$.

**Proof**

We claim that $$\phi:\mathbb{R} \to \mathbb{R}_{>0}$$ defined by $$\phi(x) = e^x$$ satisfies 

1. one-to-one,
2. onto,
3. homomorphism.

**Proof of claim 1.**

For all $$x, y \in \mathbb{R}$$, if $$\phi(x) = \phi(y)$$, then $$e^x = e^y, \ln(e^x) = \ln(e^y)$$, and $$x = y$$.

**Proof of claim 2.**

For all $$y \in \mathbb{R}_{> 0}$$, let $$x = \ln y$$. Then $$\phi(x) = e^{\ln y} = y$$.

**Proof of claim 3.**

For all $$x, y \in \mathbb{R}$$, $$\phi(x+y) = e^{x+y} = e^x \dot{} e^y = \phi(x) \dot{} \phi(y)$$. ◼

### Example $$\rm II$$

> Determine whether binary structures $$(\mathbb{Z}, \dot{})$$ and $$(2\mathbb{Z}, \dot{})$$ are isomorphic.

**Intuition**

在 $$\mathbb{Z}$$ 中，有一單位元素 $$e=1$$ 使得 $$e \dot{}n = n,\ \forall n \in \mathbb{Z}$$；但 $$2\mathbb{Z}$$ 中並沒有相應的成員。所以嘗試證明 
**non-isomorphic**。

**Proof**

Suppose $$\rho: \mathbb{Z} \to \mathbb{2Z}$$ is an isomorphism, and $$\rho(1) = a$$.

$$a = \rho(1 \dot{} 1) = \rho(1) \dot{} \rho(1) = a^2, \tag{by homomorphism}$$

Hence, $$a = 0 \lor 1$$; however $$a = 1$$ is impossible since $$ 1 \not \in 2\mathbb{Z}$$. Therefore, $$a = 0$$.

Suppose $$\rho(2) = b \not = 0$$ (since one-to-one). We can show that

$$b = \rho(2 \dot{} 1) = \rho(2)\rho(1) = ba = 0,$$

which is a contradiction.

Therefore, such $$\rho$$ doesn't exists；the two structures aren't isomorphic. ◼

### Example $$\rm III$$

> Determine whether binary structures $$(\mathbb{R}, \dot{})$$ and $$(\mathbb{C}, \dot{})$$ are isomorphic.

**Intuition**

在 $$\mathbb{C}$$ 中，$$x \dot{} x = c$$ 對於所有 $$c \in \mathbb{C}$$ 都有解，但在 $$\mathbb{R}$$ 中則不然。所以嘗試證明 
**non-isomorphic**。

**Proof**

Suppose there exists an isomorphism $$\phi: \mathbb{C} \to \mathbb{R}$$, and $$\phi(a) = -1$$. We further let $$b^2 = a \in \mathbb{C}$$.

We can show that 

$$\phi(b \dot{} b) = \phi(b)\dot{}\phi(b) = \phi(b)^2 = -1,$$

and hence 

$$\phi(b) = i \not \in \mathbb{R},$$

which is a contradiction. ◼

---

## Something on Homomorphism

$$det: M_n(\mathbb{R}) \to \mathbb{R}$$ 

is **multiplication homomorphism**, since

$$det(AB) = det(A)det(B);$$

and

$$tr: M_n(\mathbb{R}) \to \mathbb{R}$$

is **addition homomorphism**, since

$$tr(A+B) = tr(A) + tr(B).$$

---

## Morphisms and Closed Subset
### Theorem

> Let $$\rho$$ be a **homomorphism** from a binary structure $$(S, *)$$ to
anther binary structure $$(S', *')$$. Let $$B$$ and $$B'$$ be subsets of $$S$$ and $$S'$$ respectively. Then

- If $$B$$ is closed under $$*$$, then $$\rho(B)$$ is closed under $$*'$$

- If $$B'$$ is closed under $$*'$$ then $$\rho^{-1}(B')$$ is closed under $$*$$.

> 但 $$\rho^{-1}$$ 要先存在。
