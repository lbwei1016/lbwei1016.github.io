---
layout: page
title: Orthogonality
usemathjax: true
tag: Linear Algebra
---

## Prerequisites

### Inner Product

*Define:*
> Let $$\boldsymbol{v}, \boldsymbol{w} \in \mathbb{R}^n$$. The ***inner product*** of $$\boldsymbol{v}$$ and $$\boldsymbol{w}$$ is defined as: $$<\boldsymbol{v}, \boldsymbol{w}> = \boldsymbol{v}^T\boldsymbol{w} = \boldsymbol{w}^T \boldsymbol{v} = <\boldsymbol{w}, \boldsymbol{v}>$$  

### Norm

*Define:*
> The ***norm*** (length) of a vector $$\boldsymbol{v} \in R^n$$ is $$\|\boldsymbol{v}\| = \sqrt{\boldsymbol{v}^T\boldsymbol{v}}$$, $$\|\boldsymbol{v}\| = 0$$ if only if $$\boldsymbol{v} = \boldsymbol{0}$$.

---

## Orthogonal

*Define:*
> $$\boldsymbol{v}$$ and $$\boldsymbol{w}$$ are *orthiginal* if only if $$\|\boldsymbol{v} + \boldsymbol{w}\|^2 = \|\boldsymbol{v}\|^2 + \|\boldsymbol{w}\|^2$$, i.e. $$<\boldsymbol{v}, \boldsymbol{w}> = 0$$

## Orthogonal Subspaces

*Define:*
> Two subspaces $$V$$ and $$W$$ are within a vector space and *orthogoanl* if every $$\boldsymbol{v} \in V$$ is orthogonal to every $$\boldsymbol{w} \in W$$.

## Orthogonal Complement

*Define:*
> The *orthogonal complement* of a subspace $$V$$ contains every vector that is orthogonal every vector in $$V$$, which is denoted by $$V^\perp$$

### Theorem

**(i)**<br>
> $$V^\perp$$ is a subspace.

**(ii)**<br>
> $$V^\perp$$ is unique to $$V$$.

*Hint for Proof:*

($$V^\perp$$ contains ***every*** vector that is orthogonal to vectors in $$V$$.)

## Remark
> Orthogonality is impossible when $$dim(V_1) + dim(V_2) > dim(V)$$, where $$V_1$$ and $$V_2$$ are subspaces of vector space $$V$$.

*Proof:*

If $$dim(V_1) + dim(V_2) > dim(V)$$, there exists $$\boldsymbol{v} \in V_1, \boldsymbol{v} \neq \boldsymbol{0}$$ such that it is a linear combination of vectors of in $$V_2$$, i.e. $$\boldsymbol{v} \in V_2$$

$$\because$$ When a vector is in two orthogonal subspaces, it must be $$\boldsymbol{0}$$<br>
$$\therefore V_1 \not\perp V_2$$