---
layout: post
title: "拉格朗日乘子法"
tags: [math]
mathjax: true
css:
  - /assets/css/post-toc.css
---

拉格朗日乘子法处理的是带约束条件的极值问题。比如我们想优化一个目标函数，但变量不能随便取，而是必须满足若干个约束表达式等于 0。

一个简单的例子是：我们想让

$$
f(x, y) = x + y
$$

尽量大，但 \\((x, y)\\) 不能在整个平面上随便取，而是必须落在单位圆上：

$$
x^2 + y^2 - 1 = 0
$$

这里 \\(f(x, y)=x+y\\) 是目标函数，\\(x^2 + y^2 - 1\\) 就是约束表达式。

<nav class="post-toc" aria-label="文章目录">
  <div class="post-toc-title">目录</div>
  <a href="#费马引理和约束条件">费马引理和约束条件</a>
  <a href="#拉格朗日函数">拉格朗日函数</a>
  <a href="#算一个例子">算一个例子</a>
</nav>

## 费马引理和约束条件

微积分里有一个很基本的结论：对于一个性质足够好的函数，如果它在内部点取得极值，那么这个极值点的梯度应该为 0。比如函数

$$
f(x, y)
$$

在某个内部点取得极值，那么这个点应该满足：

$$
\frac{\partial f}{\partial x} = 0,\quad
\frac{\partial f}{\partial y} = 0
$$

也就是：

$$
\nabla f = 0
$$

但是一旦有了约束条件，费马引理就不能直接用了。比如我们要在约束表达式

$$
h(x, y) = 0
$$

成立的前提下优化 \\(f(x, y)\\)。如果还是直接按无约束问题去求极值，得到的点很可能根本不满足约束。

## 拉格朗日函数

为了解决这个问题，拉格朗日乘子法引入了拉格朗日函数：

$$
L(x, y, \lambda) = f(x, y) + \lambda h(x, y)
$$

动机有二：

第一，在约束成立的定义域中，\\(L\\) 和原来的目标函数 \\(f\\) 等价。因为满足约束时有：

$$
h(x, y)=0
$$

所以对任意 \\(\lambda\\)，都有：

$$
L(x,y,\lambda)
= f(x,y) + \lambda h(x,y)
= f(x,y)
$$

第二，\\(\nabla L=0\\) 蕴含约束条件 \\(h(x,y)=0\\)。

注意 \\(L\\) 里只有最后一项含有 \\(\lambda\\)：

$$
L(x,y,\lambda)=f(x,y)+{\color{#d73a49}{\lambda h(x,y)}}
$$

所以对 \\(\lambda\\) 求偏导时，直接得到：

$$
\frac{\partial L}{\partial \lambda}=h(x,y)
$$

而 \\(\nabla L=0\\) 的意思是 \\(L\\) 对所有变量的偏导都为 0，当然也包括：

$$
\frac{\partial L}{\partial \lambda}=0
$$

两式合在一起，就得到：

$$
h(x,y)=0
$$

这正是原来的约束条件。因此，\\(\nabla L=0\\) 的解天然满足约束。

所以最后要解的，可以直接写成：

$$
\nabla L(x,y,\lambda)=0
$$

也就是把 \\(x\\)、\\(y\\)、\\(\lambda\\) 都看成变量，分别对它们求偏导：

$$
\begin{cases}
\frac{\partial L}{\partial x}=0 \\
\frac{\partial L}{\partial y}=0 \\
\frac{\partial L}{\partial \lambda}=0
\end{cases}
$$

## 算一个例子

回到一开始的例子。目标函数是：

$$
f(x,y)=x+y
$$

约束表达式是：

$$
h(x,y)=x^2+y^2-1=0
$$

于是拉格朗日函数就是：

$$
L(x,y,\lambda)=x+y+\lambda(x^2+y^2-1)
$$

对 \\(x\\)、\\(y\\)、\\(\lambda\\) 分别求偏导，并令它们等于 0：

$$
\begin{cases}
\frac{\partial L}{\partial x}=1+2\lambda x=0 \\
\frac{\partial L}{\partial y}=1+2\lambda y=0 \\
\frac{\partial L}{\partial \lambda}=x^2+y^2-1=0
\end{cases}
$$

前两个式子相减，得到：

$$
2\lambda(x-y)=0
$$

这里 \\(\lambda\\) 不可能是 0，因为如果 \\(\lambda=0\\)，第一个式子会变成 \\(1=0\\)。所以只能有：

$$
x=y
$$

再代回约束条件：

$$
x^2+y^2=1
$$

得到：

$$
2x^2=1
$$

所以：

$$
x=y=\frac{1}{\sqrt{2}}
$$

或者：

$$
x=y=-\frac{1}{\sqrt{2}}
$$

这两个点都满足约束。代回目标函数 \\(f(x,y)=x+y\\)，一个得到 \\(\sqrt{2}\\)，另一个得到 \\(-\sqrt{2}\\)。所以在单位圆上，\\(x+y\\) 的最大值是：

$$
\sqrt{2}
$$

对应的点是：

$$
\left(\frac{1}{\sqrt{2}},\frac{1}{\sqrt{2}}\right)
$$
