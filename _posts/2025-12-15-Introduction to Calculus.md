---
layout: post
title: 一元函数微积分
subtitle: 
cover-img: 
thumbnail-img: 
share-img: 
tags: [math]
author: Wucz
---

[TOC]

---

# 一、一元函数微积分

## 0. 说明

### 0.1一元函数

“ **一元** ”指的是所研究的函数 **只有一个** 自变量，在更复杂和真实的物理世界及其他科学领域中，一个量往往同时依赖于 **多个** 因素（即多个自变量），这种函数称为 **多元函数**  .处理多元函数的微积分需要引入新的概念和工具，如 **偏导数、方向导数、梯度、多重积分** 等，这些并非当前学习的重点 .

### 0.2 一元函数的记号

一元函数的 **自变量** 一般用 $x$ 表示， **因变量** （更多地称之为 $x$ 的 **函数** ）一般用 $y$ 表示， $x$ 、 $y$ 之间满足 **函数关系** $y = f(x)$ ，也可以直接说 $y(x) = f(x)$ .

以下四种记号 **本质相同** ：
$$
y(x)
\stackrel{\text{简记为}}{=} y
= f(x)
\stackrel{\text{简记为}}{=} f
$$

### 0.3 一元函数的连续性和多阶可导性

在物理问题中，我们所研究的一元函数通常具有良好的数学性质，如 **连续性** 与 **多阶可导性** ：

+ **连续性** 意味着函数图像没有间断或跳跃，这在物理上对应于物理量随时间或空间的 **平滑变化**

+ **多阶可导性** 保证了我们可以讨论物理量的 **变化率** （如速度、加速度等）以及 **更高阶** 的动力学量

+ 大多数经典物理中的函数不仅是连续可导的，甚至是 **解析函数** ，可在其定义域内展开为 **收敛** 的 **幂级数**

+ 这些优良性质为我们使用微积分工具分析物理问题提供了数学基础

---

## 1. 一元函数的极限（Limit）

### 1.1 极限的定义

自由落体运动的下落高度与 $h$ 下落时间 $t$ 成二次函数的关系： $h(t) = \frac{t^2}{2}$ ，可以列出下表：

| 下落时间（s） | 下落高度（m） |
| ------- | ------------ |
| 1.1     | 6.05         |
| 1.01    | 5.1005       |
| 1.001   | 5.010005     |
| 1.0001  | 5.00100005   |
| 1.00001 | 5.0001000005 |

当下落时间 $t$ 趋近于 $1s$ 时，下落高度与 $h$ 趋近于 $5m$ ，可以记为：

$$
\begin{flalign}
&
\lim_{t \to 1s} h(t)
= 5m
\text{（其中 “lim” 是极限英文 “limit” 的缩写）}
&
\end{flalign}
$$

当自变量无限趋近于某个值（ $x \to x_{0}$ ）时，函数随之无限趋近于 **某个有限** 的值（ $y \to y_{0}$ ），用数学语言表示为：

$$
\lim_{x \to x_{0}} y(x) = y_{0}
\: \text{或} \:
\lim_{x \to x_{0}} y(x) = L
\text{（“L”取自英文 “limit” 的首字母）}
$$

称 $y_{0}$ （或 $L$ ）为 $x$ 趋于 $x_{0}$ 时函数的 **极限** .

_补充：极限的严格定义（ $\epsilon - \delta$ 语言）_

$$
\lim_{x \to x_{0}} y(x) = y_{0}
\Leftrightarrow \forall \epsilon > 0 \: , \:  \exists \delta > 0
\: s.t. \: \forall x : 0 < |x - x_0| < \delta
\Rightarrow | y(x) - y_{0} | < \epsilon
$$
其中 $0 < |x - x_0| < \delta$ 称为$x_0$的 **去心邻域** ， $y_{0}$ 是 $x$ 趋于 $x_{0}$ 时函数的极限 .

### 1.2 极限的存在性

#### 1.2.1 单侧极限

+ 左极限：
  $$
  \lim_{x \to (x_0)^-} f(x) = L^-
  $$

+ 右极限：
  $$
  \lim_{x \to (x_0)^+} f(x) = L^+
  $$

_例题1_

使用极限的定义判断下列表达式中的极限是否存在

1. $$
   \begin{flalign}
   &
   \lim_{x \to 0} \frac{1}{x}
   \: \text{极限不存在}
   &
   \end{flalign}
   $$

2. $$
   \begin{flalign}
   &
   \lim_{x \to +\infty} \sqrt x
   \: \text{极限不存在}
   &
   \end{flalign}
   $$

3. $$
   \begin{flalign}
   &
   \lim_{x \to \infty} \sin x
   \: \text{极限不存在}
   &
   \end{flalign}
   $$

| 极限不存在的情况      | 核心特征                                     | 对应例题                                                     |
| :-------------------- | :------------------------------------------- | :----------------------------------------------------------- |
| **1. 左右极限不相等** | 从不同方向趋近，得到不同的有限值或无穷趋势 . | $\lim_{x \to 0} \frac{1}{x}$ ，左极限为 $-\infty$，右极限为 $+\infty$ . |
| **2. 趋于无穷大**     | 函数值的绝对值无限增大，但趋势是单一的 .     | $\lim_{x \to \infty} \sqrt{x} = +\infty$ ，趋势单一地增大 .  |
| **3. 无限振荡**       | 函数值在某个范围内永不停止地振荡 .           | $\lim_{x \to \infty} \sin x$ ，在 $[-1, 1]$ 区间内振荡 .     |

#### 1.2.2 极限的存在性

当左极限 $=$ 右极限 $=$ 常数时， **极限存在** ，即：
$$
\lim_{x \to (x_0)^-} f(x)
= \lim_{x \to (x_0)^+} f(x)
= \lim_{x \to x_0} f(x)
= L
$$

### 1.3 无穷大和无穷小

#### 1.3.1 无穷的定义

无穷大 $\infty$ 不是某一个具体的、巨大的数字，而是一个 “没有边界” 的 **概念** ，包括正无穷大 $+\infty$ 、负无穷大 $-\infty$ .

当一个函数 $f(x)$ 的极限满足 $\lim_{x \to x_0} f(x) = 0$ 时，我们称 $f(x)$ 为当 $x \to x_0$ 时的 **无穷小量** .

例如：
$$
\begin{flalign}
& \lim_{x \to +\infty} \frac{1}{x} = 0 \: , \: \frac{1}{x} \text{ 是 } x \to +\infty \text{ 时的无穷小量} & \\
& \lim_{x \to 0} x = 0 \: , \: x \text{ 是 } x \to 0 \text{ 时的无穷小量} &
\end{flalign}
$$

_例题2_

比较说明下列三个比较无穷数大小的方法的合理性 .

+ 方法a：直接比较
  
  $$
  \begin{flalign}
  & \lim_{x \to +\infty} x^2 = \infty
  \: , \:
  \lim_{x \to +\infty} x^3 = \infty & \\
  
  & \Rightarrow \lim_{x \to +\infty} x^2 = \lim_{x \to +\infty} x^3 & 
  \end{flalign}
  $$
  
+ 方法b：作差比较
  
  $$
  \begin{flalign}
  & \lim_{x \to +\infty} x^3 - \lim_{x \to +\infty} x^2
  = \lim_{x \to +\infty} (x^3 - x^2)
  = \infty & \\ 
  
  & \Rightarrow \lim_{x \to +\infty} x^3 > \lim_{x \to +\infty} x^2 
  \end{flalign}
  $$
  
+ 方法c：作商比较
  
  $$
  \begin{flalign}
  & \lim_{x \to +\infty} \frac{x^2}{x^3}
  = \lim_{x \to +\infty} \frac{1}{x}
  = \frac{1}{+\infty} = 0
  \Rightarrow \lim_{x \to +\infty} x^2 
  \: \text{的阶数低于} \:
  \lim_{x \to +\infty} x^3 & \\
  
  & \lim_{x \to +\infty} \frac{x^3}{x^2}
  =\lim_{x \to +\infty} x = +\infty
  \Rightarrow \lim_{x \to +\infty} x^3
  \: \text{的阶数高于} \:
  \lim_{x \to +\infty} x^2
  \end{flalign}
  $$
  方法a、b都不合理，方法c合理 .
  
  在比较无穷大量的“大小”或增长趋势时，方法a直接根据极限值都为无穷大就认为两者相等，这忽略了无穷大之间可能存在不同阶的增长速度，因此是不合理的 .
  
  方法b试图通过作差来比较，虽然差值的极限为无穷大，但它在实数范围内默认可以对两个无穷大直接进行减法运算，这在数学上缺乏严格性，因此也不合理 .
  
  方法c采用作商比较，通过比值的极限来判定无穷大的阶：若比值为0，则分子是分母的低阶无穷大；若比值为无穷大，则分子是分母的高阶无穷大 .这种方法严格符合数学分析中关于无穷大阶的定义，能够准确区分不同无穷大的增长级别，因此是合理的 .

_*补充：可数无穷与不可数无穷_

+ a. 比较正自然数集 $\mathbb{N}_+ = \{ 1, 2, 3, \cdots \, \cdots \}$ 和正偶数集 $b = \{ 2, 4, 6, \cdots \, \cdots \}$ 的元素个数（基数）.

  $a$和$b$可以存在一个双射：$1 \leftrightarrow 2 \: , \: 2 \leftrightarrow 4 \: , \: 3 \leftrightarrow 6 \: , \: \dots$ ，故 $a$ 和 $b$ 的元素个数相等，记为 $|\mathbb{N}_+| = |b| = \aleph_0$ ，称正自然数集 $\mathbb{N}_+$ 为可数集，其元素个数为可数无穷 .

+ 比较有理数集 $\mathbb{Q}$ 和实数集 $\mathbb{R}$ 的元素个数 .

  有理数集 $\mathbb{Q}$ 和正自然数集 $\mathbb{N}_+$ 存在双射： 
  $$
  \begin{flalign}
  & 1 \leftrightarrow 0 & \\
  
  & 2 \leftrightarrow \frac{1}{1} \: , \:
  3 \leftrightarrow -\frac{1}{1} & \\
  
  & 4 \leftrightarrow \frac{1}{2} \: , \:
  5 \leftrightarrow -\frac{1}{2} \: , \:
  6 \leftrightarrow \frac{2}{1} \: , \:
  7 \leftrightarrow -\frac{2}{1} & \\
  
  & 8 \leftrightarrow \frac{1}{3} \: , \:
  9 \leftrightarrow -\frac{1}{3} \: , \:
  10 \leftrightarrow \frac{2}{3} \: , \:
  11 \leftrightarrow -\frac{2}{3} \: , \:
  12 \leftrightarrow \frac{3}{2} \: , \:
  13 \leftrightarrow -\frac{3}{2} \: , \:
  14 \leftrightarrow \frac{3}{1} \: , \:
  15 \leftrightarrow -\frac{3}{1} & \\
  
  & \dots & 
  \end{flalign}
  $$
   故 $\mathbb{Q}$ 的基数 $|\mathbb{Q}| = \aleph_0$ .
  
  使用反证法证明 $\mathbb{R}$ 的元素个数为不可数无穷：假设 $(0,1)$ 内的实数可以与 $\mathbb{N}$ 建立一一对应，列出所有的实数：
  $$
  \begin{flalign}
  & r_1 = 0.a_{11}a_{12}a_{12}\dots & \\
  & r_2 = 0.a_{21}a_{22}a_{22}\dots & \\
  & r_3 = 0.a_{31}a_{32}a_{32}\dots & \\
  & \dots &
  \end{flalign}
  $$
  构造新实数 $b = 0.b_{11}b_{12}b_{13}\dots$ ，其中：
  $$
  \begin{flalign}
  &
  b_i =
  \begin{cases}
  1 & \text{if } a_{ii} = 0 & \\
  0 & \text{if } a_{ii} \neq 0
  \end{cases}
  &
  \end{flalign}
  $$
  那么这个 $b$ 必然不在集合 $\{ r_1 , r_2 , r_3 , \dots \}$ 内，所以 $(0,1)$ 内的实数与 $\mathbb{N}$ 不存在双射， $\mathbb{R}$ 的元素个数为不可数无穷.可以证明：
  $$
  \begin{flalign}
  &
  |\mathbb{R}|
  = 2^{|\mathbb{N}|}
  = 2^{\aleph_0}
  \stackrel{\text{记为}}{=} \aleph_1
  &
  \end{flalign}
  $$

#### 1.3.2 无穷的阶数

我们用 **阶数** 来描述函数值 **发散** 到无穷的速度快慢 .

当 $x \to \infty$ 时：

| 函数 $f(x)$ | 无穷的阶数 | 大O记号 | 小o记号 |
| ---------- | ----------| ---------- | ---------- |
| $x$ | 1阶无穷大  | $O(x)$ | $o(x^2)$ 、 $o(x^3)$ 等 |
| $x^2$ | 2阶无穷大  | $O(x^2)$ | $o(x^3)$ 等 |
| $x^n$ | n阶无穷大  | $O(x^n)$ | $o(x^{n + 1})$ |
|   | 趋于常数L  | $\lim_{x \to \infty} f(x) = L$ | $L + o(1)$ |

当 $x \to 0$ 时：

| 函数 $f(x)$ | 无穷的阶数  | 大O记号         | 小o记号             |
| ---------- | ---------- | ---------------------- | ----------- |
| $x$       | 1阶无穷小  | $O(x)$                   | $o(1)$     |
| $x^2$     | 2阶无穷小  | $O(x^2)$                 | $o(x)$ 、 $o(1)$ 等|
| $x^n$     | n阶无穷小  | $O(x^n)$                 | $o(x^{n - 1})$ |
|           | 趋于常数L  | $\lim_{x \to 0} f(x) = L$ | $L + o(1)$  |

其中：

+ $O$ ：数量级不超过 $(\leq)$

+ $o$ ：数量级严格小于 $(\lt)$

_例题3_

a.判断下列表达式趋于无穷时的阶数

1. $$
   \begin{flalign}
   &
   3x^3 + 4x^2 + 6 \quad (x \to \infty)
   = 3x^3 + o(x^3)
   = O(x^3)
   &
   \end{flalign}
   $$

2. $$
   \begin{flalign}
   &
   \sqrt{x^3} \quad (x \to \infty)
   = x^{\frac{3}{2}}
   = O(x^{\frac{3}{2}})
   &
   \end{flalign}
   $$

3. $$
   \begin{flalign}
   &
   \frac{1}{\cos x} \quad (x \to 0)
   = 1 + o(1)
   &
   \end{flalign}
   $$

4. $$
   \begin{flalign}
   &
   \frac{1}{\sin x} \quad (x \to 0^+)
   \sim \frac{1}{x} \quad (x \to 0^+)
   \stackrel{\text{令} X = \frac{1}{x}}{=} X \quad (X \to +\infty)
   = X + o(X)
   = O(X)
   &
   \end{flalign}
   $$

5. $$
   \begin{flalign}
   &
   \frac{1}{1 - \cos x} \quad (x \to 0)
   = \frac{1}{1 - (1 - 2\sin^2(\frac{x}{2}))}
   = \frac{1}{2\sin^2(\frac{x}{2})}
   \sim \frac{1}{2(\frac{x}{2})^2}
   = \frac{2}{x^2}
   \stackrel{\text{令} X = \frac{1}{x}}{=} \frac{X^2}{2} \quad (X \to \infty)
   = \frac{X^2}{2} + o(\frac{X^2}{2})
   = O(X^2)
   &
   \end{flalign}
   $$

