---
layout: page
title: Discrete Random Variables
usemathjax: true
tag: Discrete, Random Variable, PMF
time: 2022/09/28
---

**Table of Content**
- [Random Variable](#random-variable)
  - [Definition](#definition)
  - [Independence](#independence)
- [Probability Mass Function (PMF)](#probability-mass-function-pmf)
  - [Definition](#definition-1)
- [Expected Value](#expected-value)
  - [Definition](#definition-2)
  - [Properties](#properties)
- [Variance](#variance)
  - [Definition](#definition-3)
  - [Properties](#properties-1)
- [Multiple Random Variable](#multiple-random-variable)
  - [Joint PMFs](#joint-pmfs)
  - [Functions of Multiple Random Variables](#functions-of-multiple-random-variables)
- [Special Random Variables](#special-random-variables)
  - [Uniform](#uniform)
  - [Bernoulli](#bernoulli)
  - [Binomial](#binomial)
  - [Geometric](#geometric)
    - [Memorylessness](#memorylessness)
  - [Poisson](#poisson)
- [Reference](#reference)

---

## Random Variable
### Definition
> A **random variable** $$X$$ is a *measurable function* $$X: \Omega \to E$$ from a sample space $$\Omega$$ to a measurable space $$E$$. 

> $$E$$ 可以是 $$\mathbb{R}$$、$$\mathbb{Z}$$ 等等；*measurable* 的定義之後再補

**Random variable** 的意義在於，「賦予」樣本空間中的每一事件一個可供計算的數值（粗淺來說）；例如，對於 $$\Omega = \{\text{head}, \text{tail}\}$$，可以定義

$$X(\text{head}) = 1, X(\text{tail}) = 0。$$

$$X(\omega)$$ 這個 function 可以不必是 *one-to-one*、*onto*。

### Independence
$$X$$ and $$Y$$ are **independent** random variables if 

$$P(X=x \land Y=y) = P(X=x)\dot{}P(Y=y).$$

---

## Probability Mass Function (PMF)
### Definition
> A **probability mass function (pmf)** is a function over the sample space of a discrete random variable $$X$$ which gives the probability that $$X$$ is equal to a certain value. 

Let $$X$$ be a random variable on a sample space $$\Omega$$. Then the **pmf** $$p: E \to [0,1]$$ is defined as

$$p_X(x) = P(X=x)$$

which must satisfies two conditions:

$$\sum_x p_X(x) = 1 \tag{1}$$
$$p_X(x) \ge 0 \tag{2}$$

> 賦予隨機變數值一機率。

---

## Expected Value
### Definition

The *mean* of a random variable $$X$$ on a probability sapce $$\Omega$$ is defined to be

$$\sum_{x \in X(\Omega)}x \dot{}P(X=x).$$

> If the sum is *infinite*, it has to be *well-defined* (convergent).

We can give the mean a special name and some alternative notations: Call it the **expected value** and write

$$\begin{align*}
EX = E(X) = E[X] &= \sum_{\omega \in \Omega}X(\omega)P(\omega) \\
&= \sum_{x}x \dot{}p_X(x) \\
&=  \mu
\end{align*}$$

### Properties

If $$X$$ and $$Y$$ are any two random variable defined on the same probability space $$\Omega$$, then

$$E(X+Y) = \sum_{\omega \in \Omega}(X(\omega) + Y(\omega))P(\omega) = EX + EY. \tag{1}$$

> 可以用來計算 the mean of the binomial（擲硬幣成功的次數的期望值）：
> 
> $$E\Big[\sum_i^n X_i\Big] = \sum_i^n E[X_i] = np.$$ 

這是期望值的 **linearity** 特性，也可以用 [joint pmf](./#multiple-random-variable) 來證明：

$$
\begin{align*}
E[X+Y] &= \sum_x \sum_y (x+y)p_{X,Y}(x,y) \\
&= \sum_x \sum_y xp_{X,Y}(x,y) + \sum_x \sum_y yp_{X,Y}(x,y) \\
&= \sum_x x\sum_y p_{X,Y}(x,y) + \sum_y y\sum_x p_{X,Y}(x,y) \\
&= \sum_x xp_X(x) + \sum_y yp_Y(y) \\
&= E[X] + E[Y]. \tag*{$\blacksquare$}
\end{align*}
$$


Moreover, if $$X$$ and $$Y$$ are [independent](#independence), 

$$E(XY) = E(X)E(Y). \tag{2}$$

> 左式展開即可證明。

另外，

$$E(\alpha X + \beta) = \alpha E(X) + \beta。 \tag{3}$$

還有還有，

$$
E[X] = \sum_{x=1}^n xP(X=x) = \sum_{x=1}^nP(X\ge x).
$$

> 這是在分析演算法時遇到的。

---

## Variance
### Definition

**Variance** is defined as the mean square deviation from the mean:

$$VX = V(X) = E((X-EX)^2).$$

**Variance** 用來量測數據的分散性（偏離平均的量），但計算過程的平方使得 variance 呈現的尺度被放大；為了回到常軌，我們取 square root

$$\sigma = \sqrt{VX}，$$

稱其作 **standard deviation**。

### Properties

$$\begin{align*}
  VX &= E((X - EX)^2) \\
  &= E(X^2 - 2XE(X) + E(X)^2) \\
  &= E(X^2) - 2E(X)E(X) + E(X)^2 \\
  &= E(X^2) - E(X)^2 \tag{1}
\end{align*}
$$

> *"The variance is the mean of the square minus the square of the mean."*  

If $$X$$ and $$Y$$ are [independent](#independence),

$$V(X+Y) = VX + VY.$$

> 用到 [independent expected value](#properties) 的性質。

> *"The variance of a sum of independent random variables is the sum of their
variances."* 

---

## Multiple Random Variable
### Joint PMFs
Suppose $$X,Y$$ are two random variables associated with the same experiment. The pmf of $$(x,y)$$ is

$$p_{X,Y}(x,y) = P(X=x \text{ and } Y=y) = P(X=x,Y=y),$$

and we have

$$\sum_x \sum_y p_{X,Y}(x,y) = 1.$$

Moreover, the following are called **marginal pmfs**:

$$p_X(x) = \sum_y p_{X,Y}(x,y),\\ p_Y(y) = \sum_x p_{X,Y}(x,y).$$

> 固定自己，sum over 另一個。

> 可以推廣至 $$n$$ 個 random variable。

### Functions of Multiple Random Variables

For $$Z = g(X,Y)$$, we have

$$E[Z] = E[g(X,Y)] = \sum_x \sum_y g(x,y)p_{X,Y}(x,y).$$

> 可用來證明 $$E[X+Y] = E[X] + E[Y]$$。

---

## Special Random Variables

### Uniform 

大家分配到的機率都一樣。

**Variance**

Suppose $$X$$ is uniformly distributed between $$[1, n]$$. We have

$$
E[X] = (1 + n) / 2, \\
E[X^2] = \sum_x x^2 \cdot {1\over n} = (n+1)(2n+1)/6.
$$

Then

$$
var(X) = (n^2 - 1)/12.
$$

Now suppose $$Y$$ is uniformly distributed among $$[a, b]$$, where $$b-a+1 = n$$. We can easily seen that the distribution of $$Y$$ is only the shifted one of $$X$$; thus $$var(Y) = var(X)$$, which means

$$
var(Y) = {(b-a+1)^2 - 1\over 12} = {(b-a)(b-a+2)\over 12}.
$$

### Bernoulli

$$X = \begin{cases}
  1,\ \text{head}, \\
  0,\ \text{tail}.
\end{cases}$$

### Binomial
> $$n$$ 次 Bernoulli expriment。

$$p_X(k) = {n \choose k}p^k(1-p)^{n-k},\ k \in \mathbb{N}.$$

$$
E[X] = np,\ var(X) = np(1-p).
$$


### Geometric

**PMF**:

$$p_X(k) = (1-p)^{k-1}p,\ k \in \mathbb{Z}^+.$$

#### Memorylessness

For $$n \ge 1$$,

$$
\begin{align*}
P(X-1=n|X>1) &= {P(X=n+1 \text{ and } X>1) \over P(X>1)} \\
&= {P(X=n+1) \over P(X>1)} \\
&= {(1-p)^np \over 1-p} \\
&= (1-p)^{n-1}p \\
&= P(X=n)
\end{align*}
$$

> 換個立足點，重新開始，試驗成功的機率不變（因為獨立）。

> 見 [exponential r.v.](../4-continous-rv/#memoryless)。

用來計算 the mean of the geometric:

$$\begin{align*}
E[X] &= E[X-1] + 1 \\
&= 1 + pE[X-1|X=1] + (1-p)E[X-1|X>1] \\ 
&= 1+ p\times 0 +(1-p)E[X],
\end{align*}$$

$$\Rightarrow E[X] = {1\over p}.$$

> $$var(X) = (1-p)/p^2$$.

### Poisson

**PMF**

$$
p_X(k) = e^{-\lambda}{\lambda^k \over k!},\ k=0,1,2,\cdots
$$

This is a PMF since 

$$
\sum_k e^{-\lambda}{\lambda^k \over k!} = e^{-\lambda}e^\lambda = 1.
$$

Poisson PMF with parameter $$\lambda$$ is a good **approximation** for a *binomial PMF* with parameters $$n$$ and $$p$$, i.e.,

$$
e^{-\lambda}{\lambda^k \over k!} \approx {n \choose k}p^k(1-p)^{n-k},\ k \in \mathbb{N}
$$

provided **$$\lambda = np$$**. We now show that the pmf of a binomail r.v. with parameters $$n$$ and $$p$$ **approaches** the pmf of a Poisson r.v. with parameter $$\lambda = np$$.

**Solution**

$$
\begin{align*}
p_X(k) &= {n \choose k}p^k(1-p)^{n-k} \\
&= {n(n-1)\cdots(n-k+1) \over n^k} \dot{} {\lambda^k \over k!} \dot{} (1- {\lambda \over n})^{n-k}.
\end{align*}
$$

When $$k$$ is fixed and $$n \to \infty$$, we have, for $$j=1,\cdots,k,$$

$$
{n-k+j \over n} \to 1,\ (1-{\lambda \over n})^{-k} \to 1, (1-{\lambda \over n})^n \to e^{-\lambda}.
$$

Thus, we obtain

$$p_X(k) \to e^{-\lambda}{\lambda^k \over k!}. \tag*{$\blacksquare$} $$

> Poisson 是極限情況的 binomial！（當某事發生機率極低）

---

## Reference
- [Wiki: Random variable](https://en.wikipedia.org/wiki/Random_variable)
- [ncl.ac.uk](https://www.ncl.ac.uk/webtemplate/ask-assets/external/maths-resources/statistics/distribution-functions/probability-mass-function.html)
- [Wiki: Probability mass function](https://en.wikipedia.org/wiki/Probability_mass_function)
- [CMath] (Chapter 8), Concrete Mathematics: A Foundation for Computer Science, by Ronald Graham, Donald Knuth, and Oren Patashni
- Introduction to Probability, 2/e, by
Dimitri P. Bertsekas, John N. Tsitsiklis