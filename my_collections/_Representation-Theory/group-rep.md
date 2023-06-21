---
layout: page
title: Group Represnetations
usemathjax: true
tag: Algebra, Represnetation Theory, Group theory
time: 2023/06/21
---

**Table of Contents**
- [Definition (group representation)](#definition-group-representation)
  - [Definition (equivalence of representations)](#definition-equivalence-of-representations)
  - [Example](#example)


---

## Definition (group representation)
> A **representation** of a group $$G$$ is a **homomorphism** $$\phi: G\to GL(V)$$, for some (finite-dimensional) non-zero vector space $$V$$. The **dimension** of $$V$$ is called the **degree** of $$\phi$$.
>
> Usually, $$\phi(g)$$ is denoted by $$\phi_g$$ for $$g\in G$$.

### Definition (equivalence of representations)
> Two representations $$\phi: G\to GL(V)$$ and $$\psi: G\to GL(W)$$ are **equivalent** if there exists an **isomorphism** $$T: V\to W$$ such that $$\psi_g = T\phi_g T^{-1}$$ for all $$g\in G$$. In this case, we write $$\phi \sim \psi$$.


### Example

Define $$\phi: \Bbb Z_n \to GL(\Bbb C^2)$$ by

$$
\phi(m) = \begin{pmatrix}
    e^{2\pi mi/n} & 0 \\
    0 & e^{-2\pi mi/n}
\end{pmatrix}.
$$

Also, define $$\psi: \Bbb Z_n \to GL(\Bbb C^2)$$ by

$$
\psi(m) = \begin{pmatrix}
    \cos(2\pi m/n) & -\sin(2\pi m/n) \\
    \sin(2\pi m/n) & \cos(2\pi m/n).
\end{pmatrix}
$$

We can show that $$\phi \sim \psi$$ with 

$$
T = \begin{pmatrix}
    i & -i \\
    1 & 1
\end{pmatrix}.
$$