6. $$
   \begin{flalign}
   &
   \ln x \quad (x \to \infty) = o(x^\alpha) \quad (\forall \alpha > 0)
   &
   \end{flalign}
   $$

b.比较下列表达式中两个无穷的阶数

1. $$
   \begin{flalign}
   & f(x) = x^3 + 3x \: , \: g(x) = 2x^2 & \\
   & lim_{x \to \infty} \frac{f(x)}{g(x)}
   = lim_{x \to \infty} \frac{x^3 + 3x}{2x^2}
   = lim_{x \to \infty} \frac{x}{2} + \frac{3}{2x}
   = O(x) + o(1) & \\
   & \text{当 $x \to \infty$ 时， $x^3 + 3x$ 是比 $2x^2$ 高阶的无穷大} &
   \end{flalign}
   $$

2. $$
   \begin{flalign}
   & f(x) = \ln x \: , \: g(x) = \frac{1}{x} & \\
   & lim_{x \to 0} \frac{f(x)}{g(x)}
   = lim_{x \to 0} x \ln x
   = lim_{u \to \infty} \frac{1}{u} \ln \frac{1}{u}
   = lim_{u \to \infty} \frac{- \ln u}{u}
   = o(1) & \\
   & \text{当 $x \to 0$ 时， $\frac{1}{x}$ 是比 $\ln x$ 高阶的无穷大} &
   \end{flalign}
   $$

### 1.4 极限的运算法则

+ 基本运算

  对于连续函数（见 1.6 节），极限号与连续函数可以交换顺序：
  $$
  \lim_{x \to x_0} f(x) = f(x_0)
  $$

+ 分配律（四则运算）

  若 $\lim_{x \to x_0} f(x) = A \: , \: \lim_{x \to x_0} g(x) = B$ ，则有：
  $$
  \lim_{x \to x_0} [f(x) \pm g(x)] = A \pm B \\
  \lim_{x \to x_0} [f(x) g(x)] = A B \\
  \lim_{x \to x_0} \frac{f(x)}{g(x)} = \frac{A}{B} \quad (B \neq 0)
  $$

+ 结合律
  $$
  \lim_{x \to x_0} f(g(x)) = f(\lim_{x \to x_0} g(x))
  $$

_例题4_

使用极限的运算法则计算下列表达式中极限的值

1. $$
   \begin{flalign}
   &
   \lim_{x \to 2} 2x + 1
   = 1 + \lim_{x \to 2} 2x
   = 1 + 4
   = 5
   &
   \end{flalign}
   $$

2. $$
   \begin{flalign}
   &
   \lim_{x \to \infty} \frac{1}{x + 1}
   = \frac{1}{\infty + 1}
   = 0
   &
   \end{flalign}
   $$

3. $$
   \begin{flalign}
   &
   \lim_{x \to 1} \ln x
   = \ln (\lim_{x \to 1} x)
   = \ln 1
   = 0
   &
   \end{flalign}
   $$

4. $$
   \begin{flalign}
   &
   \lim_{x \to 0} \cos x
   = \cos (\lim_{x \to 0} x)
   = \cos 0
   = 1
   &
   \end{flalign}
   $$

5. $$
   \begin{flalign}
   &
   \lim_{x \to 0} \sin x
   = \sin(\lim_{x \to 0} x)
   = \sin 0
   = 0
   &
   \end{flalign}
   $$

6. $$
   \begin{flalign}
   &
   \lim_{t \to 3} t^2 + 4t -7
   = -7 + \lim_{t \to 3} t^2 + \lim_{t \to 3} 4t
   = -7 + 9 + 12
   = 14
   &
   \end{flalign}
   $$

7. $$
   \begin{flalign}
   &
   \lim_{x \to \infty} \frac{3x}{x + 2}
   = 3
   &
   \end{flalign}
   $$

8. $$
   \begin{flalign}
   &
   \lim_{x \to \infty} \frac{3x^3 + 5x + 6}{x^4} = 0
   &
   \end{flalign}
   $$

9. $$
   \begin{flalign}
   &
   \lim_{x \to \frac{\pi}{2}} \frac{\sin x}{e^x}
   = \frac{\lim_{x \to \frac{\pi}{2}} \sin x}{\lim_{x \to \frac{\pi}{2} e^x}}
   = \frac{1}{e^{\frac{\pi}{2}}}
   &
   \end{flalign}
   $$

### 1.5 重要极限

+ 三角函数\反三角函数
  $$
  \lim_{x \to 0} \frac{\sin x}{x}
  = \lim_{x \to 0} \frac{\tan x}{x} = 1 \\
  
  \lim_{x \to 0} \frac{\arcsin x}{x}
  = \lim_{x \to 0} \frac{\arctan x}{x} = 1\\
  
  \lim_{x \to 0} \frac{1 - \cos x}{x^2} = \frac{1}{2}
  $$

+ 指数函数\对数函数
  $$
  \lim_{x \to 0} \frac{e^x - 1}{x}
  = \lim_{x \to 0} \frac{\ln(x + 1)}{x} = 1 \\
  
  \lim_{x \to +\infty} \frac{\ln(x)}{x^a}
  = \lim_{x \to +\infty} \frac{x^a}{e^x}
  = 0 \quad (a > 0) \\
  
  \lim_{x \to 0} x \ln(x + 1) = 0
  $$

+ ”1“的无穷大次幂\”0“的0次幂

  若 $\lim_{x \to a} f(x) = 1$ 且 $\lim_{x \to a} g(x) = \infty$ ，则 ：
  $$
  \lim_{x \to a} [f(x)]^{g(x)} = e^{\lim_{x \to a} [ (f(x)-1) \cdot g(x) ]}
  $$
  推论：
  $$
  \lim_{x \to 0} (1 + x)^{\frac{1}{x}} = e \\
  \lim_{x \to \infty} (1 + \frac{1}{x})^x = e
  $$

+ 斯特林公式 （Stirling‘s Approximation）
  $$
  \lim_{n \to \infty} \frac{n!}{\sqrt{2\pi n} \left( \frac{n}{e} \right)^n} = 1
  $$

_例题5_

使用重要极限计算下列表达式中极限的值

1. $$
   \begin{flalign}
   &
   \lim_{x \to 0} \frac{\sin(5x)}{x} = 5
   &
   \end{flalign}
   $$

2. $$
   \begin{flalign}
   &
   \lim_{x \to 0} \frac{\tan(3x)}{\sin(7x)} = \frac{3}{7}
   &
   \end{flalign}
   $$

3. $$
   \begin{flalign}
   &
   \lim_{x \to 0} \frac{e^{3x} - 1}{x} = 3
   &
   \end{flalign}
   $$

4. $$
   \begin{flalign}
   &
   \lim_{x \to +\infty} \frac{\ln(x)}{\sqrt{x}} = 0
   &
   \end{flalign}
   $$

5. $$
   \begin{flalign}
   &
   \lim_{x \to 0} x^2 \ln(1 + \frac{1}{x}) = 0
   &
   \end{flalign}
   $$
   
6. $$
   \begin{flalign}
   &
   \lim_{x \to \infty} (1 + \frac{2}{x})^x = e^2
   &
   \end{flalign}
   $$

7. $$
   \begin{flalign}
   &
   \lim_{x \to 0} (\cos x)^{\frac{1}{x^2}} \quad \text{（提示：利用 $1 - \cos x \sim \frac{1}{2}x^2$）} = e^{-\frac{1}{2}}
   &
   \end{flalign}
   $$

8. $$
   \begin{flalign}
   &
   \lim_{n \to \infty} \frac{\sqrt[n]{n!}}{n} = \frac{1}{e}
   &
   \end{flalign}
   $$

### 1.6 一元函数的连续性

有一个容易被忽略的事实：
$$
\begin{flalign}
&
\lim_{x \to x_0} y(x)
= y_0
\stackrel{\text{不一定}}{=} y(x_0)
&
\end{flalign}
$$

_例题6_

求分段函数 

$$
\begin{flalign}
&
f(x) = 
\begin{cases}
0, & x < 0 \\
1, & x \geq 0
\end{cases}
&
\end{flalign}
$$

在 $x_0 = 0$ 处的左、右极限以及函数值 $f(x_0)$ .
$$
\begin{flalign}
& \lim_{x \to x_0^-} f(x) = \lim_{x \to 0^-} f(x) = 0 & \\
& \lim_{x \to x_0^+} f(x) = \lim_{x \to 0^+} f(x) = 1 & \\
& f(x_0) = 1 = \lim_{x \to 0^+} f(x) \neq \lim_{x \to 0^-} f(x) = 0 & \\
& \text{左右极限不相等，所以 $x = x_0 =0$ 处极限不存在} &
\end{flalign}
$$
当函数 $y = f(x)$ 在 $x_0$ 处极限 $\lim_{x \to x_0} f(x) = L$ 存在且 $L = f(x_0)$ 时，称函数 $f(x)$ 在 $x_0$ 处 **连续** .

如果函数 $y = f(x)$ 在开区间 $(a, b)$ 内的每一点都连续，则称该函数在开区间 $(a, b)$ 上连续 .

如果函数 $y=f(x)$ 在开区间 $(a,b)$ 内连续，且在左端点 $a$ 处右连续，在右端点 $b$ 左连续，则称该函数在闭区间 $[a, b]$ 上连续 .

### *1.7 夹逼定理

在包含 $x_0$ 的某个区间里，如果对任意的 $x$ 都有 $g(x) \leq f(x) \leq h(x)$ ，那么 $\lim_{x \to x_{0}} g(x) \leq \lim_{x \to x_{0}} f(x) \leq \lim_{x \to x_{0}} h(x)$ ，如果又有 $\lim_{x \to x_{0}} g(x) = \lim_{x \to x_{0}} h(x) = L$ ，那么 $\lim_{x \to x_{0}} f(x) = L$ .

_例题7_

使用夹逼定理计算下列表达式中极限的值

1. $$
   \begin{flalign}
   &
   \lim_{x \to 0^+} x \sin(\frac{1}{x}) = 0 
   \Leftarrow 0 \leq \lim_{x \to 0^+} x \sin(\frac{1}{x}) \leq \lim_{x \to 0^+} x = 0 
   \Leftarrow 0 \leq sin(\frac{1}{x}) \leq 1
   &
   \end{flalign}
   $$

2. $$
   \begin{flalign}
   &
   lim_{x \to +\infty} \sqrt[x]{2^x + 3^x} = 3
   \Leftarrow 3 = lim_{x \to +\infty} \sqrt[x]{3^x}
   \leq lim_{x \to +\infty} \sqrt[x]{2^x + 3^x} = 3
   \leq lim_{x \to +\infty} \sqrt[x]{3^x + 3^x} = 3
   &
   \end{flalign}
   $$

### *1.8 洛必达法则

当 $\lim_{x \to x_0} f(x)$ 和 $\lim_{x \to x_0} g(x)$ 同时趋近于 $0$ 或 $\infty$ 且 $g'(x_0)$ 和 $g'(x_0)$ 都存在且 $g'(x_0) \neq 0$ 时，有：
$$
\lim_{x \to x_0} \frac{f(x)}{g(x)} = \lim_{x \to x_0} \frac{f'(x)}{g'(x)}
$$
_*例题8_

计算下列表达式中极限的值

1. $$
   \begin{flalign}
   &
   \lim_{x \to 0} \frac{e^x - x - 1}{x^2}
   = \lim_{x \to 0} \frac{e^x - 1}{2x}
   = \lim_{x \to 0} \frac{e^x}{2}
   = \frac{1}{2}
   &
   \end{flalign}
   $$

2. $$
   \begin{flalign}
   &
   \lim_{x \to 1} (\frac{\ln x}{1 - x})
   = \lim_{x \to 1} \frac{\frac{1}{x}}{-1}
   = -1
   &
   \end{flalign}
   $$

---

## 2. 一元函数的微分（Differential）

### 2.1 变量的变化量和微分

变化量 = 末状态 - 初状态 ：
$$
\Delta \delta = \delta^* - \delta
$$
自变量的变化量：

$$
\begin{flalign}
& \Delta x = x^* - x & \\
& \Delta t = t^* - t & \\
\end{flalign}
$$

函数的变化量：
$$
\begin{flalign}
& \Delta y = y^* - y & \\
& \Delta y(x) = y^*(x) - y(x) = y(x + \Delta x) - y(x) & \\
& \Delta x(t) = x^*(t) - x(t) = x(t + \Delta t) - x(t) &
\end{flalign}
$$

### 2.2 变量的微分

当末状态无限接近初状态（变量 $\delta$ 的变化量 $\Delta \delta$ 趋于无穷小， $\Delta \delta \to 0$ ）时，称变量的微小变化量 $\Delta \delta$ 为变量的 **微分** ，记为 $d\delta$ ， $d$ 被称为 **外微分算子** ，表示“微小的变化量”，用数学语言表示为：

$$
\lim_{\delta^* \to \delta} \Delta \delta = d\delta 
$$

自变量的微分：

$$
\lim_{x^* \to x} \Delta x = dx
$$

函数的微分：
$$
\lim_{x^* \to x} \Delta y
= \lim_{x^* \to x} \Delta y(x)
= \lim_{x^* \to x} y(x^*) - y(x) 
= \lim_{\Delta x \to 0} y(x + \Delta x) - y(x)
= y(x + dx) - y
= dy
$$
_例题9_

求函数 $y = x^2 -2$ 在 $x = 2$ 处，当自变量 $x$ 的变化量 $\Delta x = +0.01$ 时的函数值 $y$ 的变化量 $\Delta y$ .

_例题10_

仿照示例表示下列变量的变化量和微分，并说出其物理意义

1. $S = \pi r^2$

   变化量：
   $$
   \begin{flalign}
   &
   \Delta S 
   = \Delta(\pi r^2)
   = (\pi r^2)^* - \pi r^2
   = \pi (r^*)^2 - \pi r^2
   = \pi (r + \Delta r)^2 - \pi r^2
   &
   \end{flalign}
   $$
   微分：
   $$
   \begin{flalign}
   &
   dS
   = d(\pi r^2)
   = \lim_{\Delta r \to 0} \pi (r + \Delta r)^2 - \pi r^2 
   = \lim_{\Delta r \to 0} \pi (2r + \Delta r)\Delta r 
   = \lim_{\Delta r \to 0} 2\pi r\Delta r
   = 2\pi r dr
   &
   \end{flalign}
   $$
   表示圆面积的微小变化
   
2. $\sin \theta$

   变化量：
   $$
   \begin{flalign}
   &
   \Delta \sin \theta 
   =(\sin \theta)^* - \sin \theta
   = \sin(\theta^*) - \sin \theta
   =\sin (\theta + \Delta \theta) - \sin \theta
   &
   \end{flalign}
   $$
   微分：
   $$
   \begin{flalign}
   &
   d(\sin \theta)
   = \lim_{\Delta \theta \to 0} \sin (\theta + \Delta \theta) - \sin \theta
   = \lim_{\Delta \theta \to 0} \sin \theta cos \Delta \theta + \cos \theta \sin \Delta \theta - \sin \theta
   = \lim_{\Delta \theta \to 0} \cos \theta \sin \Delta \theta
   = \cos \theta d\theta
   &
   \end{flalign}
   $$
   表示正弦值的微小变化
   
