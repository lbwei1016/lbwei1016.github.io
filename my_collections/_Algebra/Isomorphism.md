---
layout: page
title: Isomorphism
usemathjax: true
tag: Algebra
time: 2022/09/19
---

**Table of Content**

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

> 讀：$$\phi$$ is a isomorphism.

> 見 [Linear Transformation](../../Linear-Algebra/5_Linear_transformation/#homo-isomorphism)
