---
layout: page
title: More on Group Action
usemathjax: true
tag: Abstract Algebra, Group
time: 2023/02/17
---

**Table of Content**


---

## $$p$$-Groups
### Definition (fixed subset)
> Let $$X$$ be a $$G$$-set. For any element $$g\in G$$, we define
>
> $$
> X^g = \{x\in X \mid gx=x\},
> $$
>
> which is called the **$$g$$-fixed subset of $$X$$**. Additionally, we define 
>
> $$
> X^G = \bigcap_{g\in G}X^g,
> $$
>
> which is called the **$$G$$-fixed subset of $$X$$**. Note that **$$x\in X^G$$ iff $$G_x = \{x\}$$**.

> centralizer ?

#### Remark

> Note that **$$x\in X^G$$ iff $$G_x = \{x\}$$**.

為什麼？因為 $$X^G$$ 是 $$X^g$$ 的聯集，代表 $$X^G$$ 含有**對所有 $$g\in G$$，不受 $$g$$ 影響的 $$x$$**。

### Theorem (order modulo)
> Let $$p$$ be a **prime** and let $$G$$ be a finite **$$p$$-group** (i.e., the order of $$G$$ is a power of $$p$$) that acts on a finite set $$X$$. Then it holds that $$\vert X\vert \equiv \vert X^G\vert \pmod p $$, where $$X^G$$ is the fixed subset of $$X$$ under the action of $$G$$.

**Proof**

Let $$X_1,\cdots,X_k$$ be the collection of $$G$$-orbits that contain at least two elements. Then we have

$$
X = X^G
$$