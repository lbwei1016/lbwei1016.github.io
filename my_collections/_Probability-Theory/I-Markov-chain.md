---
layout: page
title: Markov Chains
usemathjax: true
tag: Probability, Statistics
time: 2022/01/06
---

**Table of Content**
- [Discrete-Time Finite State Markov Chains](#discrete-time-finite-state-markov-chains)
  - [Transition probabilities](#transition-probabilities)
    - [Multiplicative rule](#multiplicative-rule)
  - [Steady-state propabilities](#steady-state-propabilities)
- [Misc](#misc)
- [Reference](#reference)

---

## Discrete-Time Finite State Markov Chains
### Transition probabilities

Let $$X_n$$ be the state after $$n$$ transitions.

**1-step**

$$
\begin{align*}
p_{ij} &= \text{P}(X_{1}=j\mid X_0=i) \\
&= \text{P}(X_{n+1}=j\mid X_n=i) ,\text{ (time homogeneous)} \\
&= \text{P}(X_{n+1}=j \mid X_n=i,X_{n-1},\cdots,X_0)
\end{align*}
$$

> **Markov property**: Given the current state, *the past before the previous state* doesn't matter.

> 只和前一 state 有關。

**$$n$$-step (Chapman-Kolmogorov Equation)**

$$
\begin{align*}
  r_{ij}(n) &= \text{P}(X_{n+s}=j\mid X_s=i) \\
  &= \sum_{k=1}^m r_{ik}(n-1)p_{kj}
\end{align*}
$$

In addition, 

$$
r_{ij}(0) = \begin{cases}
  1 &\text{if } i=j, \\
  0 &\text{if } i\not = j.
\end{cases} \\

r_{ij}(1) = p_{ij}.
$$

If we let $$P = \big[p_{ij}\big], R_n = \big[r_{ij}(n)\big]$$, then

$$
R_n = R_{n-1}P = P^n.
$$

#### Multiplicative rule

$$
\begin{align*}
  &\text{P}(X_1=0, X_2=3, X_3=2\mid X_0=1)  \\ 
  =\ &\text{P}(X_1=0\mid X_0=1)\text{P}(X_2=3\mid X_1, X_0)\text{P}(X_3=2\mid X_2, X_1, X_0) \\
  =\ &\text{P}(X_1=0\mid X_0=1)\text{P}(X_2=3\mid X_1=0)\text{P}(X_3=2\mid X_2=3) \\
  =\ &p_{1,0}p_{0,3}p_{3,2}
\end{align*}
$$

### Steady-state propabilities

For a Markov chain, if 

- recurrent states are all in a **single class** and 
- the single recurrent class is **not periodic**,

then $$r_{ij}(n) \to \pi_j$$ when $$n\to \infty$$, no matter what $$i$$ is. Thus we have

$$
\lim_{n\to \infty}r_{ij}(n) = \lim_{n\to \infty} \sum_{k=1}^m r_{ik}(n-1)p_{kj} \\
\implies \pi_j = \sum_{k=1}^m\pi_k p_{kj}.
$$

To solve the above system of linear equations, we also need:

$$
\sum_{j=1}^m\pi_j = 1.
$$

> **(recurrent) class**：想像 state diagram 的強連通子圖，而 recurrent state 就是包含在 class 的 state。
> 
> **periodic**：將整個 class 分成 $$n$$ 個子區塊，並給予編號。狀態轉移將依序從編號 $$1$$ 到 $$n$$，然後再回到 $$1$$。

---

## Misc
- Erlang distridution
- [Phone system](https://ocw.mit.edu/courses/res-6-012-introduction-to-probability-spring-2018/resources/design-of-a-phone-system/)

---

## Reference

- [MIT OCW](https://ocw.mit.edu/courses/res-6-012-introduction-to-probability-spring-2018/pages/part-iii-random-processes/)