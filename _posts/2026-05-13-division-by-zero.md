---
layout: post
title: "为什么不希望 0 有逆元"
tags: [math, algebra]
mathjax: true
---

如果 \\(0\\) 有逆元，那么我们可以证明环里的任意元素都等于 \\(0\\)。

假设 \\(0^{-1}\\) 存在。由 \\(0 + 0 = 0\\)，

$$
\begin{alignedat}{2}
0^{-1}\cdot(0 + 0)
  &= 0^{-1} \cdot 0
  \qquad&&\text{因为 }0 + 0 = 0 \\
0^{-1}\cdot 0 + 0^{-1}\cdot 0
  &= 0^{-1}\cdot 0
  \qquad&&\text{分配律} \\
1 + 1
  &= 1
  \qquad&&\text{因为 }0^{-1}\cdot 0 = 1 \\
1
  &= 0
  \qquad&&\text{两边同时减去 1}
\end{alignedat}
$$

所以对任意 \\(x \in R\\)，

$$
\begin{alignedat}{2}
x
  &= x \cdot 1
  \qquad&&\text{因为 }1\text{ 是乘法单位元} \\
  &= x \cdot 0
  \qquad&&\text{因为 }1 = 0 \\
  &= 0
  \qquad&&\text{因为任意元素乘 }0\text{ 都等于 }0.
\end{alignedat}
$$