3. $\cos \theta$

   变化量：
   $$
   \begin{flalign}
   &
   \Delta \cos \theta
   = (\cos \theta)^* - \cos \theta
   = \cos(\theta^*) - \cos \theta
   = \cos (\theta + \Delta \theta) - \cos \theta
   &
   \end{flalign}
   $$
   微分：
   $$
   \begin{flalign}
   &
   d(\cos \theta)
   = \lim_{\Delta \theta \to 0} \cos (\theta + \Delta \theta) - \cos \theta
   = \lim_{\Delta \theta \to 0} \cos \theta cos \Delta \theta - \sin \theta \sin \Delta \theta - \cos \theta
   = \lim_{\Delta \theta \to 0} -\sin \theta \sin \Delta \theta
   = -\sin \theta d\theta
   &
   \end{flalign}
   $$
   表示余弦值的微小变化
   
4. $a + b$

   变化量：
   $$
   \begin{flalign}
   &
   \Delta (a + b)
   = (a + b)^* - (a + b)
   = (a^* + b^*) - (a + b)
   = (a^* - a) + (b^* - b)
   = \Delta a + \Delta b
   &
   \end{flalign}
   $$
   微分：
   $$
   \begin{flalign}
   &
   d(a + b)
   = \lim_{\Delta a \to 0 , \Delta b \to 0} \Delta a + \Delta b
   = \lim_{\Delta a \to 0} \Delta a + \lim_{\Delta b \to 0} \Delta b
   = da + db
   &
   \end{flalign}
   $$
   表示两个变量和的微小变化
   
5. $ab$

   变化量：
   $$
   \begin{flalign}
   &
   \Delta (ab)
   = (ab)^* - ab
   = a^*b^* - ab
   = (a + \Delta a)(b + \Delta b) - ab
   = ab + a \Delta b + b \Delta a +\Delta a \Delta b - ab
   = a \Delta b + b \Delta a +\Delta a \Delta b
   &
   \end{flalign}
   $$
   微分：
   $$
   \begin{flalign}
   &
   d(ab)
   = \lim_{\Delta a \to 0 , \Delta b \to 0} a \Delta b + b \Delta a +\Delta a \Delta b
   = \lim_{\Delta a \to 0 , \Delta b \to 0} a \Delta b + b \Delta a
   = \lim_{\Delta b \to 0} a \Delta b + \lim_{\Delta a \to 0} b \Delta a
   = adb + bda
   &
   \end{flalign}
   $$
   表示两个变量乘积的微小变化
   
6. $\frac{u}{v}$

   变化量：
   $$
   \begin{flalign}
   &
   \Delta(\frac{u}{v})
   = (\frac{u}{v})^* - \frac{u}{v}
   = \frac{u^*}{v^*} - \frac{u}{v}
   = \frac{u + \Delta u}{v + \Delta v} - \frac{u}{v}
   = \frac{v(u + \Delta u) - u(v + \Delta v)}{v(v + \Delta v)}
   = \frac{v \Delta u - u \Delta v}{v(v + \Delta v)}
   &
   \end{flalign}
   $$
   微分：
   $$
   \begin{flalign}
   &
   d(\frac{u}{v})
   = \lim_{\Delta u \to 0, \Delta v \to 0} \frac{v \Delta u - u \Delta v}{v(v + \Delta v)}
   = \frac{v du - u dv}{v^2}
   &
   \end{flalign}
   $$
   表示两个变量商的微小变化

7. $f(g)$

   变化量：
   $$
   \begin{flalign}
   &
   \Delta f(g)
   = f(g)^* - f(g)
   = f(g^*) - f(g)
   = f(g + \Delta g) - f(g)
   = f(g(x) + \Delta g(x)) - f(g(x))
   = f(g(x + \Delta x)) - f(g(x))
   &
   \end{flalign}
   $$
   微分：
   $$
   \begin{flalign}
   df(g)
   & = \lim_{\Delta x \to 0} f(g(x + \Delta x)) - f(g(x)) & \\
   & = \lim_{\Delta x \to 0} \frac{f(g(x + \Delta x)) - f(g(x))}{\Delta g(x)}\Delta g(x) & \\
   & = \lim_{\Delta x \to 0 , \Delta g(x) \to 0} \frac{f(g + \Delta g) - f(g)}{\Delta g(x)}\Delta g(x) & \\
   & = \frac{df}{dg} dg &
   \end{flalign}
   $$
   表示复合函数值的微小变化

_例题11_

计算下列含微分的表达式的值

1. $$
   \begin{flalign}
   &
   \frac{0}{dx} = 0
   &
   \end{flalign}
   $$

2. $$
   \begin{flalign}
   &
   e^{1+ dx} \approx e
   &
   \end{flalign}
   $$

3. $$
   \begin{flalign}
   &
   \sin dx \approx dx
   &
   \end{flalign}
   $$

4. $$
   \begin{flalign}
   &
   \cos dx \approx 1
   &
   \end{flalign}
   $$

5. $$
   \begin{flalign}
   &
   d(2x) = 2dx
   &
   \end{flalign}
   $$

6. $$
   \begin{flalign}
   &
   d(x^2) = 2x dx
   &
   \end{flalign}
   $$

7. $$
   \begin{flalign}
   &
   d\cos x = -\sin x dx
   &
   \end{flalign}
   $$

8. $$
   \begin{flalign}
   &
   d\sin x = \cos x dx
   &
   \end{flalign}
   $$

9. $$
   \begin{flalign}
   &
   \frac{d(3x)}{d(4x)} = \frac{3}{4}
   &
   \end{flalign}
   $$

10. $$
    \begin{flalign}
    &
    \frac{d(x^3)}{dx} = 3x^2
    &
    \end{flalign}
    $$

11. $$
    \begin{flalign}
    &
    \frac{d\sqrt x}{dx} = \frac{1}{2\sqrt{x}}
    &
    \end{flalign}
    $$


### *2.3 一元函数的可微性

#### 2.3.1 可微的定义

设函数 $y = f(x)$ 在点 $x_0$ 的某个邻域内有定义，如果自变量在点 $x_0$ 处的变化量 $\Delta x$ 所引起的函数变化量 $\Delta y$ 可以表示为：
$$
\Delta y = A \Delta x + o(\Delta x)
$$
其中 $A \Delta x$ 是称为 $ \Delta x $ 的 **线性主部** ， $A$ 是一个与 $ \Delta x $ 无关的常数，$ o(\Delta x) $ 是当 $ \Delta x \to 0 $ 时比 $ \Delta x $ 更高阶的无穷小，那么就称函数 $f(x)$ 在点 $x_0$ 处 **可微** .

如果函数 $y = f(x)$ 在开区间 $(a, b)$ 内的每一点都可微，则称该函数在开区间 $(a, b)$ 上可微 .

#### 2.3.2 可微的几何意义

函数 $y = f(x)$ 在点 $ (x_0, f(x_0)) $ 处可微，在几何上意味着函数的图像在该点附近可以用一条直线进行“良好”的近似，这条直线就是该点的 **切线** .

因此，用微分 $dy$ 来近似代替变化量 $\Delta y$，就是在点 $x_0$ 的附近，用切线的线性变化来近似代替曲线的实际变化.它们之间的误差 $ \Delta y - dy $ 就是图中切线与曲线在竖直方向上的差距，它是一个比 $ \Delta x $ 更高阶的无穷小量 $ o(\Delta x) $ ，所以有：
$$
dy = A dx
$$
可微性是函数的一种 **光滑性描述** . 一个函数在某点可微，意味着它在该点附近的变化可以被一个线性函数（切线）很好地近似 .

### 2.4 微分在物理中的应用

#### 2.4.1 微分的物理意义

微分在物理学中更多的被称为 **微元** ，表示 **物理量的微小变化量** . 当我们需要研究某个物理量在极短时间、极小空间范围内的变化时，微元提供了精确的数学描述 .

+ 时间微元：$dt$ 表示时间的微小间隔
+ 空间微元：$dx, dy, dz$ 表示空间位置的微小位移
+ 物理量微元：$dm, dV, dQ$ 等分别表示质量、体积、电荷等的微小变化

这些微元的物理意义在于它们描述了物理系统在 **局部** 、 **瞬时** 的状态变化，是构建物理定律的基本元素 .

#### 2.4.2 力学

+ 质点位移的微元

  在研究质点运动时，质点在极短时间内位置的变化量为：
  $$d\vec{r} = \vec{r}(t+dt) - \vec{r}(t)$$
  其中 $d\vec{r}$ 是位置矢量的微分，表示质点的 **无限小位移** .

+ 质量微元

  对于连续物体，可以将其划分为无数个质量微元：
  $$dm = \rho(\vec{r}) dV$$
  其中 $\rho(\vec{r})$ 是密度函数，$dV$ 是体积微元

+ 动量微元与冲量微元

  质点的动量微元为：
  $$d\vec{p} = \vec{v} dm$$
  对于系统而言，总动量是各动量微元的矢量和

  力的冲量微元为：
  $$d\vec{I} = \vec{F} dt$$
  这表示力在极短时间内产生的动量变化

+ 功的微元

  力 $\vec{F}$ 在微小位移 $d\vec{r}$ 上所做的元功为：
  $$dW = \vec{F} \cdot d\vec{r}$$

+ 转动惯量的微元

  对于一个刚体，绕某轴的转动惯量可以表示为：
  $$dI = r_\perp^2 dm$$
  其中 $r_\perp$ 是质量微元 $dm$ 到转轴的垂直距离

例题

1. （托里拆利定律）用微元法证明理想流体从容器底部微小开口流出时的流速与液面高度之间的关系满足：$v = \sqrt{2gh}$ .
   $$
   \begin{flalign}
   & \text{设 $dt$ 时间内从开口流出质量为 $dm$ 的液体，速度为 $v$ ，液面的下降速度为 $v_0$}& \\
   & \text{开口的距离液面高度为 $h$ ，重力势能的变化量为 $dE_p$ ，动能的变化量为 $dE_k$} & \\
   & S_\text{开口} \ll S_\text{液面} \Rightarrow v_0 \ll v & \\
   & dE_p = dm g h & \\
   & dE_k = dm \frac{v^2 - v_0^2}{2} \approx dm \frac{v^2}{2} & \\
   & \text{由能量守恒：}dE_p = dE_k & \\
   & \text{联立解得：}v = \sqrt{2gh} & \\
   \end{flalign}
   $$

