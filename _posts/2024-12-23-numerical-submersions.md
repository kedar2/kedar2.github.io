---
title: 'Numerical submersions'
date: 2024-12-23
permalink: /posts/2024/12/23/numerical-submersions/
tags:
  - manifolds
  - optimization
share: false
---

Let $m \geq n$, and let $f: \mathbb{R}^m \to \mathbb{R}^n$ be a submersion. Then $f$ is not necessarily surjective. Consider, for example, $m = n = 1$, and $f(x) = \arctan(x)$. But this function fails to be surjective for a boring reason: it has a vanishing gradient as $x \to \infty$.

Let's refine our question. Suppose that for all $x \in \mathbb{R}^m$, $\sigma_n(Df(x)) \geq C$ for some $C > 0$. That is, the singular values of the derivative of $f$ are uniformly bounded below by $C$. Does it now follow that $f$ is surjective? Let $y_1 \in \mathbb{R}^n$. We would like to find $x_1 \in \mathbb{R}^m$ that maps to $y_1$. We can think of this as *training* $f$ to compute $y_1$. We can do this by minimizing the function

{: .text-center}
$L(x)=\frac{1}{2}\\|f(x)-y_1\\|^2$

with the gradient flow

{: .text-center}
$\dot{x}(t) =-\nabla L(x(t))$.

and an arbitrary initialization $x_0 \in M$. Then

{: .text-center}
$$
\begin{align*}
\frac{d}{dt} L(x(t)) &= \nabla L(x(t)) \cdot \dot{x}(t)\\
&= - \|\nabla L(x(t))\|^2\\
&= -\|Df(x) \cdot (f(x)-y_1)\|^2\\
&\leq - C^2 \|f(x)-y_1\|^2\\
&= -2 C^2 L(x(t)).
\end{align*}
$$

So the loss decays exponentially:

{: .text-center}
$$
\begin{align*}
L(x(t)) \leq L(x_0) e^{-2 C^2 t}.
\end{align*}
$$

In particular, $L(x(t)) \to 0$ as $t \to \infty$ so $f(x(t)) \to y_1$ as $t \to \infty$. With a little bit more work, we can find a limit point $x_1$ of this path and show that $f(x_1) = y_1$. Hence, $f$ is surjective.

I came across this question when I was studying the optimization dynamics of a model. I wondered about what would happen if there was no global minimizer to converge to. It turns out that good local optimization is strictly stronger than good expressivity.