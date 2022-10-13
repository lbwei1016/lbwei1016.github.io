---
layout: page
title: Solving Recurrences I
usemathjax: true
tag: Concrete Mathematics, Recurrence
time: 2022/08/21
---

> *Solve* 指的是解出 *closed form*。<br>
> 本系列討論僅止於 *linear recurrences*。

> *The point of a closed form is not necessarily to provide us with a fast method of calculation, but rather to tell us how $$F_n$$ relates to other quantities in mathematics.* -- [CMath]

**Table of Content**
- [The Repertoire Method](#the-repertoire-method)
  - [Example $$\rm I$$:](#example-rm-i)
  - [Example $$\rm II$$:](#example-rm-ii)
  - [Example $$\rm III$$:](#example-rm-iii)
  - [Example $$\rm IV$$:](#example-rm-iv)
  - [Reflection](#reflection)
- [Reference](#reference)

---

> **First-Order Recurrences** <br>
> 形式：$$a_n = Ca_{n-1} + f(n)$$ <br>
> 若 $$f(n) = 0$$，則稱為 *homogeneous*。

## The Repertoire Method

> 出自 [CMath]

> *Repertoire (曲目)*: all the music or plays, etc. that you can do or perform or that you know (Cambridge)

*The repertoire method* 的精神是**線性組合**：將欲解的遞迴關係拆解成數個較簡單、類似的遞迴關係（這些便構成了曲目――**repertoire**），再利用線性組合將曲目中較簡單的遞迴關係，組合成原遞迴。先看基本想法：

$$\begin{eqnarray}
f_1 &=& a_1 \\
f_n &=& a_n + f_{n-1}
\end{eqnarray}$$

和

$$\begin{eqnarray}
g_1 &=& b_1 \\
g_n &=& b_n + g_{n-1}
\end{eqnarray}$$

是兩組遞迴關係。如果把他們線性組合在一起：令

$$h_n = \alpha f_n + \beta g_n$$

則

$$\begin{eqnarray}
h_1 &=& \alpha f_1 + \beta g_1 \\
h_n &=& \alpha(a_n + f_{n-1}) + \beta(b_n + g_{n-1}) \\
&=& \alpha a_n + \beta b_n + h_{n-1} \\ 
&=& c_n + h_{n-1}
\end{eqnarray}$$

總而言之，因為以上三種遞迴關係有著相同的結構（$$\mathcal{F_n} = a_n + \mathcal{F_{n-1}}$$），利用線性組合便可以相互轉換。於是複雜的遞迴關係（$$h_n$$）可以由簡單的（$$f_n, g_n$$）得出，而 $$f_n, g_n$$ 就是 $$h_n$$ 的 **repertoire**。

---

### Example $$\rm I$$:

$$\begin{eqnarray}
h_0 &=& 7 \tag{1} \\ 
h_n &=& 3n^2 + 5 + h_{n-1} \tag{2}
\end{eqnarray}$$

首先觀察到遞迴關係的結構：$$\mathcal{F_n} = a_n + \mathcal{F_{n-1}}$$；我們的任務便是建立一同樣具備該結構的 **repertoire**。

在 $$(2)$$ 中，除了 $$h_n$$ 本身外，有 $$3n^2$$ 和 $$5$$ 項；這兩項就是建構 *repertoire* 的依據。接下來的目標是找出：$$f_n$$ and $$g_n$$ s.t. $$a_n = f_n - f_{n-1} = \alpha n^2$$ and $$b_n = g_n - g_{n-1} = \beta$$（來自 $$3n^2$$ 和 $$5$$）。

仔細一想，$$n^3 - (n-1)^3$$ 可以有效地產出 $$n^2$$ 項；$$n - (n-1)$$ 則可以產出常數項。於是我們可以令

$$\begin{eqnarray}
f_n &=& n^3,\ a_n = 3n^2 - 3n + 1 \\
g_n &=& n,\ b_n = 1
\end{eqnarray}$$

但是，$$a_n$$ 內出現了意外的 $$n$$ 項！我們於是必須擴充 *repertoire*、令

$$ u_n = n^2$$

來吸收多餘的 $$n$$。

整理一下目前所有資訊：

| $$\mathcal{F_n}$$ | $$a_n$$ | which can tackle |
|:-----:            |:-----:  |:-----:           |
| $$f_n = n^3$$ | $$3n^2 - 3n + 1$$ | $$3n^2$$ |
| $$g_n = n$$ | $$1$$ | $$5$$ |
| $$u_n = n^2$$ | $$2n - 1$$ | $$f_n$$ 產生的多餘項 |

開始組合吧！

$$3n^2 + 5 = (3n^2 - 3n + 1) + {3 \over 2}(2n - 1) + {11 \over 2}$$

於是

$$\begin{eqnarray}
h_n &=& f_n + {3 \over 2}u_n + {11 \over 2}g_n + c_0 \\
&=& n^3 + {3 \over 2}n^2 + {11 \over 2}n + 7 \\
\end{eqnarray}$$

（$$c_0 = h_0$$，代入 $$n = 0$$ 可得知。）

完工！

總結一下上述過程：
1. 找出結構（$$\mathcal{F_n} = a_n + \mathcal{F_{n-1}}$$）
2. 建構基本 *repertoire*（guess & try）
3. 擴充 *repertoire*（消除多餘項）
4. 代回原式
5. 代入初始項

---

### Example $$\rm II$$:

$$\begin{eqnarray}
f(1) &=& \alpha \\
f(2n) &=& 2f(n) + \beta \\
f(2n+1) &=& 2f(n) + \gamma
\end{eqnarray}$$

和上一例子相同的想法，但是用不同角度切入（類似逆推）。首先假設

$$f(n) = \alpha A(n) + \beta B(n) + \gamma C(n)$$

其中 $$A(n), B(n), C(n)$$ 是我們的 *repertoire*。

值得注意的是，這裡計算的是 *generalized* 遞迴關係，最後再代入 $$\alpha, \beta, \gamma$$ 即可；在過程中，這三個變數可以幫助我們建構適當的 *repertoire*。首先，令 

$$(\alpha, \beta, \gamma)=(1, 0, 0)$$

也就是 $$f(n) = A(n)$$。於是

$$\begin{eqnarray}
A(n) &=& 1 \\
A(2n) &=& 2A(n) \\
A(2n+1) &=& 2A(n)
\end{eqnarray}$$

所以

$$A(n) = 2^m, n = 2^m + l, 0 \leq l < 2^m$$

> 為什麼可以任意指派值給 $$(\alpha, \beta, \gamma)$$？

> 事實上，$$(\alpha, \beta, \gamma)$$ 的值為何我們並不在意（因為這只是過程），只要能求出符合 $$f(n)$$ 結構的 $$A(n), B(n), C(n)$$ 即可（有無限多組）。令 $$(\alpha, \beta, \gamma)=(1, 0, 0)$$ 可以求出 $$A(n)$$，但是令 $$(\alpha, \beta, \gamma)=(0, 1, 0)$$ 或 $$(0, 0, 1)$$ 無法解出 $$B(n), C(n)$$（因為對應的遞迴關係和 $$f(n)$$ 一樣複雜）。

> 因為沒辦法直接解出 $$B(n), C(n)$$，我們轉而求三者的關係式。

我們接下來利用同樣符合 $$f(n)$$ 結構的幾個函數（但不在 *repertoire* 內）來導出 $$A(n), B(n), C(n)$$ 的關係式。首先令 $$f(n) = f^{\prime}(n) = 1$$，

$$\begin{eqnarray}
1 &=& \alpha \\
1 &=& 2 + \beta \\
1 &=& 2 + \gamma
\end{eqnarray}$$

於是當 $$(\alpha, \beta, \gamma)=(1, -1, -1)$$，$$f^{\prime}(n)$$ 可以由 $$A(n), B(n), C(n)$$ 組成。接著令 $$f(n) = f^{\prime\prime}(n) = n$$，

$$\begin{eqnarray}
1 &=& \alpha \\
2n &=& 2n + \beta \\
2n+1 &=& 2n + \gamma
\end{eqnarray}$$

當 $$(\alpha, \beta, \gamma)=(1, 0, 1)$$，$$f^{\prime\prime}(n)$$ 可以由 $$A(n), B(n), C(n)$$ 組成。統整一下所有關於 $$A(n), B(n), C(n)$$ 的資訊：

$$\begin{eqnarray}
2^m &=& A(2^m + l) \\
1 &=& 1 \times A(n) + (-1) \times B(n) + (-1) \times C(n) \\
n &=& 1 \times A(n) + (0) \times B(n) + (1) \times C(n)
\end{eqnarray}$$

三個未知函數三個方程式！所以

$$\begin{eqnarray}
A(n) &=& 2^m \\
B(n) &=& 2^m - l = 1 \\
C(n) &=& l 
\end{eqnarray}$$

其中 $$n = 2^m + l$$、$$0 \leq l < 2^m$$、$$n \geq 1$$。

現在我們已經解出 *generalized* $$f(n)$$ 了！再代入符合原遞迴關係的常數 $$(\alpha, \beta, \gamma)$$ 即可。

---

### Example $$\rm III$$:
考慮上一範例的推廣：

$$\begin{eqnarray}
f(j) &=& \alpha_j,\ 1 \leq j < d \\
f(dn + j) &=& cf(n) + \beta_j,\ 0 \leq j < d,\ n \geq 1
\end{eqnarray}$$

可以解出

$$f((b_mb_{m-1}...b_1b_0)_d) = (\alpha_{b_m}\beta_{b_{m-1}}...\beta_{b_1}\beta_{b_0})_c \tag{3}$$

（試著展開原遞迴關係就可以得到上述解！）

---

### Example $$\rm IV$$:
比上一個範例更複雜一些：

$$\begin{eqnarray}
g(1) &=& \alpha \\
g(2n + j) &=& 3g(n) + \gamma n + \beta_j,\ j = {0,1},\ n \geq 1
\end{eqnarray}$$

和 [Example $$\rm II$$](#example-rm-ii) 一樣，先令

$$g(n) = \alpha A(n) + \beta_0 B(n) + \beta_1 C(n) + \gamma D(n)$$

利用 [Example $$\rm III$$](#example-rm-iii) 的 $$(3)$$，我們可以解 $$f(n) = \alpha A(n) + \beta_0 B(n) + \beta_1 C(n)$$，也就決定了 $$A(n), B(n), C(n)$$。於是只要再找出 $$D(n)$$ 和其他三者的關係式就可以解出 $$g(n)$$。

令 $$g(n) = n$$，$$(\alpha, \beta_0, \beta_1,  \gamma) = (1, 0, 1, -1)$$。也就是

$$n = A(n) + C(n) - D(n)$$

於是

$$g(n) = (\alpha+\gamma)A(n) + \beta_{0}B(n) + (\beta_1 + \gamma)C(n) - \gamma n$$

再令

$$\begin{eqnarray}
h(n) &=& (\alpha+\gamma)A(n) + \beta_{0}B(n) + (\beta_1 + \gamma)C(n) \\
&=& \alpha^{\prime}A(n) + \beta_{0}^{\prime}B(n) + \beta_{1}^{\prime}C(n) \\

H(n) &=& -\gamma n
\end{eqnarray}$$

這樣就解出 $$g(n) = h(n) + H(n)$$ 了！

> *Note*: $$h(n)$$ 用 [Example $$\rm III$$](#example-rm-iii) 的方法解。

---

### Reflection

從上述例子可以體會 *The repertoire method* 的線性組合精神；也就是說，如果某遞迴關係可以表示成

$$f(n) = \alpha A(n) + \beta B(n) + \gamma C(n)，$$

就可以用 *The repertoire method* 解！

---

## Reference
- [Fun with Recursion and the Repertoire Method](https://www.youtube.com/watch?v=2YW-RqAGskE)
- [StackExchange](https://math.stackexchange.com/questions/1017498/mathematical-explanation-for-the-repertoire-method/1023510#1023510)
- [Dang-Khoa's blog](https://dangkhoasdc.github.io/en/post/2017/12/26/the-repertoire-method/)
- [CMath], Concrete Mathematics: A Foundation for Computer Science, by Ronald Graham, Donald Knuth, and Oren Patashni