2. （2020年复旦大字）一质量为 $m$ ,长为 $L$ 的柔软绳自由悬垂,下端恰与一台秤的秤盘接触 . 某时刻放开柔软绳上端, 则台秤的最大读数为？
   $$
   \begin{flalign}
   & \text{设已经落在台秤上的软绳质量为 $m'$ ，此时绳子的下落速度为 $v$ ， $dt$ 时间内有质量为 $dm$ 的绳子落在台秤上，对台秤的冲击力为 $F$} & \\
   & \text{由牛顿第三定律：} N = m'g + F & \\
   & \text{由冲量定理：} Fdt = dm \Delta v = dm v & \\
   & \text{等式两边除以 $dt$ 得：} F
   = \frac{dm}{dt} v
   = \frac{\sigma dl}{dt} v
   = \sigma v^2
   = \frac{m}{L} v^2 & \\
   & N_{max} = m'_{max}g + \frac{m}{L} v_{max}^2
   = mg + \frac{m}{L} 2gL
   = 3mg &
   \end{flalign}
   $$

3. （万有引力推论）证明匀质薄球壳在其内部任一点产生的万有引力为 $0$ .
   $$
   \begin{flalign}
   & \text{设球壳的质量为 $M$ ，半径为 $R$ ，其中有一点 $P$ ，距离球心 $O$ 为 $r,r<R$} & \\
   & \text{任取一条过 $P$ 点的弦 $AB$ ， $A$ 、 $B$ 在球壳上， $\angle OAB$ 记为 $\alpha_1$ ， $\angle OBA$ 记为 $\alpha_2$ ， $AP$ 记为 $l_1$ ， $BP$ 记为 $l_2$} & \\
   & \text{由对称性：} \alpha_1 = \alpha_2 = \alpha & \\
   & \text{在 $P$ 两侧分别以 $PA$ 、 $PB$ 为轴，取大小相等的立体角微元 $d\Omega$ ，立体角与球面截得两个面元 $dS_1$ 和 $dS_2$} & \\
   & \text{由立体角定义：} dS_1 = \frac{l_1^2}{\cos\alpha} d\Omega , dS_2 = \frac{l_2^2}{\cos\alpha} d\Omega & \\
   & \text{由万有引力定律：} dF_1 = G \frac{dm_1}{l_1^2} = G \frac{\sigma dS_1}{l_1^2} = \frac{G \sigma}{\cos\alpha} d\Omega = dF_2 & \\
   & \text{任意选取的两侧面元所产生的万有引力都可抵消，故整个球壳在 $P$ 点产生的万有引力为 $0$} &
   \end{flalign}
   $$

4. 一个匀质环形橡皮筋套在一个光滑的竖直圆锥上并保持水平静止，圆锥的锥角为 $2 \theta $ ，计算橡皮筋上的张力 $T$ .
   $$
   \begin{flalign}
   & \text{任取一段 $dl$ 长度的橡皮筋，它受到两个大小相等方向相反的水平张力 $T$ ,但是两个张力的夹角并不是严格的 $180^\circ$ ，而是 $180^\circ - d\theta$} & \\
   & \text{$d\theta$ 是 $dl$ 对圆锥轴线所张的角，即 $\frac{dl}{r}$ ， $r$ 是橡皮筋的半径} & \\
   & \text{所以两个张力的合力指向圆锥轴线，大小为： $T_\Sigma = 2 T \sin \frac{d\theta}{2}$} = 2 T \frac{d\theta}{2} = T d\theta & \\
   & \text{对这一小段橡皮筋的受力正交分解，得：} T_\Sigma \sin \theta = dm g \cos \theta & \\
   & T d\theta \sin \theta
   = \sigma g dl \cos \theta
   = \frac{mg}{2 \pi r} dl \cos \theta & \\
   & T
   = \frac{mg}{2 \pi r} \frac{dl}{d\theta} \frac{\cos \theta}{\sin \theta}
   = \frac{mg}{2 \pi} \frac{1}{\tan \theta} &
   \end{flalign}
   $$

#### 2.4.3 物理学其他分支

##### 2.4.3.1  流体力学中的微元

质量守恒：流体微元的质量 $dm$ 变化满足连续性方程 $\dot m = \rho A v$
流量微元：通过面积微元 $d\vec{A}$ 的流量为 $d\Phi = \vec{v} \cdot d\vec{A}$

##### 2.4.3.2  电磁学中的微元

电荷微元：$dq = \rho dV$，其中 $\rho$ 是电荷密度
电流微元：$dI = \vec{J} \cdot d\vec{A}$，其中 $\vec{J}$ 是电流密度

电场强度的计算中，点电荷产生的电场：
$$d\vec{E} = \frac{1}{4\pi\varepsilon_0} \frac{dq}{r^2} \hat{r}$$

磁感应强度的计算中，电流元产生的磁场（毕奥-萨伐尔定律）：
$$d\vec{B} = \frac{\mu_0}{4\pi} \frac{I d\vec{l} \times \hat{r}}{r^2}$$

##### 2.4.3.3 热力学中的微元

热量微元：$dQ$ 表示系统吸收或放出的微小热量
功微元：$dW$ 表示系统对外做的微小功
内能微元：$dU$ 表示内能的微小变化

热力学第一定律的微分形式：
$$dU = dQ - dW$$

熵的微元：对于可逆过程，$dS = \frac{dQ}{T}$，其中 $T$ 是绝对温度 .

#### *2.4.4 误差分析

微分在误差分析中用于估计测量误差的传播 . 当一个物理量 $y$ 是其他测量量 $x_1, x_2, \cdots, x_n$ 的函数时：
$$y = f(x_1, x_2, \cdots, x_n)$$

各测量量的误差 $dx_1, dx_2, \cdots, dx_n$ 将导致 $y$ 的误差为：
$$dy = \frac{\partial f}{\partial x_1} dx_1 + \frac{\partial f}{\partial x_2} dx_2 + \cdots + \frac{\partial f}{\partial x_n} dx_n$$

例如：

1. 圆柱体积的误差
   圆柱体积 $V = \pi r^2 h$，半径和高度的测量误差分别为 $dr$ 和 $dh$，则体积的误差为：
   $$dV = 2\pi rh dr + \pi r^2 dh$$
   相对误差为：
   $$\frac{dV}{V} = 2\frac{dr}{r} + \frac{dh}{h}$$

2. 单摆周期的误差
   单摆周期 $T = 2\pi\sqrt{\frac{l}{g}}$，长度和重力加速度的测量误差分别为 $dl$ 和 $dg$，则周期的误差为：
   $$dT = \pi\left(\frac{1}{\sqrt{lg}} dl - \frac{\sqrt{l}}{g^{3/2}} dg\right)$$

3. 电阻并联的误差
   两个电阻并联：$R = \frac{R_1 R_2}{R_1 + R_2}$，各电阻的误差为 $dR_1$ 和 $dR_2$，则总电阻的误差为：
   $$dR = \frac{R_2^2}{(R_1 + R_2)^2} dR_1 + \frac{R_1^2}{(R_1 + R_2)^2} dR_2$$

通过微分进行误差分析，可以评估各测量量误差对最终结果的影响程度，为实验设计和仪器选择提供依据.

---

## 3. 一元函数的导数（Derivative）

### 3.1 导数的定义（微商）

当自变量 $x$ 在某一个小范围 $[x_0, x_0 + dx]$ 内变化时，将因变量的微分 $dy$ 和自变量的微分 $dx$ 相除的商 $\frac{dy}{dx}$ 如果存在，则将其称为 **导数** （或  **微商** ），用数学语言表示为：

$$
\lim_{x = x_0, dx \to 0} \frac{dy}{dx}
\stackrel{\text{记为}}{=} \frac{dy}{dx} |_{x=x_0}
= \lim_{dx \to 0} \frac{y(x_0 + dx) - y(x_0)}{(x_0 + dx) - x_0}
= \lim_{dx \to 0} \frac{f(x_0 + dx) - f(x_0)}{(x_0 + dx) - x_0}
= \lim_{dx \to 0} \frac{f(x_0 + dx) - f(x_0)}{dx}
\stackrel{\text{记为}}{=} f'(x_0)
$$

表示在 $x_0$ 点处， $y$ 相对于 $x$ 的 **瞬时变化速率** .

例如：

求自由落体运动中第 $1s$ 末时下落的速度：
$$
\begin{flalign}
& v_1 = \lim_{t = 1 , dt \to 0} \frac{dh}{dt}
= \lim_{dt \to 0} \frac{h(1 + dt) - h(1)}{(1 + dt) - 1}
= \lim_{dt \to 0} \frac{h(1 + dt) - h(1)}{dt}
\stackrel{\text{记为}}{=} h'(1)
&
\end{flalign}
$$

_例题12_

仿照示例计算下面几个导数的值

1. $$
   \begin{flalign}
   &
   \lim_{x_0 = 1 , dx \to 0} \frac{dC}{dx}
   = \lim_{dx \to 0} \frac{C - C}{dx}
   = \lim_{dx \to 0} \frac{0}{dx} = 0
   &
   \end{flalign}
   $$

2. $$
   \begin{flalign}
   &
   \lim_{x_0 = 2 , dx \to 0} \frac{d(kx + b)}{dx}
   = \lim_{dx \to 0} \frac{(k(2 + dx) + b)-(2k + b)}{dx}
   = \lim_{dx \to 0} \frac{kdx}{dx}
   = lim_{dx \to 0} k
   = k
   &
   \end{flalign}
   $$

3. $$
   \begin{flalign}
   &
   \lim_{x_0 = 3 , dx \to 0} \frac{d(x^2)}{dx}
   = \lim_{dx \to 0} \frac{(3 + dx)^2 - 3^2}{dx}
   = \lim_{dx \to 0} \frac{9 + 6dx + dx^2 - 9}{dx}
   = \lim_{dx \to 0} \frac{6dx + dx^2}{dx}
   = \lim_{dx \to 0} 6 + dx
   = 6
   &
   \end{flalign}
   $$

4. $$
   \begin{flalign}
   &
   \lim_{x = x_0 , dx \to 0} \frac{d(x^2)}{dx}
   = \lim_{dx \to 0} \frac{(x_0 + dx)^2 - x_0^2}{dx}
   = \lim_{dx \to 0} \frac{x_0^2 + 2 x_0 dx + dx^2 - x_0^2}{dx}
   = \lim_{dx \to 0} \frac{2 x_0 dx + dx^2}{dx}
   = \lim_{dx \to 0} 2x_0 + dx
   = 2x_0
   &
   \end{flalign}
   $$

5. $$
   \begin{flalign}
   & \lim_{x = x_0 , dx \to 0} \frac{d(x^n)}{dx}
   = \lim_{dx \to 0} \frac{(x_0 + dx)^n - x_0^n}{dx}
   = \lim_{dx \to 0} \frac{(x_0^n + n x_0^{n -1} dx + \frac{n(n - 1)}{2}x_0^{n -2}dx^2 + \dots + n x_0 dx^{n - 1} + dx^n) - x_0^n}{dx} & \\
   
   & = \lim_{dx \to 0} \frac{n x_0^{n -1} dx + \frac{n(n - 1)}{2}x_0^{n -2}dx^2 + \dots + n x_0 dx^{n - 1} + dx^n}{dx}
   = \lim_{dx \to 0} n x_0^{n -1} + \frac{n(n - 1)}{2}x_0^{n -2}dx + \dots + n x_0 dx^{n - 2} + dx^{n - 1}
   = n x_0^{n -1} &
   \end{flalign}
   $$

6. $$
   \begin{flalign}
   &
   \lim_{x = x_0 , dx \to 0} \frac{d(\sin x)}{dx}
   = \lim_{dx \to 0} \frac{\sin(x_0 + dx) - \sin x_0}{dx}
   = \lim_{dx \to 0} \frac{\sin x_0 \cos dx + \cos x_0 \sin dx - \sin x_0}{dx}
   = \lim_{dx \to 0} \frac{\cos x_0 \sin dx}{dx}
   = \cos x_0
   &
   \end{flalign}
   $$

7. $$
   \begin{flalign}
   &
   \lim_{x = x_0 , dx \to 0} \frac{d(\cos x)}{dx}
   = \lim_{dx \to 0} \frac{\cos(x_0 + dx) - \cos x_0}{dx}
   = \lim_{dx \to 0} \frac{\cos x_0 \cos dx - \sin x_0 \sin dx - \cos x_0}{dx}
   = \lim_{dx \to 0} \frac{-\sin x_0 \sin dx}{dx}
   = -\sin x_0
   &
   \end{flalign}
   $$

8. $$
   \begin{flalign}
   &
   \lim_{x_0 = 0 , dx \to 0} \frac{d|x|}{dx}
   = \lim_{dx \to 0} \frac{|0 + dx| - |0|}{dx}
   = \lim_{dx \to 0} \frac{|dx|}{dx}
   = 
   \begin{cases}
   -1, & \lim_{dx \to 0^-} \\
   1,  & \lim_{dx \to 0^+}
   \end{cases}
   \: \text{极限不存在}
   &
   \end{flalign}
   $$

### 3.2 可导和斜率

#### 3.2.1一元函数的可导性

由例题 8.8 可知，函数的导数不一定存在 .

当函数 $y = f(x)$ 在 $x_0$ 处极限 $\lim_{x \to x_0} \frac{dy}{dx} = f'(x_0)$ 存在时，称函数 $f(x)$ 在 $x_0$ 处 **可导** .

如果函数 $y = f(x)$ 在开区间 $(a, b)$ 内的每一点都可导，则称该函数在开区间 $(a, b)$ 上可导 .

#### 3.2.2 可微与可导的关系

函数在一点可微与可导是等价的：函数 $y = f(x)$ 在点 $x_0$ 处可微的 **充分必要条件** 是它在点 $x_0$ 处可导，并且，在微分表达式 $ dy = A dx $ 中的常数 $ A $ 正好就是函数在该点的导数，即 $ A = f'(x_0) $ .

因此，函数 $y = f(x)$ 在点 $x_0$ 处的微分可以写为：
$$
dy = f'(x_0) dx
$$

证明：

- 必要性（可微 $\Rightarrow$ 可导）：
  若 $\Delta y = A \Delta x + o(\Delta x)$ ，两边同时除以 $ \Delta x $ 并取极限：
  $$
  \lim_{\Delta x \to 0} \frac{\Delta y}{\Delta x} = \lim_{\Delta x \to 0} \left( A + \frac{o(\Delta x)}{\Delta x} \right) = A
  $$
  根据导数的定义，该极限存在且等于 $A$ ，即 $ f'(x_0) = A $ ，因此函数在 $x_0$ 处可导 .

- 充分性（可导 $\Rightarrow$ 可微）：
  若 $ f'(x_0) = \lim_{\Delta x \to 0} \frac{\Delta y}{\Delta x} $ 存在，根据极限与无穷小的关系，有：
  $$
  \frac{\Delta y}{\Delta x} = f'(x_0) + \alpha
  $$
  其中 $ \alpha \to 0 $ .两边乘以 $ \Delta x $ 得：
  $$
  \Delta y = f'(x_0) \Delta x + \alpha \Delta x
  $$
  由于 $ \lim_{\Delta x \to 0} \frac{\alpha \Delta x}{\Delta x} = 0 $ ，所以 $ \alpha \Delta x = o(\Delta x) $ . 因此，$ \Delta y = f'(x_0) \Delta x + o(\Delta x) $ ，满足可微的定义 .

#### 3.2.3 导数的几何意义

函数在一点可微与可导的等价定理揭示了微分学中两个核心概念的同一性：可导关注的是函数变化的瞬时速率（比值 $ \frac{\Delta y}{\Delta x} $ 的极限），而可微关注的是函数变化的线性近似，它们描述的是同一现象的两个侧面.某个自变量值的导数的大小就是 $y - x$ 曲线对应点处切线 **斜率** 的大小，即：

$$
\lim_{x \to x_0} \frac{dy}{dx}
= \lim_{x = x_0,\Delta x \to 0} \frac{\Delta y}{\Delta x}
= \lim_{x = x_0,\Delta x \to 0} \frac{y(x + \Delta x) - y(x)}{(x_0 + \Delta x) - x_0}
= \lim_{\Delta x \to 0} k
$$

也就是此处函数值随自变量变化的 **变化率** .

### 3.3 导函数

由例题8.4~8.7可知，每一个 $x_0$ 对应一个微商 $\frac{dy}{dx} |_{x=x_0}$ ，把 $x_0$ 替换成 $x$ ，得到每一个 $x$ 对应一个 $\frac{dy}{dx}(x)$ . 回顾函数的概念，一个自变量对应一个唯一的函数值，求每一个自变量所对应的微商的操作，相当于一个映射，由坐标映射到曲线的斜率，我们把得到的函数称为原函数的 **导函数** ，记为：

$$
\frac{dy}{dx} |_x
= \frac{d}{dx}y(x)
= \frac{d}{dx}y
\stackrel{\text{记为}}{=} y'(x)
= f'(x)
$$

其中 $\frac{d}{dx}$ 被称为 **微分算子** .

微商也可以称为 **导数** ，求微商可以称为 **求导** .

### 3.4 导函数的记号

| 记号类型       | 主要记号形式                                              | 创始人                                                       | 特点与适用场景                                               |
| -------------- | --------------------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **"撇记号"**   | $y'$, $f'$, $y''$, $f^{(n)}$                              | **拉格朗日**<br>Joseph-Louis Lagrange<br>(1736-1813，法国数学家)<br>• 分析力学奠基人<br>• 微积分重要贡献者 | • **书写简洁**，形式紧凑<br>• 适合**理论推导**和一般性讨论<br>• **高阶导数**表示方便 |
| **"微分记号"** | $\frac{dy}{dx}$, $\frac{d^2y}{dx^2}$, $\frac{d^ny}{dx^n}$ | **莱布尼茨**<br>Gottfried Wilhelm Leibniz<br>(1646-1716，德国数学家、哲学家)<br>• **微积分独立创始人**<br>• 符号系统设计者 | • 直观体现"**微商**"本质<br>• **链式法则**表达清晰<br>• **积分运算**中特别方便<br>• 变量关系明确 |
| **"点记号"**   | $\dot{y}$, $\ddot{y}$                                     | **牛顿**<br>Isaac Newton<br>(1643-1727，英国物理学家、数学家)<br>• **经典力学奠基人**<br>• **微积分创始人之一** | • **物理学中广泛使用**<br>• 专用于对**时间**的导数<br>• **力学问题**首选记号<br>• 书写简便 |

### 3.5 求导的本质

导函数是函数的“函数”，它将一个函数映射为另一个描述其变化率的函数 .

函数映射：

| 输入（数值） | 映射关系（函数）            | 输出（数值）     |
| ------- | ------------------          | ------------   |
| $x_0$ | $f(\cdot)=(\cdot)^2$      | $x_0^2$      |
| $x_0$ | $f(\cdot)=\sqrt{(\cdot)}$ | $\sqrt{x_0}$ |
| $x_0$ | $f(\cdot)=e^{(\cdot)}$    | $e^x_0$      |
| $x_0$ | $f(\cdot)=\ln(\cdot)$     | $\ln x_0$    |
| $x_0$ | $f(\cdot)=k(\cdot)+b$     | $kx_0 + b$   |

微分映射：

| 输入（函数） | 映射关系（算子） | 输出（导函数） |
| ------------ | ---------------- | -------------- |
| $C$        | $\frac{d}{dx}$ | $0$          |
| $kx$       | $\frac{d}{dx}$ | $k$          |
| $x^2$      | $\frac{d}{dx}$ | $2x$         |
| $x^n$      | $\frac{d}{dx}$ | $nx^{n-1}$   |
| $\sin x$   | $\frac{d}{dx}$ | $\cos x$     |

微分算子也可以称为 *泛函* ，它作用在原函数上得到导函数 .

### **3.6 一元函数的导函数的性质**

#### **3.6.1 代数性质**

+ **线性性**
  _例题13_
  求函数 $f(x) = ax^2 + bx +c$ ， $g(x) = x^2$ ， $h(x) = bx$ 求 $f'(x)$ 和 $ag'(x) + bh'(x) + c'$ . 发现什么规律？
  $$
  \begin{flalign}
  &
  \frac{df(x)}{dx}
  = \frac{d(ag(x) + bh(x) +c)}{dx}
  = a\frac{dg(x)}{dx} + b\frac{h(x)}{dx} + \frac{dc}{dx}
  &
  \end{flalign}
  $$
  普遍地，导函数满足：
  
  - 常数倍法则（齐次性）：
    $$
    y(x) = cf(x) \Rightarrow y'(x) = cf'(x) \\
    (cf)' = cf' \\
    \frac{d(cy)}{dx} = c\frac{dy}{dx}
    $$
    
  - 加减法法则（可加性）：
    $$
    y(x) = f(x) \pm g(x) \Rightarrow y'(x) = f'(x) \pm g'(x) \\
    (f \pm g)' = f' \pm g' \\
    \frac{f(x) \pm g(x)}{dx} = \frac{df(x)}{dx} \pm \frac{dg(x)}{dx}
    $$
  
  常数倍法则证明：
  $$
  \begin{flalign}
  y'(x)
  & = \lim_{dx \to 0} \frac{y(x + dx) - y(x)}{dx} & \\
  & = \lim_{dx \to 0} \frac{cf(x + dx) - cf(x)}{dx} & \\
  & = c\lim_{dx \to 0} \frac{f(x + dx) - f(x)}{dx} & \\
  & = cf'(x) &
  \end{flalign}
  $$
  
  
  _例题14_
  
  证明导数加减法法则 .
  
  证明：
  $$
  \begin{flalign}
  y'(x) 
  & = \lim_{dx \to 0} \frac{y(x + dx) - y(x)}{dx} & \\
  & = \lim_{dx \to 0} \frac{(f(x + dx) \pm g(x + dx)) - (f(x) \pm g(x))}{dx} & \\
  & = \lim_{dx \to 0} \frac{(f(x + dx) - f(x)) \pm (g(x + dx) - g(x))}{dx} & \\
  & = \lim_{dx \to 0} \frac{f(x + dx) - f(x)}{dx} \pm \lim_{dx \to 0} \frac{g(x + dx) - g(x)}{dx} & \\
  & = f'(x) \pm g'(x) &
  \end{flalign}
  $$
  
+ 乘积法则：
  
  $$
  y(x) = f(x)g(x) \Rightarrow y'(x) = f'(x)g(x) + f(x)g'(x) \\
  (fg)' = f'g + fg' \\
  \frac{f(x)g(x)}{dx} = \frac{df(x)}{dx} g(x) + f(x)\frac{dg(x)}{dx}
  $$
  
+ 商法则：
  
  $$
  y(x) = \frac{f(x)}{g(x)} \Rightarrow y'(x) = \frac{f'(x)g(x) - f(x)g'(x)}{g^2(x)} \\
  (\frac{f}{g})' = \frac{f'g - fg'}{g^2} \\
  \frac{d(\frac{f(x)}{g(x)})}{dx} = \frac{\frac{df(x)}{dx} g(x) - f(x)\frac{dg(x)}{dx}}{g^2(x)}
  $$
  
+ 链式法则：
  
  $$
  y(x) = f(g(x)) \Rightarrow y'(x) = f'(g(x))g'(x) \\
  (f(g))' = f'(g)g' \\
  
  \frac{df(g(x))}{dx}
  = \frac{df(g(x))}{dg(x)} \frac{dg(x)}{dx}
  \stackrel{\text{令$g(x) = u$}}{=} \frac{df(u)}{du} \frac{u}{dx}
  $$

对导函数的乘积、商、链式法则的证明可以参考 2.2 节的例题10 .

#### **3.6.2 几何性质**

+ *有界性
+ 单调性
+ *极值

#### 3.6.3 分析性质

+ 反函数的导数：
  
  $$
  (f^{-1})'(x) = \frac{1}{f'(f^{-1}(x))}
  $$

