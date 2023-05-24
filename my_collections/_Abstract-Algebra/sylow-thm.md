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
  - [Corollary (all intersection =\> normal)](#corollary-all-intersection--normal)
    - [Lemma (conjugate; intersection)](#lemma-conjugate-intersection)
    - [Corollary (not simple)](#corollary-not-simple)
- [The Third Sylow Theorem](#the-third-sylow-theorem)
  - [Corollary (normal)](#corollary-normal)
- [**Remark**](#remark)
- [Applications](#applications)
  - [Simple groups](#simple-groups)
    - [Theorem ($$p$$-group + non-abelian)](#theorem-p-group--non-abelian)
    - [Lemma (injective homomorphism)](#lemma-injective-homomorphism)
    - [Theorem (orders)](#theorem-orders)
    - [Questions](#questions)

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

### Corollary (all intersection => normal)
> Let $$H = H_1\cap H_2\cap \cdots\cap H_n$$ be the intersection of all Sylow $$p$$-subgroups of $$G$$. Then $$H$$ is **normal** in $$G$$.

**Proof**

First, we should prove a lemma: 

#### Lemma (conjugate; intersection)

> For some $$g\in G$$, $$g(H_1\cap H_2)g^{-1} = (gH_1g^{-1})\cap(gH_2g^{-1})$$. 

Since $$\rho_g: h \mapsto ghg^{-1}$$ is an isomorphism, we have a bijective correspondence between $$H_1$$ and $$gH_1g^{-1}$$, and similarly, between $$H_2$$ and $$gH_2g^{-1}$$. Then, for all $$h\in H_1\cap H_2$$, there is also a bijective correspondence between $$h$$ and $$ghg^{-1}$$, and thus the lemma is proved.

Now consider $$gHg^{-1}$$ for some $$g \in G$$. We have

$$
gHg^{-1} = g\big(\bigcap_i H_i\big)g^{-1} = \bigcap_i\big(gH_ig^{-1}\big) \supseteq H,
$$

by [the second Sylow theorem](#the-second-sylow-theorem). However, it is obviois that $$gHg^{-1} \subseteq H$$, and thus $$gHg^{-1}=H$$. Since $$g$$ is arbitrary, we have proved that $$H$$ is a normal subgroup of $$G$$. ◼

#### Corollary (not simple)
> Let $$H = H_1\cap H_2\cap \cdots\cap H_n$$ be the intersection of all Sylow $$p$$-subgroups of $$G$$. If $$H$$ is non-trivial, then $$G$$ is **not simple**.

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

## **Remark**

對於兩質數 $$p$$、$$q$$，$$\mathcal S_p$$ 和 $$\mathcal S_q$$ 的交集必定只有 identity（從 element order 來想）。但對於兩個 Sylow $$p$$-subgroups，$$\mathcal{S_{p,1}}$$、$$\mathcal{S_{p,2}}$$，他們的交集**不一定**是 $$\{e\}$$：若 $$\vert S_{p, 1} \vert = \vert S_{p, 2} \vert = p$$，交集是 $$\{e\}$$，但若 $$\vert S_{p, 1}\vert = \vert S_{p, 2} \vert = p^k, k > 1$$，交集就不見得是 $$\{e\}$$（element order 可以是 $$p^j, j<k$$）！

假設有 $$m$$ 個 Sylow $$p$$-subgroups，對於任意兩 Sylow $$p$$-subgroup，他們的交集大小必須一樣嗎？答案是否定的，看看 [maximal Sylow intersection](https://groupprops.subwiki.org/wiki/Maximal_Sylow_intersection)。

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
> 1. For all primes $$p\mid \vert G\vert$$, $$\vert G\vert \mid (n_p)!$$.
> 2. For all *proper* subgroups $$H$$ of $$G$$, $$\vert G\vert \Big\vert [G:H]!$$.

**Proof 1.**

Since $$G$$ is simple and $$G$$ is not a $$p$$-group, we have $$n_p > 1$$. The action of $$G$$ on the set of Sylow $$p$$-subgroups by conjugation induces a group homomorphism $$\rho:G\to S_{n_p}$$. By the Second Sylow Theorem, such action is **transitive**, which implies $$\rho$$ is [non-trivial](../group-action/#remark-2). By this [lemma](#lemma-injective-homomorphism), $$\rho$$ is **injective** and $$\vert G\vert =\vert \rho(G)\vert$$ divides $$\vert S_{n_p}\vert = (n_p)!$$. ◼

**Proof 2.**

The action of $$G$$ on $$G/H$$ by left multiplication induces a group homomorphism $$\rho: G\to S_{G/H}$$. Since only $$h\in H_i$$ makes $$hH_i = H_i$$, $$\rho$$ is transitive; since $$H$$ is a proper subgroup, $$\rho$$ is non-trivial. Thus, $$\rho$$ is **injective** and $$\vert G\vert = \vert \rho(G)\vert $$ divides $$\vert S_{G/H}\vert= [G:H]!$$. 

#### Questions

**Q1:**

> Show that for any non-abelian group $$G$$, if $$\vert G\vert=132=2^2\cdot 3\cdot 11$$, $$G$$ is **not** a simple group.

**Solution**

We have $$n_2=1, 3, 11, 33$$, $$n_3=1,4$$, and $$n_{11} = 1, 12$$. Suppose $$n_{11}=12$$ and $$n_3=4$$. There are already $$(11-1)\cdot 12 + (3-1)\cdot 4 = 128$$ elements. Suppose $$n_2=3$$, for minimizing possible elements. Let $$N_2$$ denote the number of elements whose order divides $$4$$. Then by t*he inclusion-exclusion principle*, 

$$
\begin{align*}
N_2 = \vert H_1\cup H_2\cup H_3\vert &\geq \sum_i \vert H_i\vert - \sum_{\substack{i, j \\ i\not=j}}\vert H_i\cap H_j\vert \\
&\geq 4\cdot 3 - {3\choose 2}\cdot 2 \\
&= 6,
\end{align*}
$$

where $$H_i$$ are distinct Sylow $$2$$-subgroups. However, $$128 + 6=134>132$$, which is a contradiction. Thus, $$G$$ is not simple. ◼

> $$\vert H_i\cap H_j\vert = 1\text{ or } 2$$.

> $$n_p$$ 小的時候，inclusion-exclusion 比較容易奏效。

**Q2:**

> Show that for any non-abelian group $$G$$, if $$\vert G\vert=90$$, $$G$$ is **not** a simple group.

**Solution**

First note that $$90=2\cdot 3^2\cdot 5$$. As a routine, we check that 

$$
\begin{align*}
n_2&=1, 3, 5, 15 \\
n_3&=1, 10 \\
n_5&=1,6
\end{align*}
$$

by [the third Sylow theorem](#the-third-sylow-theorem). Since $$3$$ is the only prime which is squared, let's play with it. (Actually we should first suppose $$n_5=6$$, and count the elements of order $$5$$, trying to make a contradiction. However, this doesn't help.)

If $$n_3=1$$, game over. Suppose $$n_3=10$$. For any two distinct Sylow $$3$$-subgroup $$P$$ and $$Q$$, there are two possibilities: $$\vert P\cap Q\vert = 1$$ or $$3$$.

If $$\vert P\cap Q\vert=1$$, the number of elements whose order is divisible by $$3$$ is $$10 \cdot (9 - 1) = 80$$. Add this with the number of order $$5$$ elements, we have $$6\cdot(5-1) + 80 = 104 > 90$$, a contradiction. Thus, we must have some $$P, Q$$ such that $$\vert P\cap Q\vert = 3$$.

In such case, by [the second isomorphism theorem](../3-isomorphism/#the-second-isomorphism-theorem), 

$$
\vert PQ\vert = {\vert P\vert \vert Q\vert \over \vert P\cap Q\vert } = 27.
$$

Then, by [the first Sylow theorem](#the-first-sylow-theorem), we know that $$P\cap Q$$ is normal in $$P$$ and in $$Q$$(or use this [theorem](../normalizer/#theorem-smallest-index-normal)), which implies that 

$$
PQ \subseteq N_G(P\cap Q) \text{ and } P\leq N_G(P\cap Q).
$$

> $$P$$ and $$Q$$ are assumed to be **not** normal, and thus $$PQ$$ is **not** necessarily a subgroup!

Hence, we have gathered some information regarding the order of $$N_G(P\cap Q)$$:

1. $$\geq 27$$,
2. divisible by $$9$$,
3. divides $$90$$;

the only choices are $$45$$ and $$90$$. If $$\vert N_G(P\cap Q)\vert = 90$$, we have $$P\cap Q$$ as a non-trivial proper normal subgroup of $$G$$. If $$\vert N_G(P\cap Q)\vert = 45$$, since $$[G:N_G(P\cap Q)] = 2$$, we have $$N_G(P\cap Q)$$ as a normal subgroup of $$G$$. In conclusion, $$G$$ must not be simple. ◼

> Reference: [StackExchange](https://math.stackexchange.com/a/2793813)

> For $$\vert G\vert = 112$$, check [this](https://math.stackexchange.com/questions/351642/proving-that-a-group-of-order-112-is-not-simple). (Check all the answers, and comments.)

**Q3:**

> Show that for any non-abelian group $$G$$, if $$\vert G\vert=120$$, $$G$$ is **not** a simple group.

**Solution**

Assume $$G$$ is simple. Then we have $$n_5=6$$. This means (check the proof [here](#theorem-orders)) that $$\rho: G\to S_6$$ is injective. Moreover, since $$2$$ is the [minimum prime factor](../normalizer/#theorem-smallest-index-normal) of $$\vert G\vert=120$$, $$G$$ has no subgroup of index $$2$$, and neither does $$\rho(G)$$. This implies that $$\rho(G)$$ is composed of only even cycles (Otherwise, half of $$\rho(G)$$ is even and the other half is odd, which means that $$\rho(G)$$ has a subgroup of index $$2$$.), i.e., $$\rho(G)\le A_6$$. 

Now, let $$A_6$$ acts on $$A_6/\rho(G)$$. Since this action is transitive (multiply by some inverse), $$\rho': A_6 \to S_{\vert A_6/\rho(G)\vert} \cong S_3$$ is [non-trivial](../group-action/#remark-2), i.e., $$\text{ker}(\rho') \neq A_6$$. Moreover, since $$A_6$$ is simple ($$A_n$$ is [simple](https://sites.pitt.edu/~gmc/ch1/node4.html) except $$n=4$$.), we must have $$\text{ker}(\rho') = \{e\}$$. However, $$\vert A_6\vert = 360 > 6 = \vert S_3\vert$$, which is a contradiction. Therefore, $$G$$ is not simple. ◼

> Reference: [Aryaman](https://aryamanmaithani.github.io/alg/groups/simple/120/)
