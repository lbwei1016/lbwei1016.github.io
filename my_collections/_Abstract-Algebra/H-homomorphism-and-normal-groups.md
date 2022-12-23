---
layout: page
title: Homomorphism & Normal Subgroups
usemathjax: true
tag: Abstract Algebra, Group Theory
time: 2022/10/20
---

**Table of Content**
- [Properties](#properties)
  - [Corollary (injective homomorphism)](#corollary-injective-homomorphism)
  - [Corollary (one-to-one)](#corollary-one-to-one)
  - [Corollary (onto)](#corollary-onto)
- [Facts](#facts)
  - [fact I](#fact-i)
  - [fact II](#fact-ii)
  - [Question (all the homomorphism)](#question-all-the-homomorphism)
- [Kernel](#kernel)
  - [Definition (kernel)](#definition-kernel)
  - [Theorem (kernel and coset)](#theorem-kernel-and-coset)
  - [Corollary (one-to-one)](#corollary-one-to-one-1)
- [Normal Subgroups](#normal-subgroups)
  - [Definition (normal subgroup)](#definition-normal-subgroup)
    - [Remark](#remark)
  - [Corollary (kernel is normal)](#corollary-kernel-is-normal)
  - [Proposition (index two)](#proposition-index-two)
  - [Theorem (equivalent conditions)](#theorem-equivalent-conditions)
- [Quotient Groups](#quotient-groups)
  - [Theorem (quotient group)](#theorem-quotient-group)
  - [Quotient Group Computation](#quotient-group-computation)
    - [Question](#question)
- [Homomorphism and Normal Groups](#homomorphism-and-normal-groups)
  - [Theorem (homomorphism and normal subgroups)](#theorem-homomorphism-and-normal-subgroups)
  - [Theorem (the first isomorphism theorem)](#theorem-the-first-isomorphism-theorem)
  - [Theorem (quotient group of integer modulo $$n$$)](#theorem-quotient-group-of-integer-modulo-n)
    - [Question](#question-1)
    - [Remark](#remark-1)
- [Reference](#reference)

---

## Properties

Let $$\phi$$ be a homomorphism of a group $$G$$ into a group $$G'$$.

- $$\phi(e) = e'$$.
- $$\phi(a^{-1})=\phi{(a)}^{-1} \text{ for all } a \in G$$.
- If $$H$$ is a subgroup of $$G$$, then $$\phi(H)$$ is a subgroup of $$G'$$.

> $$\phi(H)$$ is the **image** of $$H$$.

- If $$H'$$ is a subgroup of $$G'$$, then $$\phi^{-1}(H')$$ is a subgroup of $$G$$.

> $$\phi^{-1}(H)$$ is the **preimage** of $$H'$$.

> 請嘗試證明，尤其是 subgroup 的部分。

### Corollary (injective homomorphism)
> Let $$\phi: G\to G'$$ be a group homomorphism. If $$\phi$$ is **one-to-one** then $$G$$ and $$\phi(G)$$ are **isomorphic**. 

> 顯然 $$\phi: G \to \phi(G) $$ 已經 onto。

### Corollary (one-to-one)
> Homoporphism $$\rho$$ is **one-to-one** if $$\ker{\rho} = \{e\}$$.

### Corollary (onto)
> Homomorphism $$\rho$$ is **onto** if $$\rho(G)$$ contains a set of **generators** of $$G'$$.

> one-to-one 的 corollary 比較好用。

## Facts

Let $$\phi: G\to G'$$ be a group homomorphism.

### fact I

For $$a \in G$$, suppose its order is $$n$$. Since $$\phi$$ is homomorphism, we have

$$
\phi(a^n) = \phi(e) = e' = \phi(a)^n,
$$

and thus 

$$
\text{ord}(\phi(a))\big\vert n.
$$

### fact II

If $$\gcd(\vert G \vert, \vert G' \vert) = 1$$, for all $$g$$ in $$G$$, we let $$n = \text{ord}(\phi(g))$$ and $$m = \text{ord}(g)$$.

By Lagrange's Theorem, we have 

$$
n \big\vert \vert G' \vert,\ m \big\vert \vert G \vert.
$$

Moreover, by the definition of order, we have

$$
\phi(g^m) = e',
$$

which implies that $$\phi(g)^m$$ is identity and the order of $$\phi(g)$$ divides $$m$$. From this result, we can further observe that

$$
n \big\vert \vert G \vert, \\
\Rightarrow n \big\vert \gcd(\vert G \vert, \vert G' \vert) = 1,
$$

which means that $$n$$ is one. Thus for all $$\phi(g)$$ in $$G'$$, the order of them are one, i.e. $$\phi$$ is a **trivial homomorphism**.

### Question (all the homomorphism)

Describe **all** the homomorphism from $$\mathbb{Z}_6$$ to $$\mathbb{Z}_8$$.

**Solution**

Let $$\phi$$ be a homomorphism from $$\mathbb{Z}_6$$ to $$\mathbb{Z}_8$$. Suppose $$\phi(\bar 1) = k$$ for some $$k \in \mathbb{Z}_8$$. Then since $$\phi$$ is a homomorphism, we have, for all $$\bar m \in \mathbb{Z}_6$$, $$\phi(\bar m) = \phi(\bar 1+\bar 1+\cdots+\bar 1) = m\phi(\bar 1) = mk$$. In particular, we have $$\bar 6k = \phi(\bar 6) = \phi(\bar 0) = \bar 0$$, which means that $$6k \equiv 0 \text{ mod } 8 $$, i.e. $$k \equiv 0 \text{ mod }4 $$. Thus, $$\phi(\bar 1) = \bar 0, \bar 4$$, each of which uniquely determines a homomorphism.

In terms of kernel, if $$\phi(\bar 1) = \bar 0$$, then $$\text{ker}(\phi) = \mathbb{Z}_6$$; otherwise, $$\text{ker}(\phi) = \{\bar 0, \bar 2, \bar 4\} = \langle \bar 2 \rangle$$.

To generalize, **what is the number of all possible homomorphisms from $$\mathbb{Z}_n$$ to $$\mathbb{Z}_m $$**? From the above result, we see that

$$
nk \equiv 0 \text{ mod m},
$$

which is to say

$$
k \equiv (n/\gcd(n, m))^{-1} \text{ mod }(m/\gcd(n,m)).
$$

Let $$(n/\gcd(n, m))^{-1} = a$$. Therefore, 

$$
k = a, a+{m\over \gcd(n,m)}, a+{2m\over \gcd(n,m)}, \cdots, a+{(\gcd(n,m)-1)m\over \gcd(n,m)},
$$

which means that there are **$$\gcd(n, m)$$ homomorphisms**.

---

## Kernel
### Definition (kernel)
> The **subgroup** $$\phi^{-1}(\{e'\}) $$ is called the **kernel** of $$\phi$$, denoted by **$$\text{ker}(\phi)$$**.

也就是說，對於任意在 domain $$X$$ 的 $$x$$，只要 $$\phi(x) = e'$$，那麼 $$x$$ 就在 $$\text{ker}(\phi)$$ 中！

**Example**

We know that 

$$
\text{sgn: }S_n \to \{\pm 1\}
$$

is a group homomorphism, and therefore $$A_n = \text{ker(sgn)}$$ is a **subgroup** of $$S_n$$.

> $$A_n$$ 是 [even permutation 形成的 subgroup！](../D-transpositions/#corollary-even-permutation)

### Theorem (kernel and coset)

Let $$\psi: G\to G'$$ be a group homomorphism, and let $$H = \text{ker}(\psi)$$. Let $$a\in G$$. Then the set

$$
\{x \in G: \psi(x)=\psi(a) \} = \psi^{-1}(\{\psi(a) \})
$$

is the **left coset $$aH$$**, and is also the **right coset $$Ha$$**.

> $$\psi^{-1}(\{\psi(a) \})$$ 是 $$\psi(a)$$ 的 preimage！（$$\psi(a)$$ 來的地方。）

### Corollary (one-to-one)

> A group homomorphism $$\psi: G \to G'$$ is **one-to-one** iff $$\text{ker}(\psi) = \{e\}$$.

One-to-one 本來就會使 $$\text{ker}(\psi) = \{e\}$$；而當 $$\text{ker}(\psi) = \{e\}$$ 時，對於任意 $$a \in G$$，他的 preimage 都是 $$aH = a$$，也就證明了 one-to-one。

**Proof of the theorem** 

We first show that $$aH \subseteq \psi^{-1}(\{\psi(a)\})$$: Let $$x=ah\in aH$$. Since $$\psi$$ is a homomorphism, we ahve $$\psi(x) = \psi(a)\psi(h) = \psi(a)e' = \psi(a)$$. Therefore, $$x \in \psi^{-1}(\{\psi(a)\})$$.

Then, we are to show that $$\psi^{-1}(\{\psi(a)\}) \subseteq aH$$ : Suppose that $$x \in \psi^{-1}(\{\psi(a)\})$$. We have $$\psi(x) = \psi(a)$$, and thus $$\psi(a)^{-1}\psi(x) = e'$$. Then $$\psi(a^{-1})\psi(x) = \psi(a^{-1}x) = e'$$, which implies that $$a^{-1}x \in H$$. We see that $$x \in aH$$.

The proof for the right coset is similar. ◼

**Example**

Let $$\psi: \mathbb{Z} \to \mathbb{Z}_n $$ defined by $$\psi(a) = \bar a$$; then $$\text{ker}(\psi) = n\mathbb{Z}$$. For each $$\bar b \in \mathbb{Z}_n$$, its preimage $$\psi^{-1}(\{\bar b\}) = \{\cdots,b-n,b,b+n,\cdots \} = b + n\mathbb{Z}$$ is indeed a coset. 

---

## Normal Subgroups
### Definition (normal subgroup)

> A subgroup $$H$$ of a group $$G$$ is **normal** if its left cosets and right cosets concide, that is, if 
>
>$$
> gH = Hg,\ \text{for all } g \in G.
>$$
> If $$H$$ is a normal subgroup of $$G$$, we denoted it as $$H \triangleleft G $$.

#### Remark

看到 $$gH=Hg$$，我們可能會想到 abelian group：$$gx = xg$$；事實上，*being normal* 是比 *being abelian* 弱的性質，因為 abelian 要求一一對應，而 normal 只需要「整個集合」一樣就好了（像是 $$g_1H = Hg_2$$）。

另外，檢查一 subgroup $$H$$ 是否 normal 只需看 group  $$G$$ 和 subgroup $$H$$ 的 generator(s) 就好，因對於所有 $$g\in G$$，$$g$$ 都可以用 generator(s) 來表示：如果 generator(s) 可以在 $$H$$ 左右移動，則任意 $$h$$ 拆成 generator(s) 之後也必可以在 $$H$$ 左右移動；演示如下：

If $$G = \langle g_1, \cdots,g_n\rangle$$, and let $$g = g_1^{k_1}\cdots g_n^{k_n}$$. Then

$$
\begin{align*}
(g_1^{k_1}\cdots g_n^{k_n})h(g_1^{k_1}\cdots g_n^{k_n})^{-1} &= (g_1^{k_1}\cdots g_n^{k_n})h(g_n^{k_n})^{-1}\cdots(g_1^{k_1})^{-1} \\
&= (g_1^{k_1}\cdots g_{n-1}^{k_{n-1}})h'(g_{n-1}^{k_{n-1}})^{-1}\cdots(g_1^{k_1})^{-1} \\
&= \cdots \in H.
\end{align*} 
$$

If $$H = \langle h_1,\cdots, h_m\rangle$$, and let $$h = h_1^{i_1}\cdots h_m^{i_m}$$. Then

$$
\begin{align*}
g(h_1^{i_1}\cdots h_m^{i_m})g^{-1} = (gh_1^{i_1}g^{-1})\cdots(gh_m^{i_m}g^{-1}) \in H.
\end{align*}
$$

> 非常好用！尤其在處理 [permutaiton group](../9-Groups-of-Permutation/#theorem-generator) 的時候。

### Corollary (kernel is normal)
> If $$\psi: G\to G'$$ is a group homomorphism, then $$\text{ker}(\psi)$$ is a normal subgroup.

> From [this theorem](#theorem-kernel-and-coset).

### Proposition (index two)

> Let $$N$$ be **a subgroup of [index](../F-Lagrange-thm/#index) two** of $$G$$. Then $$N$$ is normal.

**Proof**

For $$g \in G$$, if $$g \in N$$, then $$gN = N = Ng$$. If $$g \not \in N$$, then $$G=N \bigsqcup gN = N \bigsqcup Ng$$, and therefore $$gN = G\backslash N = Ng$$. We now have $$gN = Ng$$. ◼

### Theorem (equivalent conditions)

> The following are equivalent conditions for a subgroup $$H$$ of a group $$G$$ to be normal.
>
> 1. $$ghg^{-1} \in H$$ for all $$g$$ in $$G$$ and all $$h$$ in $$H$$,
> 2. $$gHg^{-1} = H$$ for all $$g$$ in $$G$$,
> 3. $$gH = Hg$$ for all $$g$$ in $$G$$,
> 4. $$aHbH = abH$$ for all $$a,b$$ in $$G$$.

**Proof**

$$(1)\Rightarrow(2)$$:

Suppose $$gHg^{-1} \subset H$$ for all $$g \in G$$. Replacing $$g$$ with $$g^{-1}$$, we have $$g^{-1}Hg \subset H$$, which implies that $$H \subset gHg^{-1}$$. We conclude that $$gHg^{-1} = H$$.

$$(4)\Rightarrow(1)$$:

For $$g \in G$$,

$$
ghg^{-1}e \in gHg^{-1}H = gg^{-1}H = H.
$$

---

## Quotient Groups

From [this theorem](#theorem-equivalent-conditions), we see that for $$G/N$$, the left coset of a normal subgroup $$N$$ of $$G$$, we have

$$
aNbN = abN
$$

for all $$a,b \in G$$. Then we can see that

$$
aN * bN := abN
$$

is a [well-defined](../2-Isomorphism/#well-definedness) binary operator on $$G/N$$.

> For $$c=a, d=b$$, we have $$cNdN = cdN = abN = aNbN$$.

### Theorem (quotient group)
> $$(G/N,*)$$ is a group, called the **quotient group** of $$G$$ *by* $$N$$.

To prove $$(G/N,*)$$ be a group, we have to check three conditions: **Associativity, Identity, Inverse**.

**Example $$\rm I$$**

Let $$G = \mathbb{Z}_6$$ and $$N = \{\bar 0, \bar 3\}$$. The left cosets are $$N,\bar 1+N,\bar 2+N$$. Moreover, we have $$(\bar 1+N) + (\bar 1+N) = \bar 2+N$$ and $$(\bar 1+N) +(\bar 1+N) +(\bar 1+N) = N$$. Therefore, $$G/N$$ is a **cyclic group** of order $$3$$ generated by $$\bar 1+N$$.

**Example $$\rm II$$**

> 見 [Remark](#remark)。

對於 $$D_4$$，令 $$N = \langle \sigma^2 \rangle$$。欲檢查 $$N$$ 是否 normal，我們只需看 generators $$\sigma$$ 和 $$\tau$$。而

$$
N\sigma = \{\sigma^3,\sigma \} = \sigma N,\\
N\tau = \{\tau\sigma^2, \tau \} = \tau N,
$$

所以 $$N$$ is normal，且

$$
D_4 = N \bigsqcup \sigma N \bigsqcup \tau N \bigsqcup \tau \sigma N.
$$

於是，$$D_4$$ 的 quotient group is of order $$4$$，和 $$\mathbb{Z}_4$$ 或 $$\mathbb{Z}_2\times \mathbb{Z}_2$$ 同構。再來，因為 $$D_4/N$$ 的每一元素都是 order $$2$$，所以 $$D_4/N \cong \mathbb{Z}_2\times \mathbb{Z}_2$$。

### Quotient Group Computation

試著找出一個 group $$G'$$ isomorphic to the **quotient group** $$G/H$$，因為 quotient group 不易處理和計算！

**Some facts**

1. $$G/\{e\} \cong G$$.
2. $$G/G$$ is isomorphic to the trivial group with one element.
3. If $$G$$ is cyclic, then $$G/H$$ is also cyclic.
4. If $$G=G_1\times G_2$$, then $$G/(\{e\})\times G_2 \cong G_1$$.
5. If $$G=G_1 \times G_2$$, $$H_1\triangleleft G_1$$, and $$H_2 \triangleleft G_2$$, then $$G/(H_1\times H_2)$$ is isomorphic to $$(G_1/H_1 \times (G_2/H_2))$$. 

**Proof of 3.**

If $$G = \langle a \rangle$$, then every coset of $$H$$ is of the form $$a^kH = (aH)^k$$ for some integer $$k$$. Thus, $$G/H = \langle aH \rangle$$. ◼

> $$H = \langle a^d \rangle$$, $$d \vert n$$.


要證明 quotient group 和某 group isomorphic，可以用 [the first isomorphism theorem](#theorem-the-first-isomorphism-theorem)：

Construct $$\rho: G \to G'$$, and then $$G/\text{ker} (\rho) \cong \rho(G)$$.

**Proof of 4.** 

Let $$\phi: G_1\times G_2 \to G_1$$ be defined by $$\phi(g_1, g_2) = g_1$$. Then we have $$\text{ker}(\phi) = \{e_1\}\times G_2$$. We complete the proof by the first isomorphism theorem. ◼

**Proof of 5.**

Let $$\phi: G_1\times G_2 \to (G_1/H_1)\times (G_2/H_2)$$ defined by $$\phi(g_1, g_2) = (g_1H_1, g_2H_2)$$. By apply the first isomorphism theorem, we obtained the desired result. ◼

#### Question

> Classify the quotient group $$\mathbb{Z}_4\times \mathbb{Z}_2/\langle (2,0)\rangle$$.

(Guess that the answer is $$\mathbb{Z}_2\times\mathbb{Z}_2$$.)

Define a function $$\phi: \mathbb{Z}_4\times \mathbb{Z}_2 \to \mathbb{Z}_2\times \mathbb{Z}_2$$ by 

$$
\phi(a \text{ mod } 4, b \text{ mod } 2) = (a \text{ mod } 2, b \text{ mod } 2),
$$

which is *well-defined* since $$2\vert 4$$. We can also see that $$\phi$$ is a homomorphism.

The kernel is $$\{(\bar 0, \bar 0),(\bar 2, \bar 0) \} = H$$. Moreover $$\phi$$ is onto since 

$$
(\bar 1, \bar 0) = \phi(\bar 1, \bar 0),\\
(\bar 0, \bar 1) = \phi(\bar 0, \bar 1).
$$

> generator 都 map 到了！於是 onto。

Therefore, by the first isomorphism theorem we have 

$$
\mathbb{Z}_4\times \mathbb{Z}_2/\langle (2,0)\rangle \cong \mathbb{Z}_2\times\mathbb{Z}_2.
$$

> 先猜，然後建 isomorphism，最後用 theorem！

---

## Homomorphism and Normal Groups
### Theorem (homomorphism and normal subgroups)
> Let $$N$$ be a normal subgroup of $$G$$. Then $$\gamma:G \to G/N$$ given by $$\gamma(g) = gN$$ is a homomorphism with the kernel $$N$$.

> "with the kernel $$N$$" 指的是 $$N = \text{ker}(\gamma)$$！

**Proof**

Since $$N \triangleleft G$$, we have $$(aN)(bN) = (ab)N$$, that is, $$\gamma(a)\gamma(b) = \gamma(ab) $$, and thus $$\gamma $$ is a homomorphism.

For the second part, we know that $$g \in \text{ker}(\gamma)$$ iff $$gN=eN$$. This means that $$g \in \text{ker}(\gamma)$$ iff $$g \in N$$. Thus $$N = \text{ker}(\gamma)$$. ◼

### Theorem (the first isomorphism theorem)
> Let $$\psi: G\to G'$$ be a group homomorphism with kernel $$N$$. Then $$G/N$$ and $$\psi(G)$$ are isomorphic. The **canonical isomorphism** $$\mu: G/N \to \psi(G) $$ is given by $$\mu(gN) = \psi(g)$$.

> $$G/\text{ker}(\psi) \cong \psi(G) = \text{the image of }G = \text{Im}(G)$$.

> 也稱作 the **fundamental homomorphism theorem**。

$$G/\text{ker}(\psi)$$ 的 order 正是 left coset 的數量，又 isomorphic groups 的 order 必相等。因此

$$
\vert G \vert = \vert \text{ker}(\psi) \vert \cdot \vert \text{Im}(G) \vert.
$$

**Proof**

For $$\mu$$, we need to check four conditions:

1. well-definedness
2. one-to-one
3. onto
4. homomorphism

**proof of well-definedness**

Suppose $$g_1N = g_2N$$. We need to show that $$\mu(g_1N) = \mu(g_2N)$$. 

We know that $$g_1N = g_2N$$ iff $$g_1 = g_2h$$ for some $$h \in N$$. Then 

$$
\mu(g_1N) = \psi(g_1) = \psi(g_2h) = \psi(g_2)\psi(h).
$$

Since $$N$$ is the kernel of $$\psi$$, we have $$\psi(h)=e'$$. Therefore, $$\mu(g_1N) = \psi(g_2) = \mu(g_2N)$$.

**proof of one-to-one**

Suppose that $$\mu(g_1N) = \mu(g_2N)$$, which means $$\psi(g_1) = \psi(g_2)$$. Then we have $$\psi(g_2^{-1}g_1) = e'$$, which implies that $$g_2^{-1}g_1 \in \text{ker}(\psi) = N$$. Hence, $$g_1N = g_2N$$.

> $$g_1N = g_2N$$ iff $$g_2^{-1}g_1 \in N$$.

**proof of onto**

For all $$g' \in \psi(G)$$, we have some $$g \in G$$ such that $$\psi(g) = g'$$. Therefore, we have $$gN \in G/N$$ such that $$\mu(gN) = \psi(g) = g'$$.

**proof of homomorphism**

By the fourth statement of [this theorem](#theorem-equivalent-conditions). ◼

### Theorem (quotient group of integer modulo $$n$$)
> Every **abelian group** with **$$n$$ generators** is isomorphic to a **quotient group of $$\mathbb{Z}^n$$.**

**Proof**

Let $$g_1\cdots g_n$$ be a set of generators of an *additive* group $$G$$. Then $$G = \{\sum a_ig_i \vert a_i \in \mathbb{Z} \}$$. Let 

$$
\rho: \mathbb{Z}^n \to G
$$

defined by $$\rho((a_1,\cdots,a_n)) = \sum a_ig_i$$, which is a surjective group homomorphism. By [the first isomorphism theorem](#theorem-first-isomorphism-theorem), $$G$$ is isomorphic to $$\mathbb{Z}^n/\text{ker}(\rho)$$. ◼

#### Question

> Let $$G=D_6$$ and $$H_1 = \langle \sigma^2,\tau \rangle$$. Find a group homomorphism from $$G$$ with kernel equal to $$H_1$$.

**Solution**

設該 homomorphism 為 $$\phi$$，利用本定理，$$G/H_1 \cong \phi(G)$$，也就是說，

$$
\phi(G) \cong \{H_1, \sigma H_1\}。
$$

從上式可以看出，for all $$g\in \text{ker}(\phi)$$, $$\phi(g) = H_1$$（因為 $$H_1$$ 是 identity！）所以若定義 $$\phi(g) = gH_1$$，則

$$
gH_1 = H_1 \iff g \in H_1,
$$

說明了 $$\text{ker}(\phi) = H_1$$！

#### Remark

According to [the first isomorphism theorem](#theorem-first-isomorphism-theorem), $$\mathbb{Z}^n/\text{ker}(\rho) \cong \rho(\mathbb{Z}^n)$$. However, since $$\rho$$ is **surjective**, we have $$\rho(\mathbb{Z}^n) = G$$. Thus the result follows.

---

## Reference

- [Describe all the group homomorphism...](https://math.stackexchange.com/questions/2207900/describe-all-the-group-homomorphisms-from-mathbbz-24-to-mathbbz-18)
