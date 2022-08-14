---
layout: page
title: Extended Euclidean Algorithm
usemathjax: true
tag: Number Theory
---

> Given $$ax+by=gcd(a,b)$$, find a solution $$(x,y) = (x_0, y_0)$$.

### Solution:
**Step $$I$$**:

$$a = q_1\color{#5DADE2}{b} + \color{#E74C3C}{r_1}$$<br>
$$\color{#5DADE2}{b} = q_2\color{#E74C3C}{r_1} + \color{#A569BD}{r_2}$$<br>
$$\color{#E74C3C}{r_1} = q_3\color{#A569BD}{r_2} + \color{#17A589}{r_3}$$<br>
$$...$$<br>
$$r_{m-3} = q_{m-1}r_{m-2} + \boldsymbol{gcd(a, b)}$$<br>
$$r_{m-2} = q_m\boldsymbol{gcd(a, b)} + 0$$

**Step $$II$$**:

$$\boldsymbol{gcd(a, b)} = r_{m-3} - q_{m-1}\color{#A569BD}{r_{m-2}}$$<br>
$$\boldsymbol{gcd(a, b)} = r_{m-3} - q_{m-1}\color{#A569BD}{(r_{m-4} - q_{m-2}r_{m-3})}$$<br>
$$...$$<br>
(直到代換出 $$a, b$$)

$$gcd(a,b) = ax_0+by_0 \ ◼$$ 

### e.g.
> Solve $$47x + 21y = gcd(47,21) = 1$$.

**Step $$I$$**:

$$47 = 2\times\color{#5DADE2}{21} + \color{#E74C3C}{5}$$<br>
$$\color{#5DADE2}{21} = 4\times\color{#E74C3C}{5} + \color{#A569BD}{1}$$<br>
$$\color{#E74C3C}{5} = 5\times \color{#A569BD}{1} + \color{#17A589}{0}$$<br>

**Step $$II$$**:

$$\boldsymbol{1} = 21 - 4\times\color{#A569BD}{5}$$<br>
$$\boldsymbol{1} = 21 - 4\times\color{#A569BD}{(47 - 2\times 21)}$$<br>
$$\boldsymbol{1} = 47\times (-4) + 21 \times 9$$

$$(x,y) = (-4,9) \ ◼$$