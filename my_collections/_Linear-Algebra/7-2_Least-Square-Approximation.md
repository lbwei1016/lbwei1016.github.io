---
layout: page
title: Least Square Approximation
usemathjax: true
tag: Linear Algebra
---
In many cases, $$A\boldsymbol{x}=\boldsymbol{b}$$ has no solution; hence we need some approximation.

*Define:*

> Let $$\boldsymbol{e} = A\boldsymbol{x}-\boldsymbol{b}$$. The best approximation is the minimized $$\boldsymbol{e}$$, i.e. $$\|\boldsymbol{e}\|^2$$ is minimized.

## Theorem (orthogonality principle)

> Let $$\boldsymbol{e}$$ be defined as above, and it is minimized if $$\boldsymbol{x = \hat{x}}$$, where $$A\hat{\boldsymbol{x}} = \boldsymbol{p}$$. 

> $$\|\boldsymbol{e}\|^2 = \|A\hat{\boldsymbol{x}} - \boldsymbol{b}\|^2 \geq \|\boldsymbol{e_{rr}}\|^2$$

*Proof:*

As previously defined in [Projection](../7_Projection/), we know that the *error vector* $$\boldsymbol{e_{rr}} = \boldsymbol{b} - \boldsymbol{p}$$. So we now have $$\boldsymbol{b} = \boldsymbol{p + e_{rr}}$$ and 

$$\|A\boldsymbol{x}-\boldsymbol{b}\|^2 = \|A\boldsymbol{x} - \boldsymbol{p} - \boldsymbol{e_{rr}}\|^2 = (A\boldsymbol{x} - \boldsymbol{p} - \boldsymbol{e_{rr}})^T(A\boldsymbol{x} - \boldsymbol{p} - \boldsymbol{e_{rr}})$$

, which is equal to

$$\|A\boldsymbol{x}-\boldsymbol{p}\|^2 + \|\boldsymbol{e_{rr}}\|^2 - 2\boldsymbol{e_{rr}}^T(A\boldsymbol{x}-\boldsymbol{p})$$

Since $$\boldsymbol{e_{rr}}$$ is orthogonal to $$C(A)$$, we have

$$\boldsymbol{e_{rr}}^T(A\boldsymbol{x}-\boldsymbol{p}) = 0$$

This leads to the final equations:

$$\|A\boldsymbol{x}-\boldsymbol{b}\|^2 = \|A\boldsymbol{x}-\boldsymbol{p}\|^2 + \|\boldsymbol{e_{rr}}\|^2 \geq \|\boldsymbol{e_{rr}}\|^2$$

The rightmost equation is valid only if $$A\boldsymbol{x} = \boldsymbol{p}$$. That is, when $$\boldsymbol{x} = \hat{\boldsymbol{x}}$$.

Here we get the minimized $$\boldsymbol{e}$$:

$$\|\boldsymbol{e}\|^2 = \|A\boldsymbol{x}-\boldsymbol{b}\|^2 \geq \|A\hat{\boldsymbol{x}}-\boldsymbol{b}\|^2 = \|\boldsymbol{e_{rr}}\|^2$$ 

◼