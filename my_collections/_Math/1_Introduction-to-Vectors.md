---
layout: page
title: Introduction to Vectors
usemathjax: true
tag: Linear Algebra
---

> Definition: A *vector* is a collection of numbers in $$\mathbb{R}$$

## Operation

* vector addition
  * element-wise addition
* scalar multiplication

> A ***linear combination*** consists of the two operations above

## Axiom 

* Associativity of addition (結合)
* Commutativity of addition (交換)
* Distributivity of scalar multiplication (分配)
  1. with respect to *vector* addition
  2. with respect to *field (scalar)* addition
* Compatibility of scalar multiplication (結合)
  * with field multiplication: $$a(b\boldsymbol{v}) = (ab)\boldsymbol{v}$$
* Identity element of addition 
  * exists an element $$\boldsymbol{0}$$ (called *zero vector*) in **V** (vector space) such that $$\boldsymbol{v} + \boldsymbol{0} = \boldsymbol{v}$$, for all $$\boldsymbol{v}$$ in **V**
* Identity element of scalar multiplication: $$1 \times \boldsymbol{v} = \boldsymbol{v}$$
  * $$1$$ denotes the *multiplicative identity* in $$R$$
* Inverse elements of addition
  * $$-\boldsymbol{v}$$ is the *additive inverse* of $$\boldsymbol{v}$$ 
  
  > 另外有兩前提: (封閉性)
  >
  > 1. $$x+y\in V$$ whenever $$x, y \in V$$
  > 2. $$\alpha x\in V$$ whenever $$\alpha \in F$$ 