+ *中值定理

  - 罗尔定理：如果函数 $f(x)$ 在闭区间 $[a,b]$ 上连续，在开区间 $(a,b)$ 内可导，且端点值相等 $f(a) = f(b)$，则至少存在一点 $\xi \in (a,b)$，使得 $f'(\xi) = 0$ .

  - 拉格朗日中值定理：如果函数 $f(x)$ 在闭区间 $[a,b]$ 上连续，在开区间 $(a,b)$ 内可导，则至少存在一点 $\xi \in (a,b)$，使得
    $$
    f'(\xi) = \frac{f(b) - f(a)}{b - a}
    $$
    成立 .

  - 柯西中值定理：如果函数 $f(x)$ 和 $g(x)$ 在闭区间 $[a,b]$ 上连续，在开区间 $(a,b)$ 内可导，且对任意 $x \in (a,b)$ 有 $g'(x) \neq 0$，则至少存在一点 $\xi \in (a,b)$，使得
    $$
    \frac{f(b) - f(a)}{g(b) - g(a)} = \frac{f'(\xi)}{g'(\xi)}
    $$
    成立 .


+ *凹凸性
  
  - 定义：设函数 $f(x)$ 在区间 $I$ 上连续，在 $I$ 的内点处可导 .
    - 若对于 $I$ 上任意两点 $x_1 \neq x_2$，均有
      $$
      f\left( \frac{x_1 + x_2}{2} \right) \leq \frac{f(x_1) + f(x_2)}{2}
      $$
      则称 $f(x)$ 在 $I$ 上是凹函数（或下凸函数） .
    - 若不等式反向，即
      $$
      f\left( \frac{x_1 + x_2}{2} \right) \geq \frac{f(x_1) + f(x_2)}{2}
      $$
      则称 $f(x)$ 在 $I$ 上是凸函数（或上凸函数） .
  
  - 判别法：设函数 $f(x)$ 在区间 $I$ 上二阶可导 .
    - 若在 $I$ 上 $f''(x) \geq 0$，则 $f(x)$ 在 $I$ 上是凹函数 .
    - 若在 $I$ 上 $f''(x) \leq 0$，则 $f(x)$ 在 $I$ 上是凸函数 .
    - 若 $f''(x) > 0$（或 $f''(x) < 0$）在 $I$ 上恒成立，则 $f(x)$ 在 $I$ 上是严格凹（或严格凸）函数 .
  
  - 拐点：曲线 $y = f(x)$ 的凹凸性发生变化的点称为拐点 . 若 $ (x_0, f(x_0)) $ 是拐点，且 $f''(x_0)$ 存在，则 $f''(x_0) = 0$ .

### 3.7 隐函数与参数方程求导

#### 3.7.1 **隐函数求导**

**定义**：如果变量 $x$ 和 $y$ 满足方程 $F(x,y) = 0$，且存在函数 $y = f(x)$ 使得 $F(x,f(x)) \equiv 0$，则称 $y = f(x)$ 是由方程 $F(x,y) = 0$ 所确定的隐函数 .

**求导方法**：

1. 对方程 $F(x,y) = 0$ 两边同时对 $x$ 求导，将 $y$ 视为 $x$ 的函数
2. 解出 $\frac{dy}{dx}$

例题

对于方程 $x^2 + y^2 = 1$，求 $\frac{dy}{dx}$
$$
\begin{flalign}
&\frac{d}{dx}(x^2 + y^2) = \frac{d}{dx}(1) & \\
&2x + 2y\frac{dy}{dx} = 0 & \\
&\frac{dy}{dx} = -\frac{x}{y} &
\end{flalign}
$$

#### 3.7.2 **参数方程求导**

**定义**：若曲线由参数方程
$$
\begin{flalign}
&
\begin{cases}
x = \varphi(t) \\
y = \psi(t)
\end{cases}
&
\end{flalign}
$$
给出，其中 $t$ 为参数 .

- **一阶导数**：
  $$
  \frac{dy}{dx} = \frac{\frac{dy}{dt}}{\frac{dx}{dt}} = \frac{\psi'(t)}{\varphi'(t)}, \quad \varphi'(t) \neq 0
  $$

- **二阶导数**：
  $$
  \frac{d^2y}{dx^2} = \frac{d}{dx}\left(\frac{dy}{dx}\right) = \frac{\frac{d}{dt}\left(\frac{dy}{dx}\right)}{\frac{dx}{dt}} = \frac{\frac{d}{dt}\left(\frac{\psi'(t)}{\varphi'(t)}\right)}{\varphi'(t)}
  $$

- **应用**：参数方程求导常用于描述平面曲线的切线斜率和曲率 .

+ **相关变化率**
  - **概念**：当两个或多个变量通过某个方程相关联，且它们都是时间 $t$（或其他参数）的函数时，它们的变化率之间也存在关系 .

  - **求解步骤**：
    1. 找出变量之间的关系式
    2. 对关系式两边同时对 $t$ 求导
    3. 代入已知的变化率，求解未知的变化率

  **例**：直角三角形两条直角边 $x$ 和 $y$ 满足 $x^2 + y^2 = z^2$，若已知 $\frac{dx}{dt}$，求 $\frac{dy}{dt}$
  $$
  \begin{aligned}
  \frac{d}{dt}(x^2 + y^2) &= \frac{d}{dt}(z^2) \\
  2x\frac{dx}{dt} + 2y\frac{dy}{dt} &= 2z\frac{dz}{dt}
  \end{aligned}
  $$

### 3.8 初等函数的导数公式

| 函数类型       | 导数公式                                                | 备注与条件                                       |
| :------------- | :------------------------------------------------------ | :----------------------------------------------- |
| **常数**       | $(C)' = 0$                                              | $C$ 为常数                                       |
| **幂函数**     | $(x^n)' = n x^{n-1}$                                    | $n$ 为实数                                       |
| **三角函数**   | $(\sin x)' = \cos x$                                    |                                                  |
|                | $(\cos x)' = -\sin x$                                   |                                                  |
|                | $(\tan x)' = \frac{1}{\cos^2x}$                         | $x \neq \frac{\pi}{2} + k\pi , k \in \mathbb{Z}$ |
|                | $(\frac{1}{\sin x})' = -\frac{\cos x}{\sin^2 x}$        | $x \neq k\pi, k \in \mathbb{Z}$                  |
|                | $(\frac{1}{\cos x})' = \frac{\sin x}{\cos^2 x}$         | $x \neq \frac{\pi}{2} + k\pi, k \in \mathbb{Z}$  |
|                | $(\frac{1}{\tan x})' = -\frac{1}{\sin^2 x}$             | $x \neq k\pi, k \in \mathbb{Z}$                  |
| **反三角函数** | $(\arcsin x)' = \frac{1}{\sqrt{1 - x^2}}$               | $x \in (-1, 1)$                                  |
|                | $(\arccos x)' = -\frac{1}{\sqrt{1 - x^2}}$              | $x \in (-1, 1)$                                  |
|                | $(\arctan x)' = \frac{1}{1 + x^2}$                      |                                                  |
|                | $(\operatorname{arccot} x)' = -\frac{1}{1 + x^2}$       |                                                  |
| **指数函数**   | $(e^x)' = e^x$                                          |                                                  |
|                | $(a^x)' = a^x \ln a$                                    | $a > 0, , a \neq 1$                              |
| **对数函数**   | $(\ln x)' = \frac{1}{x}$                                | $x > 0$                                          |
|                | $(\log_a x)' = \frac{1}{x \ln a}$                       | $a > 0, , a \neq 1, , x > 0$                     |
| **双曲函数**   | $(\sinh x)' = \cosh x$                                  |                                                  |
|                | $(\cosh x)' = \sinh x$                                  |                                                  |
|                | $(\tanh x)' = \frac{1}{\cosh^2 x}$                     |                                                  |
| **反双曲函数** | $(\operatorname{arsinh} x)' = \frac{1}{\sqrt{x^2 + 1}}$ |                                                  |
|                | $(\operatorname{arcosh} x)' = \frac{1}{\sqrt{x^2 - 1}}$ | $x > 1$                                          |
|                | $(\operatorname{artanh} x)' = \frac{1}{1 - x^2}$        | $x \in (-1, 1)$                                  |

_例题15_

 求下列导函数

1. $$
   \begin{flalign}
   &
   (x^3)' = 3x^{3 - 1} = x^2
   &
   \end{flalign}
   $$

2. $$
   \begin{flalign}
   &
   (5x^4)' = 4 \times 5x^{4 - 1}  = 20x^3
   &
   \end{flalign}
   $$

3. $$
   \begin{flalign}
   &
   (\frac{1}{x^2})' \text{（提示：可写成 $x^{-2}$ ）}
   = (x^{-2})'
   = -2x^{-2 - 1}
   = -2x^{-3}
   &
   \end{flalign}
   $$

4. $$
   \begin{flalign}
   &
   (\sqrt{x})' \text{（提示：可写成 $x^{0.5}$ ）}
   = 0.5x^{0.5 - 1}
   = 0.5x^{-0.5}
   &
   \end{flalign}
   $$

5. $$
   \begin{flalign}
   &
   (3x^2 + 2x + 5)' = (3x^2)' + (2x)' + (5)' = 6x + 2
   &
   \end{flalign}
   $$

6. $$
   \begin{flalign}
   &
   ((2x + 1)(x - 3))'
   = (2x^2 - 5x -3)'
   = (2x^2)' - (5x)' - (3)'
   = 4x -5
   &
   \end{flalign}
   $$

7. $$
   \begin{flalign}
   &
   (xe^x)' \text{（提示：乘法公式）}
   = x'e^x + x(e^x)'
   = (1 + x)e^x
   &
   \end{flalign}
   $$

8. $$
   \begin{flalign}
   &
   (\frac{x}{x + 1})' \text{（提示：除法公式）}
   = \frac{x'(x + 1) - x(x + 1)'}{(x + 1)^2}
   = \frac{(x + 1) - x}{(x + 1)^2}
   = \frac{1}{(x + 1)^2}
   &
   \end{flalign}
   $$

9. $$
   \begin{flalign}
   &
   (\sin 3x + \cos 2x)'
   = (\sin 3x)' + (\cos 2x)'
   = \cos(3x)(3x)' + (-\sin(2x))(2x)'
   = 3\cos 3x - 2\sin 2x
   &
   \end{flalign}
   $$

10. $$
    \begin{flalign}
    &
    (4e^x + \ln(x^2))' \text{（提示：对数的性质）}
    = (4e^x + 2\ln x)'
    = (4e^x)' + (2\ln x)'
    = 4e^x + \frac{2}{x}
    &
    \end{flalign}
    $$

11. $$
    \begin{flalign}
    &
    (\sin(x^2))' \text{（提示：链式法则）}
    = \cos(x^2)(x^2)'
    = 2x\cos(x^2)
    &
    \end{flalign}
    $$

12. $$
    \begin{flalign}
    &
    (e^{2x})' \text{（提示：链式法则）}
    = e^{2x}(2x)'
    = 2e^{2x}
    &
    \end{flalign}
    $$

13. $$
    \begin{flalign}
    &
    \ln(x^2 + 1)' \text{（提示：链式法则）}
    = \frac{1}{x^2 + 1}(x^2 + 1)'
    = \frac{2x}{x^2 + 1}
    &
    \end{flalign}
    $$

14. $$
    \begin{flalign}
    &
    f(x) = x^{x} \quad (x > 0)\\
    &
    \ln f(x) = \ln x^x = x\ln x
    \Rightarrow (\ln f(x))' = (x\ln x)'
    \Rightarrow \frac{1}{f(x)}f'(x)
    = \ln x + 1 \rightarrow f'(x)
    = (\ln x + 1)f(x)
    = (\ln x + 1)x^x
    &
    \end{flalign}
    $$

_例题16_

求下列函数的多阶导函数

1. $$
   \begin{flalign}
   & f(x) = x^3 & \\
   & f'(x) = 3x^2 & \\
   & f^{(2)}(x) = 6x & \\
   & f^{(3)}(x) = 6 & \\
   & f^{(4)}(x) = 0 &
   \end{flalign}
   $$

2. $$
   \begin{flalign}
   & f(x) = \cos 4x & \\
   & f'(x) = -4\sin 4x \\
   & f^{(2)}(x) = -16\cos 4x & \\
   & f^{(3)}(x) = 64\sin 4x & \\
   & f^{(4)}(x) = 256 \cos x & \\
   & f^{(n)}(x) = -(-1)^{\lfloor (n-1)/2 \rfloor} 4^n(\frac{1 + (-1)^{n}}{2}\cos 4x + \frac{1 + (-1)^{n + 1}}{2}\sin 4x) &
   \end{flalign}
   $$

_例题17_

求下列导函数的原函数

1. $$
   \begin{flalign}
   &
   3 \rightarrow 3x + C
   &
   \end{flalign}
   $$

2. $$
   \begin{flalign}
   &
   4x \rightarrow 2X^2 + C
   &
   \end{flalign}
   $$

3. $$
   \begin{flalign}
   &
   2x + 5 \rightarrow X^2 + 5x + C
   &
   \end{flalign}
   $$

4. $$
   \begin{flalign}
   &
   x^2 \rightarrow \frac{x^e}{3} + C
   &
   \end{flalign}
   $$

5. $$
   \begin{flalign}
   &
   3x^2 - 2x + 1 \rightarrow x^3 - x^2 + x + C
   &
   \end{flalign}
   $$

6. $$
   \begin{flalign}
   &
   \frac{1}{x^2} \text{（提示：可写为 $x^{-2}$ ）} \rightarrow -\frac{1}{x} + C
   &
   \end{flalign}
   $$

7. $$
   \begin{flalign}
   &
   \sqrt{x} \text{（提示：可写为 $x^{1/2}$ ）} \rightarrow \frac{2}{3}x^{\frac{3}{2}} + C
   &
   \end{flalign}
   $$

8. $$
   \begin{flalign}
   &
   2\cos(x) \rightarrow 2\sin x + C
   &
   \end{flalign}
   $$

9. $$
   \begin{flalign}
   &
   \cos(2x) \rightarrow \frac{\sin 2x}{2} + C
   &
   \end{flalign}
   $$

10. $$
    \begin{flalign}
    &
    e^{2x} \rightarrow \frac{e^{2x}}{2} + C
    &
    \end{flalign}
    $$

### 3.9 导数在物理中的应用

#### 3.9.1 力学

##### 3.9.1.1 运动学

+ 位移： 
  $$
  \begin{flalign}
  &
  \vec x(t) \stackrel{\text{取某个方向的分量}}{\rightarrow} x(t)
  &
  \end{flalign}
  $$
  
+ 速度： 
  $$
  \begin{flalign}
  &
  v(t) = lim_{dt \to 0} \frac{x(t + dt) - x(t)}{dt}
  = \frac{dx}{dt}
  = x'(t) \stackrel{\text{记为}}{=} \dot x(t)
  = \dot x
  &
  \end{flalign}
  $$
  
+ 加速度：
  $$
  \begin{flalign}
  &
  a(t) = lim_{dt \to 0} \frac{v(t + dt) - v(t)}{dt}
  = \frac{dv}{dt} = v'(t) \stackrel{\text{记为}}{=} \dot v(t) = (x'(t))'
  = \frac{d\frac{dx}{dt}}{dt}
  = \frac{d^2x}{dt^2}
  = x''(t) \stackrel{\text{记为}}{=} \ddot x(t)
  = \ddot x
  &
  \end{flalign}
  $$
  
