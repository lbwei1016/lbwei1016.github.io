---
layout: page
title: Normal Extension and Separable Extensions
usemathjax: true
tag: Abstract Algebra, Field Extension
time: 2023/04/26
---

**Table of Content**
- [Normal Extensions](#normal-extensions)
  - [Definition (normal extension)](#definition-normal-extension)
    - [Definition (mapping extension)](#definition-mapping-extension)
  - [Theorem (Embedding extension theorem)](#theorem-embedding-extension-theorem)
  - [Definition (splitting field)](#definition-splitting-field)
  - [**Theorem (normal extension: eqivalence)**](#theorem-normal-extension-eqivalence)
    - [Corollary (char. zero)](#corollary-char-zero)
  - [Definition (normal closure)](#definition-normal-closure)
    - [Remark](#remark)
  - [Definition (separable extension)](#definition-separable-extension)
  - [**Theorem (separable extension: eqivalence)**](#theorem-separable-extension-eqivalence)
  - [**Theorem (Galois extension: eqivalence)**](#theorem-galois-extension-eqivalence)
    - [Corollary (intermediate field --\> Galois)](#corollary-intermediate-field----galois)
    - [Corollary (who is normal / separable?)](#corollary-who-is-normal--separable)
    - [Remark](#remark-1)


---

Recall from [Galois Extensions](../Galois-ext/#definition-galois-extension), we listed two conditions that a field extension must be satisfied, in order for it to be called a **Galois extension**. Here we dive into the details of the two conditions.

## Normal Extensions
### Definition (normal extension)
> Let $$E/F$$ be a field extension. $$E/F$$ is called a **normal extension** if $$\text{Aut}(E/F) = \text{Emb}(E/F)$$.

#### Definition (mapping extension)
> Let $$E/F$$ be a finite field extension and $$K$$ be an intermediate field between $$E$$ and $$F$$. Given $$\rho \in \text{Emb}(K/F)$$ and $$\tilde \rho\in \text{Emb}(E/F)$$, $$\tilde\rho$$ is called an **extension** of $$\rho$$ to $$E$$ if $$\tilde\rho\big\vert_K = \rho$$.

> 這個定義，對於任何兩個值域有包含關係的函數都可以用！

### Theorem (Embedding extension theorem)
> Let $$E/F$$ be a finite field extension and let $$K$$ be an intermediate field bewteen $$E$$ and $$F$$. For all $$\rho\in\text{Emb}(K/F)$$, there exists an extension of $$\rho$$ to $$E$$. Moreover, **if $$F$$ is of characteristic zero, then there are $$[E:K]$$ such extensions**.

### Definition (splitting field)
> If a field extension of $$F$$, $$E$$, is obtained by **adjoining all zeros of a polynomial** $$f(x)\in F[x]$$ in $$\bar F $$, then $$E$$ is called the **splitting field** of $$f(x)$$ over $$F$$, denoted by **$$F_f$$**. In other words, $$F_f$$ is the **smallest** field extension of $$F$$ in $$\bar F$$ in which $$f(x)$$ **splits**.

> split 代表 $$f(x)$$ 可以寫成 linear factor 的乘積。

> $$f(x)$$ 未必要 irreducible。

### **Theorem (normal extension: eqivalence)**
> Let $$E$$ be a finite field extension over $$F$$. The following are equivalent:
>
> - $$E/F$$ is a normal extension.
> - $$E$$ is the splitting field of **some** polynomial over $$F$$.
> - For all elements in $$E$$, its irreducible polynomial over $$F$$ splits over $$E$$.

> $$F$$ **needs not** be of characteristic zero.

#### Corollary (char. zero)
> Let $$E/F$$ be a finite field extension and $$\text{char}F = 0$$. Then $$E/F$$ is a Galois extension **iff** $$E$$ is the splitting field of some polynomial over $$F$$. 

> 因為當 $$char F=0$$，$$E/F$$ 是 Galois extension **iff** $$E/F$$ 是 normal！

### Definition (normal closure)
> The smallest field extension $$E'/F$$ such that $$E/F \le E'/F$$ and $$E'/F$$ is a normal extension, is called the **normal closure** of $$E/F$$.

#### Remark

若 $$E=F(\alpha)$$，$$E/F$$ 的 normal cloure 正是 $$\text{Irr}(\alpha, F)(x)$$ over $$F$$ 的 splitting　field！

### Definition (separable extension)
> A finite extension $$E/F$$ is called a **separable extension** if $$\vert \text{Emb}(E/F)\vert = [E:F]$$.

### **Theorem (separable extension: eqivalence)**
> Let $$E/F$$ be a finite field extension. The following are eqivalent:
>
> - $$E/F$$ is a separable extension.
> - $$E$$ is obtained from $$F$$ by joining some zeros of a separable polynomial in $$\bar F$$.
> - For all elements in $$E$$, its irreducible polynomial over $$F$$ is separable.

### **Theorem (Galois extension: eqivalence)**
> For a finite extension $$E/F$$, the following are equivalent:
>
> - $$E/F$$ is Galois.
> - $$E/F$$ is **normal** and **separable**.
> - $$E$$ is the splitting field of a separable polynomial over $$F$$.
> - For all elements in $$E$$, its irreducible polynomial over $$F$$ is separable and splits over $$E$$.

#### Corollary (intermediate field --> Galois)
> Let $$E/F$$ be a Galois extension. For all intermediate field $$K$$ between $$E$$ and $$F$$, **$$E/K$$ is Galois**.

#### Corollary (who is normal / separable?)
> Let $$E/F$$ be a finite field extension and $$K$$ be an intermediate field between $$E$$ and $$F$$. Then
>
> - If $$E/F$$ is normal, then **$$E/K$$ is normal**.
> - If $$E/F$$ is separable, then **$$E/K$$ and $$K/F$$ are separable**.
> - If $$E/F$$ is Galois, then **$$E/K$$ is Galois**.

#### Remark

$$E/F$$ 是 normal extension，代表 $$E$$ 含有 $$F[x]$$ 中某個不可約多項式 $$f(x)$$ 的所有零點。對於 $$K$$，我們可以取同一不可約多項式 $$f(x)$$，也就是說

$$
E = F_f \implies E = K_f \implies E/K \text{ is normal.}
$$

但是 $$K$$ 不見得包含所有 $$f(x)$$ 的零點，於是 $$K/F$$ 不一定 normal！