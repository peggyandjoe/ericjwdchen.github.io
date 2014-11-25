---
layout: post
title: "Mathematical Induction: Divisibility by 7 Example"
link:
---

Prove that \\(3^{2n+1}+2^{n+2}\\) is divisible by \\(7\\) for every nonnegative integer \\(n\\).

<hr>

Let \\(P(n)\\) be: \\(3^{2n+1}+2^{n+2}\\) is divisible by \\(7\\).

We wish to show that \\(P(n)\\) is true \\(\forall n \geq0\\).

We first verify the base \\(n=0\\) case:
\\[3^{2\times0+1}+2^{0+2}=3^1+2^2=7\\]
\\[1 \times 7 = 7\\]

We wish to show that \\(P(k)\implies P(k+1) \, \forall k \geq 0\\).

We assume \\(P(k)\\) to be true for some \\(k \geq 0\\).

Thus \\(7q=3^{2k+1}+2^{k+2}\\) for some \\(q \in \mathbb{Z}\\).

Consider \\(3^{2(k+1)+1}+2^{(k+1)+2}&=3^{(2k+1)+2}+2^{(k+2)+2}\\)

$$
\begin{align*}
& 3^{2(k+1)+1}+2^{(k+1)+2} \\
&= 3^{(2k+1)+2}+2^{(k+2)+1} \\
&= 3^{2}(3^{2k+1})+2^{1}2^{k+2} \\
\end{align*}
$$

$$
\begin{eqnarray*}
{a + b + c + d + e + f + g + h}\nonumber\\
  & = & i + j + k + l + m \\
  & = & n + o + p + q + r + s
  \end{eqnarray*}

$$
