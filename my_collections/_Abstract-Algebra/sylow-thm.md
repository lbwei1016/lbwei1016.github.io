---
layout: page
title: Sylow Theorem
usemathjax: true
tag: Abstract Algebra, Sylow Theorem
time: 2023/03/02
---

**Table of Content**
- [The first Sylow theorem](#the-first-sylow-theorem)
  - [Corollary ($$p$$-subgroup contained)](#corollary-p-subgroup-contained)
  - [Corollary (subgroup order)](#corollary-subgroup-order)
- [The Second Sylow Theorem](#the-second-sylow-theorem)
- [The Third Sylow Theorem](#the-third-sylow-theorem)
  - [Corollary (normal)](#corollary-normal)
- [Applications](#applications)
  - [Simple groups](#simple-groups)
    - [Theorem ($$p$$-group + non-abelian)](#theorem-p-group--non-abelian)
    - [Lemma (injective homomorphism)](#lemma-injective-homomorphism)
    - [Theorem (orders)](#theorem-orders)

---

Sylow theorems can be used to find normal subgroups, and in turn [determine group structures](../NH/#theorem-determine-structure-of-g)!

Let $$G$$ be a group of order $$p^nm$$, where $$p$$ does not divide $$m$$.

## The first Sylow theorem
> There exists a subgroup of order $$p^i$$ for $$1<i\leq n$$. Moreover, **every subgroup of order $$p^i$$ is normal in some subgroup of order $$p^{i+1}$$** when $$i<n$$.

**Proof**

To prove this, we construct a series of $$p$$-subgroups $$H_1 < H_2 < \cdots < H_n$$, with $$\vert H_i\vert = p^i$$ and $$H_i \trianglelefteq H_{i+1}$$ for $$i<n$$, **by induction**.

By Cauchy's theorem, $$G$$ has a subgroup $$H_1$$ of order $$p$$. Suppose that for some $$i<n$$, $$H_i$$ has been constructed. We then wish to construct $$H_{i+1}$$. 

Since $$i<n$$, we have $$p\mid [G:H_i]$$. By [this lemma](../normalizer/#lemma-index-congruent):

$$
[N_G(H_i):H_i ] \equiv [G:H_i] \equiv 0\pmod p,
$$

which means that $$p$$ divides the order of $$N_G(H_i)/H_i$$. By Cauchy's theorem, **there is a subgroup $$K$$ of $$N_G(H_i)/H_i$$ of order $$p$$**.

Now consider the canonical homomorphism $$\phi: N_G(H_i)\to N_G(H_i)/H_i$$ defined by $$\phi(g) = gH_i$$. We can verify that $$\text{ker}(\phi) = H_i$$. Suppose that $$K = \{H_i, g_1H_i,\cdots,g_{p-1}H_i \}$$. We can find a subgroup $$R$$ containing $$H_i$$ such that $$R=\phi^{-1}(K)$$. **In particular, $$R = \{e, g_1,\cdots, g_{p-1} \}H_i$$**. Thus we have $$\vert R\vert = p^{i+1}.$$

Moreover, $$H_i$$ is normal in $$N_G(H_i)$$ by [definition](../normalizer/#definition-normalizer), and thus $$H_i$$ is also normal in $$R$$. The desired $$H_{i+1}$$ is exactly $$R$$. ◼

> $$R = \{e, g_1,\cdots, g_{p-1} \}H_i$$，這是兩個 set 乘在一起，像 [$$NH$$](../NH) 一樣！

### Corollary ($$p$$-subgroup contained)
> Every $$p$$-subgroup is contained in a Sylow $$p$$-subgroup.

### Corollary (subgroup order)
> If $$G$$ is a $$p$$-group, then $$G$$ admits a subgroup of any order $$d$$ that divides $$\vert G\vert$$.

> 看看[這](../more-group-action/#remark-1) ！

---

## The Second Sylow Theorem
> Any two **Sylow $$p$$-subgroups** of a finite group $$G$$ are **conjugate** to each other.

**Proof**

Let $$P_1$$ and $$P_2$$ be two Sylow $$p$$-subgroups of $$G$$. Let $$X$$ be the set of **all left cosets of $$P_1$$** in $$G$$, and let **$$P_2$$ act on $$X$$** by left multiplication. Since $$P_2$$ is a $$p$$-group, we have $$\vert X\vert\equiv \vert X^{P_2}\vert\pmod p$$. On the other hand, $$\vert X \vert = [G:P_1] = m$$ is not divisible by $$p$$, so $$X^{P_2}$$ is non-empty.

Let $$xP_1\in X^{P_2}$$. Then $$gxP_1 = xP_1$$ for all $$g\in P_2$$, which implies that **$$x^{-1}gx\in P_1$$ for all $$g\in P_2$$**. Therefore, we have $$x^{-1}P_2x\subseteq P_1$$. However $$\vert P_1\vert =\vert P_2\vert =\vert x^{-1}P_2x\vert$$ , so we must have $$x^{-1}P_2x = P_1$$. This shows that $$P_2$$ is conjugate to $$P_1$$ in $$G$$, completing the proof. ◼

> Conjugate 後大小不變！

---

## The Third Sylow Theorem
> Let **$$n_p$$** be the number of **Sylow $$p$$-subgroups**. Then $$n_p$$ satisfies the following **two conditions**:
>
> $$
> \begin{align*}
> &n_p \equiv 1 \pmod p, \tag{1}  \\
> &n_p \mid m. \tag{2}
> \end{align*}
> $$ 

> The subgroup $$H$$ of order $$p^n$$ is called a **Sylow $$p$$-subgroup**, which is exactly a maximal $$p$$-subgroup.

**Proof of $$n_p \equiv 1\pmod p$$**

Let $$P$$ be a Sylow $$p$$-subgroup of $$G$$, and let $$X$$ be the set of all Sylow $$p$$-subgroups. Let $$P$$ act on $$X$$ by conjugation. **Since $$P$$ is a $$p$$-group, we have $$n_p=\vert X\vert \equiv \vert X^P\vert \pmod p $$.**

Let $$Q\in X^P$$. Then [$$P\subseteq N_G(Q)$$](../normalizer/#normalizer). Since $$P$$ and $$Q$$ are both Sylow $$p$$-subgroups of $$N_G(Q)$$ (hint: $$N_Q(G) \leq G$$) , they are conjugate in $$N_G(Q)$$ by [the Second Sylow Theorem](#the-second-sylow-theorem). However, since $$Q$$ is normal, we must have 

$$
P = gQg^{-1} = (Qg)g^{-1} = Q,
$$

for some $$g\in N_G(Q)$$. This shows that $$X^P = \{P\}$$, and thus $$n_p\equiv \vert X^P\vert = 1 \pmod p$$.

---

**Proof of $$n_p \mid m$$**

Let $$X$$ be the set of all Sylow $$p$$-subgroups, and let $$G$$ act on $$X$$ by conjugation. Let $$P$$ be any Sylow $$p-$$subgroup. By the Second Sylow Theorem, **the $$G$$-orbit of $$P$$ is the whole set $$X$$. Then by [the orbit-stabilizer theorem](../group-action/#theorem-the-orbit-stabilizer-theorem), we have

$$
n_p = \vert X\vert = G_P = [G:\text{Stab}_G(P)],
$$

where 

$$
\text{Stab}_G(P) = \{g\in G\mid gPg^{-1}=P \} = N_G(P).
$$

Since $$P\leq N_G(P)$$, we have

$$
m = [G:P] = [G:N_G(P)][N_G(P):P] = n_p[N_G(P):P]. 
$$

Thus, $$n_p\mid m$$. ◼

### Corollary (normal)
> A Sylow $$p$$-subgroup is **normal iff $$n_p = 1$$**.

---

## Applications

> Check the corollaries [here](../normalizer/#normal-subgroups-with-small-indexes).

### Simple groups

> Recall: [Simple groups](../more-on-normal-subgroups/#simple-groups).

#### Theorem ($$p$$-group + non-abelian)
> **A non-abelian $$p$$-group is not simple**. Conversely, a non-abelian simple group is not a $$p$$-group.

**Proof**

By this [theorem](../more-group-action/#theorem-center-of-p-groups).

#### Lemma (injective homomorphism)
If $$G$$ is simple, then for any non-trivial homomorphism $$\rho:G\to G'$$, $$\rho$$ must be injective.

**Proof**

Suppose $$\rho$$ is not injective, which means that $$\text{ker}\rho > 1$$. However, since $$\text{ker}\rho$$ is normal and $$G$$ is simple, we must have $$\text{ker}\rho = G$$, i.e., $$\rho$$ is trivial. ◼

#### Theorem (orders)
> Suppose $$G$$ is a non-abelian **simple** group.
>
> 1. For all primes $$p\mid \vert G\vert$$, $$\vert G\vert \mid (np)!$$.
> 2. For all *proper* subgroups $$H$$ of $$G$$, $$\vert G\vert \mid [G:H]!$$.

**Proof 1.**

Since $$G$$ is simple and $$G$$ is not a $$p$$-group, we have $$n_p > 1$$. The action of $$G$$ on the set of Sylow $$p$$-subgroups by conjugation induces a group homomorphism $$\rho:G\to S_{n_p}$$. By the Second Sylow Theorem, such action is **transitive**, which implies $$\rho$$ is [non-trivial](../group-action/#remark-2). By this [lemma](#lemma-injective-homomorphism), $$\rho$$ is **injective** and $$\vert G\vert =\vert \rho(G)\vert$$ divides $$\vert S_{n_p}\vert = (n_p)!$$. ◼

**Proof 2.**

The action of $$G$$ on $$G/H$$ by left multiplication induces a group homomorphism $$\rho: G\to S_{G/H}$$. Since only $$h\in H_i$$ makes $$hH_i = H_i$$, $$\rho$$ is transitive; since $$H$$ is a proper subgroup, $$\rho$$ is non-trivial. Thus, $$\rho$$ is **injective** and $$\vert G\vert = \vert \rho(G)\vert $$ divides $$\vert S_{G/H}\vert= [G:H]!$$. 