+ 角位移： 
  $$
  \begin{flalign}
  &
  \theta(t)
  &
  \end{flalign}
  $$
  
+ 角速度：
  $$
  \begin{flalign}
  &
  \omega(t) = lim_{dt \to 0} \frac{\theta(t + dt) - \theta(t)}{dt}
  = \frac{d\theta}{dt}
  = \theta'(t) \stackrel{\text{记为}}{=} \dot \theta(t)
  = \dot \theta
  &
  \end{flalign}
  $$
  
+ 角加速度： 
  $$
  \begin{flalign}
  &
  \beta(t) = lim_{dt \to 0} \frac{\omega(t + dt) - \omega(t)}{dt}
  = \frac{d\omega}{dt}
  = \omega'(t) \stackrel{\text{记为}}{=} \dot \omega(t)
  = (\theta'(t))'
  = \frac{d\frac{d\theta}{dt}}{dt}
  = \frac{d^2\theta}{dt^2}
  = \theta''(t) \stackrel{\text{记为}}{=} \ddot \theta(t)
  = \ddot \theta
  &
  \end{flalign}
  $$

_例题18_

1. 已知自由落体的下落高度$h$和下落时间$t$的关系为 $h(t) = \frac{gt^2}{2}$ ，用导数的知识证明物体做匀加速直线运动且加速度恒定 .
   $$
   \begin{flalign}
   & v
   = \frac{dh}{dt}
   = \frac{d}{dt} (\frac{gt^2}{2})
   = gt & \\
   & a
   = \frac{dv}{dt}
   = \frac{d}{dt} gt
   = g &
   \end{flalign}
   $$

2. 一个质点的直线运动方程为 $x(t) = t^3 - 6t^2 + 9t + 1$ ，利用导数知识求速度和加速度的表达式 $v(t)$ 和 $a(t)$ ，并求出物体何时速度为 $0$ .
   $$
   \begin{flalign}
   & v
   = \frac{dx}{dt}
   = \frac{d}{dt} (t^3 - 6t^2 + 9t + 1)
   = 3t^2 - 12t + 9 & \\
   & 3t^2 - 12t + 9 =0
   \Rightarrow t = 1 \text{ or } 3 s &
   \end{flalign}
   $$

3. 一个质点做圆周运动的运动方程为 $\theta(t) = -3t^3 + 2t^2 + 1$ ，利用导数知识求角速度和角加速度的表达式 $\omega(t)$ 和 $\beta(t)$ ，并求出物体何时正向角速度最大 .
   $$
   \begin{flalign}
   & \omega
   = \frac{d\theta}{dt}
   = \frac{d}{dt} (-3t^2 +2t^2 + 1)
   = -9t^2 + 4t & \\
   & \beta
   = \frac{d\omega}{dt}
   = \frac{d}{dt} (-9t^2 + 4t)
   = -18t + 4 & \\
   & -18t + 4 = 0
   \Rightarrow t = \frac{2}{9} \text{s} &
   \end{flalign}
   $$

4. （2009年同济大学）距平直河岸 $l = 500m$ 处有一艘静止的船，船上的探照灯以转速 $n = 1 r/min$ 转动.当光束与岸边成 $60^\circ$ 角时,光束沿岸边移动的速率为？
   $$
   \begin{flalign}
   & x
   = l \sin \theta
   = l \sin \omega t & \\
   & v
   = \frac{dx}{dt}
   = \frac{d}{dt} (l \tan \omega t)
   = l \omega \frac{1}{\cos^2 \omega t} & \\
   & v|_{\theta = 90^\circ - 60^\circ = 30^\circ }
   = l \omega \frac{1}{\cos^2 \theta}
   = \frac{4}{3} l \omega
   = \frac{4}{3} \times 500 \times \frac{2 \pi}{60}
   \approx 69.8 \text{m/s} &
   \end{flalign}
   $$

5. 用导数证明以 $45^\circ$ 从水平面发射初速度大小 $v_0$ 相同的物体后其落地时的水平位移最大.
   $$
   \begin{flalign}
   & x
   = v_x t_y
   = v_0 \cos \theta \frac{2 v_0 \sin \theta}{g}
   = \frac{2 v_0^2}{g} \cos \theta \sin \theta
   = \frac{v_0^2}{g} \sin 2\theta & \\
   & \frac{dx}{d\theta}|_\theta = 45^\circ
   = \frac{v_0^2}{g} \frac{d}{d\theta} (\sin 2\theta)|_\theta = 45^\circ
   = \frac{2 v_0^2}{g} \cos 2\theta|_\theta = 45^\circ
   = 0 &
   \end{flalign}
   $$

##### 3.9.1.2 动力学

+ 牛顿第二定律：
  $$
  \vec F = m \vec a \stackrel{\text{取某个方向的分量}}{\rightarrow} F(t) = m \ddot x
  $$

#### 3.9.2 物理学其他分支

+ 电磁学
+ 光学
+ 热力学
+ 近代物理学

---

## 4. 一元函数的积分（Integral）

### 4.1 积分的定义

#### 4.1.1 积分的几何意义

导数可以理解为 **求斜率** 的过程，积分可以理解为 **求面积** 的过程 .

对于 $y = f(x)$ 在区间 $[a, b]$ 上的图像，我们希望用一种方法计算曲线与 $x$ 轴之间的面积 .

例如：

* 求匀速直线运动中速度 $v$ 和时间 $t$ 的关系曲线与 $t$ 轴之间的面积，该面积的大小可以代表位移 $x$ 的大小 .

* 求变力做功中力 $F$ 和位移 $x$ 的关系曲线与 $x$ 轴之间的面积，该面积可以代表功 $W$ 的大小 .

#### 4.1.2 黎曼和与定积分

将区间 $[a, b]$ 分成 $n$ 个小区间，每个小区间长度为 $\Delta x_i$ ，在每个小区间 $[x_i,x_i + \Delta x_i]$ 上任取一点 $\xi_i$ ，则第 $i$ 个小区间的面积为：
$$
s(i) = f(\xi_i) \Delta x_i
$$
所有小区间的面积和为：
$$
S(n)
= \Sigma_{i = 1}^{n} s(i)
= \Sigma_{i = 1}^{n} f(\xi_i) \Delta x_i
$$

称为**黎曼和**.

当最大小区间长度 $\max(\Delta x_i) \to 0$ 时，  $n \to \infty$  ，如果黎曼和的极限存在，即：
$$
\lim_{n \to \infty , \max(\Delta x_i) \to 0} S(n) = S
$$
则称此极限为 $f(x)$ 在$[a, b]$上的 **定积分** ：
$$
S
= \lim_{\max(\Delta x_i) \to 0} \Sigma_{i=1}^n f(\xi_i) \Delta x_i
= \lim_{\max(\Delta x_i) \to 0} \Sigma_{i = 1}^{n} f(x_i) \Delta x_i
\stackrel{\text{记为}}{=} \int_{a}^b f(x) dx
$$

其中：

* $\int$ ：积分号， 是求和的英文 $\text{“Sum”}$ 的首字母 $\text{"S"}$ 的变形，表示求和

* $a, b$ ：积分下限和积分上限，表示面积的最左端和最右端

* $f(x)$ ：被积函数，表示曲线的形状

* $dx$ ：积分变量，表示小区间的宽度的微分

_例题19_

匀加速直线运动的 $v - t$ 图线是一条直线： $v = v_0 + at$ ，用定积分证明 $v - t$ 与 $t$ 轴在区间 $[0,t]$ 内所围的面积 $S = v_0 t + \frac{a t^2}{2}$ .

证明：
$$
\begin{flalign}
&
\text{把区间} \: [0,t] \:
\text{$n$ 等分，则} \:
\Delta t_i = \frac{t}{n}
\text{，取} \:
\xi_i = \frac{t}{n}i \:
\text{则} \:
v(\xi_i) = v_0 + a \frac{t}{n}i
&
\end{flalign}
$$

$$
\begin{flalign}
\text{黎曼和：} S(n)
& = \Sigma_{i = 1}^{n} v(\xi_i) \Delta t_i & \\
& = \Sigma_{i = 1}^{n} (v_0 + a \frac{t}{n}i) \frac{t}{n} & \\
& = \Sigma_{i = 1}^{n} v_0 \frac{t}{n} + \Sigma_{i = 1}^{n} a (\frac{t}{n})^2i & \\
& = v_0 \frac{t}{n}\Sigma_{i = 1}^{n} 1 + a (\frac{t}{n})^2\Sigma_{i = 1}^{n} i & \\
& = v_0 \frac{t}{n} n + a (\frac{t}{n})^2 \frac{(1 + n)n}{2} & \\
& = v_0 t + a t^2 \frac{1 + n}{2n} &
\end{flalign}
$$

$$
\begin{flalign}
\text{定积分：} \lim_{n \to \infty} S(n)
& = \lim_{n \to \infty} v_0 t + a t^2 \frac{1 + n}{2n} & \\
& = v_0 t + \frac{a t^2}{2} &
\end{flalign}
$$

### 4.2 变上限定积分与微积分第一基本定理

#### 4.2.1 变上限定积分

我们固定定积分的积分下限 $a$ 而让积分上限变化，从而构造出一个新的函数：
$$
\Phi(x) = \int_{a}^{x} f(t) dt
$$

这个函数 $\Phi(x)$ 称为 **变上限定积分** 或 **积分上限函数** .

#### 4.2.2 微积分第一基本定理

如果 $f(x)$ 在 $[a, b]$ 上连续，那么由它构造出的变上限定积分 $\Phi(x)$ 在 $[a, b]$ 上可导，且 $\Phi'(x) = f(x)$ ：
$$
\frac{d\Phi(x)}{dx} = \frac{d}{dx}[\int_{a}^{x} f(t) dt] = f(x)
$$
证明：
$$
\begin{flalign}
\frac{d\Phi(x)}{dx}
& = \frac{d}{dx}(\int_{a}^{x} f(t) dt) & \\
& = \frac{\int_{a}^{x + dx} f(t) dt - \int_{a}^{x} f(t) dt}{dx} & \\
& = \frac{\int_{x}^{x + dx} f(t) dt}{dx} & \\
& = f(x) &
\end{flalign}
$$

### 4.3 不定积分与微积分第二基本定理

#### 4.3.1 原函数与不定积分

如果 $F'(x) = f(x)$ ，则称 $F(x)$ 是 $f(x)$ 的一个 **原函数** . $f(x)$的所有原函数的集合称为$f(x)$的 **不定积分** ，记为：

$$
F(x) + C \stackrel{记为}{=} \int f(x) dx
$$

其中 $C$ 为任意常数 .

显然，变上限积分 $\Phi(x)$ 是 $f(x)$ 的一个原函数 .

_例题20_

求下列不定积分

1. $\int 2x dx = x^2 +C$
2. $\int \cos x dx = \sin x + C$

**补充：不定积分与微分方程*

求函数 $f(x)$ 的不定积分，实质上就是在求解一个最简单的 **一阶微分方程** ：
$$
\frac{dy}{dx} = f(x)
$$
这个方程的含义是：寻找一个函数 $y = F(x)$，满足导数恰好等于已知函数 $f(x)$ .

该微分方程的 **通解**（即所有可能的解）正是 $f(x)$ 的不定积分：
$$
y = \int f(x) dx = F(x) + C
$$
其中任意常数 $C$ 对应了不同的初始条件 . 如果给定初始条件 $y(x_0) = y_0$，我们就可以确定唯一的常数 $C$，从而得到一个 **特解** .

因此，求不定积分是求解微分方程的基础，它解决了“已知变化率，求原函数”这一基本问题 .

#### 4.3.2 微积分第二基本定理（牛顿-莱布尼茨公式）

如果 $F(x)$ 是$f(x)$在 $[a, b]$ 上的一个原函数，则：

$$
\int_{a}^{b} f(x) dx = F(b) - F(a)
\stackrel{\text{记为}}{=} F(x)|_{x = a}^{x = b}
\stackrel{\text{简记为}}{=} F(x)|_{a}^{b}
$$

这个公式建立了定积分与不定积分之间的联系，计算定积分就等价于先求不定积分，再代入上下限求差值 .

_例题21_

求下列定积分

1. $$
   \begin{flalign}
   &
   \int_0^1 x^2 dx = (\frac{x^3}{3} + C)|_0^1
   = (\frac{1^3}{3} + C) - (\frac{0^3}{3} + C)
   = \frac{1^3}{3}
   &
   \end{flalign}
   $$

2. $$
   \begin{flalign}
   &
   \int_0^\pi \sin x dx = (-\cos x )|_0^\pi
   = \cos x |_\pi^0
   = \cos0 - \cos \pi
   = 2
   &
   \end{flalign}
   $$

#### 4.3.3 导数与积分的关系

导数和积分，一个研究变化的瞬时速率，一个研究变化的累积效应，起初被认为是两个互不相关的概念 .

然而， **微积分基本定理** 揭示了 **求导（微分）与积分是互逆运算** 这一核心关系：
$$
\frac{d(\int f(x) dx)}{dx} = \int \frac{df(x)}{dx} dx = \int f'(x) dx = f(x) \\
\int df = f
$$

换言之，一个函数的原函数的导函数是其本身，一个函数的导函数的原函数也是其本身 .

### **4.4 积分的性质**

#### 4.4.1 代数性质

+ 线性性质：

  $$
  \int (af(x) \pm bg(x)) dx  =a\int f(x) dx \pm b\int g(x) dx
  $$

+ 区间可加性：

  $$
  \int_a^b f(x) dx = \int_a^c f(x) dx  + \int_c^b f(x) dx
  $$

+ 区间反称性：
  $$
  \int_a^b f(x) dx = -\int_b^a f(x) dx
  $$

#### 4.4.2 几何性质

+ 奇偶函数的积分
+ *非负性
+ *单调性
+ *绝对可积性与三角不等式

+ *积分中值定理：
  如果 $f(x)$ 在 $[a, b]$ 上连续，则存在 $\xi \in [a, b]$ ，使得：
  $$
  \int_a^b f(x) dx = f(\xi)(b - a)
  $$

#### 4.4.3 分析性质

+ *连续性
+ *可微性（莱布尼茨法则）
+ 极限与积分顺序可交换
+ 微积分基本定理

### **4.5 积分的计算方法**

#### 4.5.1 第一类换元积分法（凑微分）

设 $u = g(x)$ 可导，则：

$$
\int f(g(x))g′(x) dx  = \int f(u) du
$$

证明：
$$
\begin{flalign}
& \int f(g(x))g′(x) dx = \int f(u) du & \\
& \stackrel{\text{两边对 $x$ 积分}}{\Leftarrow} f(g(x))g′(x)
= \frac{d(\int f(u) du)}{dx} & \\
& \stackrel{\text{导数的链式法则}}{\Leftarrow} \frac{d(\int f(u) du)}{du} \frac{du}{dx}
= f(u) \frac{du}{dx} &
\end{flalign}
$$
_例题22_

1. $$
   \begin{flalign}
   &
   \int 2x e^{x^2} dx
   = \int e^{x^2} (2x dx)
   = \int e^{x^2} d(x^2)
   \stackrel{\text{令} x^2 = u}{=} \int e^{u} du = e^u + C
   \stackrel{u = x^2}{=} e^{x^2} + C
   &
   \end{flalign}
   $$

2. $$
   \begin{flalign}
   &
   \int \frac{\ln x}{x} dx 
   = \int \ln x (\frac{1}{x} dx)
   = \int \ln x d(\ln x)
   \stackrel{\text{令} \ln x = u}{=} \int u du
   = \frac{1}{2}u^2 + C
   \stackrel{u = \ln x}{=} \frac{1}{2}(\ln x)^2 + C
   &
   \end{flalign}
   $$

3. $$
   \begin{flalign}
   &
   \int \frac{e^x}{1 + e^x} dx 
   = \int \frac{1}{1 + e^x}(e^x dx)
   = \int \frac{1}{1 + e^x} d(1 + e^x)
   \stackrel{\text{令} 1 + e^x = u}{=} \int \frac{1}{u} du
   = \ln|u| + C
   \stackrel{u = 1 + e^x}{=} \ln(1 + e^x) + C
   &
   \end{flalign}
   $$

#### 4.5.2 第二类换元积分法（变量代换）

令 $x = g(t)$ 可导，则：
$$
\int f(x) dx = \int f(g(t)) dg(t) = \int f(g(t)) g'(t) dt
$$

_例题23_

1. $$
   \begin{flalign}
   &
   \int \frac{1}{\sqrt{a^2 - x^2}} dx (a>0)
   \stackrel{\text{令} x = a \sin t}{=} \int \frac{1}{\sqrt{a^2 - a^2 \sin^2 t}} d(a \sin t)
   = \int \frac{1}{a \sqrt{\cos^2 t}} a \cos t dt
   = \int \frac{\cos t}{|\cos t|} dt
   = \int 1 dt \quad \text
   = t + C
   \stackrel{t = \arcsin x}{=} \arcsin \frac{x}{a} + C
   &
   \end{flalign}
   $$

2. $$
   \begin{flalign}
   & \int \frac{1}{\sqrt{x^2 + a^2}} dx (a>0)
   \stackrel{\text{令} x = a \tan t}{=} \int \frac{1}{\sqrt{a^2 + a^2 \tan^2 t}} d(a \tan t)
   = \int \frac{|\cos t|}{a} \frac{a}{\cos^2 t} dt
   = \int \frac{1}{|\cos t|} dt
   \stackrel{0 < \cos t}{=} \int \frac{1}{\cos t} dt & \\
   & \stackrel{\text{令} t = 2 \arctan u}{=} \int \frac{1 + u^2}{1 - u^2} d(2 \arctan u)
   = \int \frac{1 + u^2}{1 - u^2} \frac{2}{1 + u^2} du
   = \int \frac{1}{u + 1} - \frac{1}{u - 1} du
   = \ln |u + 1| + \ln |u - 1| + C
   \stackrel{u = \tan \frac{t}{2}}{=} \ln |\frac{1 + \tan \frac{t}{2}}{1 - \tan \frac{t}{2}}| + C &
   \end{flalign}
   $$

#### 4.5.3 分部积分法

$$
\int udv = uv − \int vdu \\
\int u(x)v′(x) dx = u(x)v(x) − \int u′(x)v(x) dx
$$

证明：

$$
\begin{flalign}
\int udv
& = uv − \int vdu & \\
\Leftarrow & \frac{d(\int udv)}{dx} = \frac{d(uv)}{dx} − \frac{d(\int vdu)}{dx} & \\
\Leftarrow & \frac{d(\int udv)}{dv} \frac{dv}{dx}
= \frac{du}{dx}v + u\frac{dv}{dx} - \frac{d(\int vdu)}{du} \frac{du}{dx} & \\
\Leftarrow & u\frac{dv}{dx}
= \frac{du}{dx}v + u\frac{dv}{dx} - v\frac{du}{dx} &
\end{flalign}
$$

_例题24_

1. $$
   \begin{flalign}
   &
   \int x e^x dx
   = \int x (e^x dx)
   = \int x de^x
   = x de^x - \int e^x dx
   = x de^x - (e^x + C)
   = (x - 1)e^x + C
   &
   \end{flalign}
   $$

2. $$
   \begin{flalign}
   \int e^x \sin x dx
   & = \int\sin x (e^x  dx) & \\
   & = \int\sin x de^x & \\
   & = \sin x de^x - \int e^x d\sin x & \\
   & = \sin x de^x - \int e^x \cos x dx & \\
   & = \sin x de^x - \int \cos x de^x & \\
   & = \sin x de^x - (\cos x e^x - \int e^x d(\cos x)) & \\
   & = \sin x de^x - (\cos x e^x + \int e^x \sin x dx) & \\
   \stackrel {\text{左式}=\text{右式}}{\Rightarrow} & \int e^x \sin x dx = \frac{\sin x de^x - \cos x e^x}{2} &
   \end{flalign}
   $$

### 4.6 反常积分

### **4.7 初等函数的积分公式**

| 函数类型       | 积分公式                                                     | 备注与条件                     |
| :-------------| :----------------------------------------------------------- | :----------------------------- |
| **常数**      | $\int k dx = kx + C$                                         | $k$ 为常数                     |
| **幂函数**    | $\int x^n dx = \dfrac{x^{n+1}}{n+1} + C$                     | $n \neq -1$                    |
|                | $\int \frac{1}{x} dx = \ln |x|+ C$                           | $x \neq 0$                     |
|                | $\int \dfrac{1}{x^2} dx = -\dfrac{1}{x} + C$                 | $x \neq 0$                     |
|                | $\int \sqrt{x} dx = \dfrac{2}{3}x^{3/2} + C$                 | $x > 0$                        |
|                | $\int \dfrac{1}{\sqrt{x}} dx = 2\sqrt{x} + C$                | $x > 0$                        |
| **三角函数**  | $\int \sin x dx = -\cos x + C$                               |                                |
|                | $\int \cos x dx = \sin x + C$                                |                                |
|                | $\int \tan x dx = -\ln \cos x + C$                           | $x \neq \dfrac{\pi}{2} + k\pi , k \in \mathbb{Z}$ |
|                | $\int \frac{1}{\tan x}x dx = \ln \sin x + C$        | $x \neq k\pi , k \in \mathbb{Z}$ |
|                | $\int \frac{1}{\sin^2 x} \, dx = -\cot x + C$ | $x \neq k\pi , k \in \mathbb{Z}$ |
|                | $\int \frac{1}{\cos^2 x} \, dx = \tan x + C$ | $x \neq \dfrac{\pi}{2} + k\pi , k \in \mathbb{Z}$ |
|                | $\int \frac{\sin x}{\cos^2 x} \, dx = \frac{1}{\cos x} + C$ | $x \neq \dfrac{\pi}{2} + k\pi , k \in \mathbb{Z}$ |
|                | $\int \frac{\cos x}{\sin^2 x} \, dx = -\frac{1}{\sin x} + C$ | $x \neq k\pi , k \in \mathbb{Z}$ |
| **反三角函数** | $\int \dfrac{1}{1+x^2} dx = \arctan x + C$                   |                                |
|                | $\int \dfrac{1}{\sqrt{1-x^2}} dx = \arcsin x + C$            | **$|x| < 1$**                  |
|                | $\int \dfrac{1}{\sqrt{a^2-x^2}} dx = \arcsin \dfrac{x}{a} + C$ | $a > 0$, **$|x| < a$**         |
|                | $\int \dfrac{1}{a^2+x^2} dx = \dfrac{1}{a} \arctan \dfrac{x}{a} + C$ | $a \neq 0$                     |
| **指数函数**   | $\int e^x dx = e^x + C$                                      |                                |
|                | $\int a^x dx = \dfrac{a^x}{\ln a} + C$                       | $a > 0, a \neq 1$              |
|                | $\int e^{-x} dx = -e^{-x} + C$                               |                                |
| **对数函数**   | $\int \ln x dx = x\ln x - x + C$                             | $x > 0$                        |
|                | $\int \log_a x dx = \dfrac{x\ln x - x}{\ln a} + C$           | $x > 0, a > 0, a \neq 1$       |
| **双曲函数**   | $\int \sinh x dx = \cosh x + C$                              |                                |
|                | $\int \cosh x dx = \sinh x + C$                              |                                |
|                | $\int \tanh x dx = \ln (\cosh x) + C$                        |                                |

### 4.8 积分在物理中的应用

#### 4.8.1 力学应用

##### 4.8.1.1 运动学

+ 急动度（加加速度）：
  $$
  \begin{flalign}
  &
  j(t)
  &
  \end{flalign}
  $$

+ 加速度：
  $$
  \begin{flalign}
  &
  a(t) = \int j(t) dt
  &
  \end{flalign}
  $$

+ 速度：
  $$
  \begin{flalign}
  &
  v(t) = \int a(t) dt = \int \int j(t) dt dt
  &
  \end{flalign}
  $$

+ 位移：
  $$
  \begin{flalign}
  &
  x(t) = \int v(t) dt = \int \int a(t) dt dt = \int \int \int j(t) dt dt dt
  &
  \end{flalign}
  $$

1. （2013年复旦大学）质点做直线运动， $0 \leq t \leq T$ 时间段内瞬时速度为 $v = v_0\sqrt{1-(\frac{t}{T})^2}$ ，其平均速度为？

$$
\begin{flalign}
\bar v
& = \frac{x_T}{T} & \\
& = \frac{1}{T} \int_0^T v(t) dt & \\
& = \frac{1}{T} \int_0^T v_0 \sqrt{1 - (\frac{t}{T})^2} dt & \\
& \stackrel{\text{令}t = T\sin \tau , \tau \in [0,\frac{\pi}{2}]}{=} \frac{1}{T} \int_0^T v_0 \sqrt{1 - (\frac{T\sin \tau}{T})^2} d(T\sin \tau) & \\
& = \frac{1}{T} \int_0^\frac{\pi}{2} v_0 \sqrt{1 - (\frac{T\sin \tau}{T})^2} d(T\sin \tau) & \\
& = v_0 \int_0^\frac{\pi}{2} \cos^2 \tau d\tau & \\
& = v_0 \int_0^\frac{\pi}{2} \frac{1 + \cos 2\tau}{2} d\tau & \\
& = v_0 (\int_0^\frac{\pi}{2} \frac{1}{2} d\tau + \int_0^\frac{\pi}{2} \frac{\cos 2\tau}{2} d\tau) & \\
& = v_0 (\frac{\pi}{4} + 0) & \\
& = \frac{\pi}{4} v_0 &
\end{flalign}
$$

2. （2020年上海交通大学）物体运动的速度与位移满足关系 $v = \frac{v_0 L}{L + x}$ ，其中 $v_0 = 3 m/s$ ， $L = 30m$ ，则它经过 $30m$ 位移所需的时间？

$$
\begin{flalign}
t
& = \int dt & \\
& = \int_0^L \frac{1}{v(x)} dx & \\
& = \int_0^L \frac{L + x}{v_0 L} dx & \\
& = \int_0^L \frac{1}{v_0} + \int_0^L \frac{x}{v_0 L} dx & \\
& = \frac{L}{v_0} + \frac{1}{v_0 L}\frac{L^2}{2} & \\
& = \frac{3 L}{2 v_0} & \\
& = 15s &
\end{flalign}
$$

##### 4.8.1.2 动力学

1. （2019年上海交通大学）质量为 $10g$ 的物体在光滑水平面上做直线运动 . 物体从 $t =0$ 时刻起受到与时间依赖关系为 $F = 0.001sin2t (N)$ 的合外力作用 . 已知物体在 $t = 0$ 时处于 $x = 0$ 位置，且初速度 $v.=-0.05 m/s$ ，则 $t = \frac{\pi}{6}s$ 时物体的位置坐标为？
   $$
   \begin{flalign}
   & \text{由牛顿第二定律 $F = ma$ 得：} & \\
   & a(t) = \frac{F(t)}{m} = \frac{0.001\sin 2t}{0.01} = 0.1\sin 2t  (m/s^2) & \\
   & v(t) = \int a(t)  dt = \int 0.1\sin 2t  dt = -0.05\cos 2t + C_1 & \\
   & \text{由初条件 $v(0) = -0.05$ 得：} & \\
   & -0.05\cos 0 + C_1 = -0.05 \Rightarrow -0.05 + C_1 = -0.05 \Rightarrow C_1 = 0 \Rightarrow v(t) = -0.05\cos 2t & \\
   & x(t) = \int v(t)  dt = \int -0.05\cos 2t dt = -0.025\sin 2t + C_2 & \\
   & \text{ 由初条件 $x(0) = 0$ 得：} & \\
   & -0.025\sin 0 + C_2 = 0 \Rightarrow C_2 = 0 \Rightarrow x(t) = -0.025\sin 2t & \\
   & x(\frac{\pi}{6}) = -0.025\sin \frac{\pi}{3} = \frac{\sqrt{3}}{80} m
   \end{flalign}
   $$

2. （2020年北京大学）设想在宇宙中，一个水平放置的半径为 $R$ 的圆环上套有一个质量为 $m$ 的小珠，开始时小珠的速度为 $v_0$ . 已知小珠与圆环的动摩擦因数为 $\mu$ ，则小珠停下所需的时间为？
   $$
   \begin{flalign}
   & \text{小珠受到圆环的摩擦：} f = \mu F_n
   = \mu m \frac{v^2}{R} & \\
   & \text{由牛顿第二定律：} -f = ma_\tau
   \stackrel{\text{代入} f}{\Rightarrow} - \mu m \frac{v^2}{R} = ma_\tau
   \stackrel{\text{消去} m}{\Rightarrow} - \mu \frac{v^2}{R} = a_\tau
   \stackrel{\text{用} \frac{dv}{dt} \text{代替} a_\tau}{\Rightarrow} - \mu \frac{v^2}{R} = \frac{dv}{dt} & \\
   & \text{分离变量：} dt = \frac{dv}{- \mu \frac{v^2}{R}} & \\
   & \text{两边积分：} \int_0^t dt = \int_{v_0}^0 \frac{1}{- \mu \frac{v^2}{R}} dv & \\
   & t = \frac{R}{\mu}\int_0^{v_0} \frac{1}{v^2} dv
   = \frac{R}{\mu}(-\frac{1}{v})|_0^{v_0}
   = \frac{R}{\mu}(\frac{1}{0} - \frac{1}{v_0}) \text{ 趋于无穷大} &
   \end{flalign}
   $$

3. 用积分证明一个球完全浸没在在水中时所受的浮力大小满足阿基米德原理： $F_\text{浮} = \rho_\text{液} g V_\text{排}$ .
   $$
   \begin{flalign}
   & \text{设球的半径为} R &
   \end{flalign}
   $$

#### 4.8.2 物理学其他分支

+ 电磁学
+ 光学
+ 热力学
+ 近代物理学

---

## 6. 一元函数的泰勒展开（Taylor expansion）

### 6.1 泰勒公式
f(x) = f(x₀) + f'(x₀)(x-x₀) + f''(x₀)(x-x₀)²/2! + ... + f⁽ⁿ⁾(x₀)(x-x₀)ⁿ/n! + Rₙ(x)

### 6.2 常见函数的麦克劳林展开（x₀=0）
e^x = 1 + x + x²/2! + x³/3! + ...
sin x = x - x³/3! + x⁵/5! - ...
cos x = 1 - x²/2! + x⁴/4! - ...
1/(1-x) = 1 + x + x² + x³ + ... (|x|<1)

---

## 7. 常微分方程（Ordinary Differential Equation）

### 7.1 基本概念

含有未知函数导数的方程称为微分方程.

### 7.2 一阶微分方程
- 可分离变量方程：dy/dx = f(x)g(y)
- 一阶线性方程：y' + P(x)y = Q(x)

### 7.3 积分在物理中的应用

#### 7.3.1 力学应用

##### 7.3.1.1 运动学

##### 7.3.1.2 动力学

例题

1. （2018年清华大学）一个小球贴着一个圆柱形桶的边缘做圆周运动，已知初速度 $v_0 = 10 m/s$ ，小球与桶壁及桶底之间的动摩擦因数均为 $\mu = 0.01$ ，桶的半径 $R = 10 m$ ，那么小球停止运动的时间约为？
   $$
   \begin{flalign}
   & \text{小球受到桶底和桶壁的摩擦：} f = \mu F_N + \mu F_n
   = \mu mg + \mu m \frac{v^2}{R} & \\
   & \text{由牛顿第二定律：} -f = ma_\tau
   \stackrel{\text{代入} f}{\Rightarrow} -\mu mg - \mu m \frac{v^2}{R} = ma_\tau
   \stackrel{\text{消去} m}{\Rightarrow} -\mu g - \mu \frac{v^2}{R} = a_\tau & \\
   & \text{用 $\frac{dv}{dt}$ 代替 $a$ 得到微分方程：} -\mu g - \mu \frac{v^2}{R} = \frac{dv}{dt} & \\
   & \text{分离变量：} dt = \frac{dv}{-\mu g - \mu \frac{v^2}{R}} & \\
   & \text{两边积分：} \int_0^t dt = \int_{v_0}^0 \frac{1}{-\mu g - \mu \frac{v^2}{R}} dv & \\
   & t = \int_0^{v_0} \frac{1}{\mu g + \mu \frac{v^2}{R}} dv
   = \frac{R}{\mu} \int_0^{v_0} \frac{1}{gR + v^2} dv
   \stackrel{\text{由积分公式} \int \dfrac{1}{a^2+x^2} dx = \dfrac{1}{a} \arctan \dfrac{x}{a} + C}{=} \frac{R}{\mu} \frac{1}{\sqrt{gR}} \arctan \frac{v}{\sqrt{gR}}|_0^{v_0}
   = \frac{R}{\mu} \frac{1}{\sqrt{gR}} \arctan \frac{v_0}{\sqrt{gR}} & \\
   & t = \frac{10}{0.01} \frac{1}{\sqrt{10 \times 10}} \arctan \frac{10}{\sqrt{10 \times 10}}
   = 25 \pi
   \approx 78.5 s &
   \end{flalign}
   $$

2. （2019年上海交通大学三位一体）为了研究钢球在液体中的运动，让钢球从某一高度竖直落下进入液体中运动，已知钢球在液体中运动时受到的阻力与速度大小成正比，则钢球会做什么运动？
   $$
   \begin{flalign}
   & \text{钢球液体的摩擦：} f = -kv & \\
   & \text{由牛顿第二定律：} mg + f = ma
   \stackrel{\text{代入} f}{\Rightarrow} mg -kv = ma
   \stackrel{\text{消去} m}{\Rightarrow} g - \frac{k}{m}v = a & \\
   & \text{用 $\frac{dv}{dt}$ 代替 $a$ 得到微分方程：} g - \frac{k}{m}v = \frac{dv}{dt} & \\
   & \text{分离变量：} dt = \frac{dv}{g - \frac{k}{m}v} & \\
   & \text{两边积分：} \int_0^t dt = \int_{v_0}^v \frac{1}{g - \frac{k}{m}v} dv & \\
   & t = - \frac{m}{k} \int_{v_0}^v \frac{1}{g - \frac{k}{m}v} d(g - \frac{k}{m}v)
   = - \frac{m}{k} \ln|g - \frac{k}{m}v||_{v_0}^v
   = - \frac{m}{k} \ln|\frac{g - \frac{k}{m}v}{g - \frac{k}{m}v_0}| & \\
   & e^{- \frac{k}{m} t}
   = e^ {\ln|\frac{g - \frac{k}{m}v}{g - \frac{k}{m}v_0}|}
   = |\frac{g - \frac{k}{m}v}{g - \frac{k}{m}v_0}| & \\
   & v = \frac{mg}{k} - (\frac{mg}{k} - v_0) e^{- \frac{k}{m} t} & \\
   \end{flalign}
   $$

#### 7.3.2 其他物理学分支

##### 7.3.2.1 电磁学

1. 求均匀圆盘圆心到圆周上一点的等效电阻 .

## **_作业_**

### 1. 极限部分：

* a. 仿照 $\lim_{t \to 5s} x(t) = 10 m$ 的形式举2个类似的极限式子 .

* b. 用极限的语言表示下列事实：
  
  1. $S = \frac{1}{5} + \frac{2}{25} + \frac{3}{125} + \cdots$
  
  2. 质点在 $t = 2s$ 时的 **瞬时速率** 大小为 $u_2$ .
  
  3. 根据万有引力定律，地球表面的重力加速度随离地高度增加而变小： $g(h) = \frac{GM_e}{(R_e + h)^2}$ ，但是在实际应用中，地球表面 **附近** 的重力加速度可近似为 $g$ .
  
  4. 对于薄透镜，物距 $u$ 、像距 $v$ 、焦距 $f$ 满足高斯公式： $\frac{1}{u} + \frac{1}{v} = \frac{1}{f}$ ，当物体距离透镜 **无限远** 时物体的像呈现在焦平面上 .
  
  5. 已知相对论动能公式： $E_k = (\gamma - 1)mc^2$ ，其中 $\gamma = \frac{1}{\sqrt{1-v^2/c^2}}$ ，当速度 **远小于** 光速时，动能公式近似成：$E_k = \frac{1}{2}mv^2$ .

* c. 计算下列极限的值：
  
  1. $$
     \begin{flalign}
     &
     \lim_{x \to \pi} \cos x = \cos \pi = -1
     &
     \end{flalign}
     $$
  
  2. $$
     \begin{flalign}
     &
     \lim_{x \to 3} \frac{x - 3}{x^2 +x - 12} = \frac{1}{7}
     &
     \end{flalign}
     $$
  
  3. $$
     \begin{flalign}
     &
     \lim_{x \to 4} \frac{\sqrt x - 2}{x - 4} =
     &
     \end{flalign}
     $$
  
  4. $$
     \begin{flalign}
     &
     \lim_{x \to \infty} \frac{5 - x^2}{2x^2 + 1} =
     &
     \end{flalign}
     $$
  
  5. $$
     \begin{flalign}
     &
     \lim_{x \to 0} \frac{\sin(5x)}{\sin(2x)} =
     &
     \end{flalign}
     $$
  
  6. $$
     \begin{flalign}
     &
     \lim_{x \to 0} \frac{x}{1 - \cos x} \text{（提示：三角恒等变换）}
     =
     &
     \end{flalign}
     $$
     
  7. $$
     \begin{flalign}
     &
     \lim_{x \to \infty} (1 + \frac{1}{2x})^x
     \text{（提示：$\lim_{x \to \infty} (1 + \frac{1}{x})^x $）}
     = e
     &
     \end{flalign}
     $$
  
* d. 已知分段函数 
  
  $$
  \begin{flalign}
  &
  g(x) = 
  \begin{cases}
  \frac{\sin x}{x} & x \neq 0 \\
  1 & x = 0
  \end{cases}
  &
  \end{flalign}
  $$
  
  证明函数 $g(x)$ 在其定义域内处处连续 .

### 2. 导数部分：

* a. 仿照 $x(t) \rightarrow 求导 \frac{d}{dt} \rightarrow \frac{dx}{dl} = x'(t) = v(t)$ 的形式举2个类似的导数式子 .

* b. 使用极限的数学语言证明下列法则：
  
  1. 导数加法法则
  
  2. 导数乘法法则
  
  3. 导数除法法则

  4. 导数链式法则
  
* c. 根据线性函数的定义说明一次函数 $f(x) = kx + b$ 是否是线性的 .

* d. 设函数 $f(x) = x(x + 1)(x + 2)\cdots(x + n)$ ， $n \in N_+$ ，求 $f'(0)$ . （提示：多项式展开）

* e. 设函数 $f(x) = \sin(x^2)$ ，求 $f^{(3)}(x)$ .

* f. 设函数 $f(x) = \ln(\frac{2}{x})$，求 $f'(x)$ .

* g. 设函数 $f(x) = a^x$ ， $g(x) = x^x$ ，求 $f'(x)$ 和 $g'(x)$ .

* h. 弹簧以平衡位置为中心做往返的周期运动，这种运动叫简谐振动，其位移 $x$ 和时间 $t$ 的关系是 $x(t) = A \sin(\omega x + \phi_0)$ ，利用导数知识求速度和加速度的表达式 $v(t)$ 和 $a(t)$ .

### 3. 积分部分：

* a. 用黎曼和的形式表示下列物理量：
  
  1. 匀速直线运动 $t_1$ 到 $t_2$ 时间内的位移
  
  2. 变力 $F(x)$ 从 $x_1$ 到 $x_2$ 做的功

* b. 计算下列不定积分：
  
  1. $$
     \begin{flalign}
     &
     \int (5x^4 - 3x^2 + 2) dx
     &
     \end{flalign}
     $$
  
  2. $$
     \begin{flalign}
     &
     \int (4\cos x - 3\sin x) dx
     &
     \end{flalign}
     $$

  3. $$
     \begin{flalign}
     &
     \int \frac{1}{\sqrt{x}} dx
     &
     \end{flalign}
     $$
  
  4. $$
     \begin{flalign}
     &
     \int (2e^x + 3\ln x) dx
     &
     \end{flalign}
     $$
  
  6. $$
     \begin{flalign}
     &
     \int e^{2x} dx
     &
     \end{flalign}
     $$
  
* c. 计算下列定积分：
  
  1. $$
     \begin{flalign}
     &
     \int_0^1 (x^2 + 1) dx
     &
     \end{flalign}
     $$
  
  2. $$
     \begin{flalign}
     &
     \int_0^{\pi} \sin x dx
     &
     \end{flalign}
     $$
  
  3. $$
     \begin{flalign}
     &
     \int_1^e \frac{1}{x} dx
     &
     \end{flalign}
     $$
  
  4. $$
     \begin{flalign}
     &
     \int_0^2 (x^3 - 2x) dx
     &
     \end{flalign}
     $$
  
  5. $$
     \begin{flalign}
     &
     \int_0^{\pi/2} \cos x dx
     &
     \end{flalign}
     $$
  
  6. $$
     \begin{flalign}
     &
     \int_1^4 \frac{1}{x} dx
     &
     \end{flalign}
     $$
  
* d. 用换元法计算下列不定积分：
  
  1. $$
     \begin{flalign}
     &
     \int \cos(3x) dx
     &
     \end{flalign}
     $$
  
  2. $$
     \begin{flalign}
     &
     \int \frac{1}{2x+1} dx
     &
     \end{flalign}
     $$
  
  3. $$
     \begin{flalign}
     &
     \int 2x(x^2+1)^3 dx
     &
     \end{flalign}
     $$
  
  4. $$
     \begin{flalign}
     &
     \int \cos(x) \cos(2x) dx
     &
     \end{flalign}
     $$
  
* e. 用分部积分法计算下列不定积分：
  
  1. $$
     \begin{flalign}
     &
     \int x\cos x dx
     &
     \end{flalign}
     $$
  
  2. $$
     \begin{flalign}
     &
     \int \ln x dx
     &
     \end{flalign}
     $$
  
* f. 物理应用题：
  
  1. 质点的加速度 $a(t) = 2t + 1 (m/s²)$ ，初速度 $v_0 = 2m/s$ ，求 $t = 3s$ 时的速度 .
  
  2. 质点的速度 $v(t) = 3t^2 + 2t (m/s)$ ，求在 $t = 0$ 到 $t = 2s$ 内的位移 .
  
  3. 弹簧的弹力 $F(x) = -kx$，求弹簧从伸长量 $x_1$ 压缩到 $x_2$ 时弹力做的功 .
  
  4. 电流 $I(t) = I_0\sin(\omega t)$，求在 $t = 0$ 到 $t = \frac{\pi}{\omega}$ 时间内通过导体的电荷量 .
