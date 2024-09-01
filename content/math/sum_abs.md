+++
title = '$|X|+|Y|\leqslant a$ 型の不等式'
date = 2024-09-01T22:54:39+09:00
draft = false
tags = ['math', 'high-school']
+++
よく高校数学で，例えば $|x-7|+|x-8|\leqslant 3$ となる $x$ の範囲を求める問題とかあるが，その際に使えるテクニックについて紹介する．
本質的には場合分けをするのと変らないので，単に時短テクである．

{{<thmbox title="命題">}}
$X,Y,a\in\mathbb{R}$ とするとき，
$$
|X|+|Y|\leqslant a\quad\Longleftrightarrow\quad
\begin{cases}
|X+Y|\leqslant a \\
|X-Y|\leqslant a
\end{cases}
$$
が成り立つ．
{{</thmbox>}}

**証明**  
$x\in\mathbb{R}$ のとき，$|x|=\max\{x, -x\}$ であることに注意する．
よって，
$$
\begin{align}
&|X|+|Y|\leqslant a \\
\Longleftrightarrow &\max\{X, -X\}+\max\{Y, -Y\}\leqslant a \\
\Longleftrightarrow &\max\{X+Y, X-Y, -X+Y, -X-Y\}\leqslant a \\
\Longleftrightarrow &\max\{X+Y, -(X+Y)\}+\max\{X-Y, -(X-Y)\}\leqslant a \\
\Longleftrightarrow &|X+Y|+|X-Y|\leqslant a
\end{align}
$$
となる．
{{<qed>}}

これを認めると，冒頭の不等式は $|2x-15|\leqslant 3$ と同値なので $-6\leqslant x\leqslant 9$ が答えとすぐにわかる．
