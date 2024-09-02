+++
title = ' 絶対値の和の不等式'
date = 2024-09-01T22:54:39+09:00
draft = false
tags = ['数学','高校数学']
+++
よく高校数学で，例えば $|x-7|+|x-8|\leqslant 3$ となる $x$ の範囲を求める問題とかあるが，その際に使えるテクニックについて紹介する．
本質的には場合分けをするのと変らないので，単に時短テクである．

{{<thmbox title="命題">}}
$(X,\|\cdot\|)$ をノルム空間とする．
このとき，任意の $x,y\in X,a\in\mathbb{R}$ に対して
$$
\|x\|+\|y\|\leqslant a\quad\Longleftrightarrow\quad
\begin{cases}
\|x+y\|\leqslant a \\
\|x-y\|\leqslant a
\end{cases}
$$
が成り立つ．
{{</thmbox>}}

**証明**  
$\Rightarrow$ は三角不等式より明らかである．
逆も
$$
\|x\|+\|y\|=\frac{\|(x+y)+(x-y)\|}{2}+\frac{\|x+y-(x-y)\|}{2}
$$
と分解して三角不等式を用いればよい．
{{<qed>}}

これを認めると，冒頭の不等式は $|2x-15|\leqslant 3$ と同値なので $-6\leqslant x\leqslant 9$ が答えとすぐにわかる．
