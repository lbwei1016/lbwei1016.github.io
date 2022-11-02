---
layout: page
title: More on Conditioning
usemathjax: true
tag: Conditional Probability
time: 2022/10/15
---

**Table of Content**
- [Continuous Stuff](#continuous-stuff)
  - [Coditional CDF](#coditional-cdf)
- [Bayes' Rule *revisted*](#bayes-rule-revisted)
- [Conditional Expectation and Variance](#conditional-expectation-and-variance)
  - [Problem](#problem)

---

> 見 [Conditioning](../3-Conditioning)。

## Continuous Stuff

$$
f_{X \vert Y}(x \vert y) = {f_{X,Y}(x,y) \over f_Y(y)}, \\
P(X\in A \vert Y=y) = \int_A f_{X\vert Y}(x \vert y)dx. $$

### Coditional CDF

$$
F_{X|Y}(x|y) = P(X\le x|Y=y) = \int_{-\infty}^x f_{X|Y}(t|y)dt, \\

f_{X|Y}(x|y) = {\partial F_{X|Y}(x|y) \over \partial x}.
$$

> 注意是 under $$Y=y$$！

但是，在 continous r.v. 中，$$P(Y=y)$$ 不是應該要等於 $$0$$ 嗎？的確，$$P(Y=y) = 0$$，不過這裡我們計算的是 r.v. $$X$$，也就是說，我們關注的是**在 $$Y=y$$ 的情況下，$$\forall X \le x$$ 的機率**！也因為這個考量，$$F_{X\vert Y}(x\vert y)$$ 才不寫成 $$P(X\le x, Y=y)/P(Y=y)$$。

---

## Bayes' Rule *revisted*

> 見 [Bayes’ Rule](../1-Introduction#bayes-rule)。

Given a **discrete** r.v. $$K$$ and a **continous** r.v. $$Y$$, the joint probability is

$$
\begin{align*}
&P(K=k, y \le Y \le+\delta) \\
=\ &P(K=k)P(y \le Y \le y+\delta|K=k) \approx p_K(k)f_{Y|K}(y|k)\delta \\
=\ &P(y\le Y \le y+\delta)P(K=k|y\le Y \le y+\delta) \approx f_Y(y)\delta p_{K|Y}(k|y).
\end{align*}
$$

Comparing the right hand side, we have

$$
p_K(k)f_{Y|K}(y|k) = f_Y(y)p_{K|Y}(k|y).
$$

From this equation, we can derive two formulae

$$
\begin{align*}
p_{K|Y}(k|y) = {p_K(k)f_{Y|K}(y|k) \over f_Y(y)}, \tag{1} \\
f_{Y|K}(y|k)  = {f_Y(y)p_{K|Y}(k|y) \over p_K(k)}, \tag{2}
\end{align*}
$$

where 

$$
f_Y(y) = \sum_{k'} p_K(k')f_{Y|K}(y|k'), \\
p_K(k) = \int f_Y(y')p_{K|Y}(k|y')dy'.
$$

> 可以發現，這 sum 和 integral 分別對應到 $$(1)$$ 和 $$(2)$$ 的分子！

> 解 $$(1)、(2)$$ 的時候，先算出分子再解決分母；一項一項慢慢來。

這裡，$$p_K(k)$$ 稱為 *prior probability*（事前機率），指在沒有任何額外資訊下，*the belief on $$K$$*；而 $$p_{K\vert Y}(k\vert y)$$ 稱為 *posterior probability*（事後機率），則是多了 $$Y=y$$ 的資訊。

> 後來發生的事件 $$Y=y$$ 改變了我們對 $$K$$ 的看法。

---

## Conditional Expectation and Variance

### Problem
> A rat in a maze has only two paths to go. If the rat goes right, it will return to the starting point after $$3$$ minutes. If the rat goes left, there is a $$2\over 3$$ chance of returning to the starting point after $$5$$ minutes, and a $$1\over 3$$ chance of exiting the maze after $$2$$ minutes. Find the average time that the rat is in the maze if the probability of the rat going left and right is equal.

**Solution**

Let $$T$$ be the time that the rat is in the maze and 

$$
X = \begin{cases}
    0, &\text{goes right}, \\
    1, &\text{goes left}.
\end{cases}
$$

Then

$$
P(X=0) = P(X=1) = {1\over 2}, \\
E(T|X=0) = 3 + E(T), \\
E(T|X=1) = {2\over 3}(5 + E(T)) + {1\over 3}\cdot 2.
$$

Thus we have

$$
E[E(T|X)] = {1\over 2}(3+E(T)) + {1\over 2}({2\over 3}(5 + E(T)) + {1\over 3}\cdot 2) = E(T), \\
\therefore E(T) = 21.
$$