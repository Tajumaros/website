+++
title = '３回合成して自分自身になる実数上の函数'
date = 2024-08-30T06:54:10+09:00
draft = false
tags = ['math']
+++

$$
    \begin{align}
        L(C_1y_1 + C_2y_2)
        &= \frac{{\rm d}^2}{{\rm d}x^2}(C_1y_1 + C_2y_2) + p(x)\frac{{\rm d}}{{\rm d}x}(C_1y_1 + C_2y_2) + q(x)(C_1y_1 + C_2y_2) \\
        &= C_1\left(\frac{{\rm d}^2y_1}{{\rm d}x^2} + p(x)\frac{{\rm d}y_1}{{\rm d}x} + q(x)y_1\right) + C_2\left(\frac{{\rm d}^2y_2}{{\rm d}x^2} + p(x)\frac{{\rm d}y_2}{{\rm d}x} + q(x)y_2\right) \\
        &= C_1L(y_1) + C_2L(y_2)
    \end{align}
$$

{{<thmbox title="ピタゴラスの定理">}}
直角三角形において、斜辺の二乗は他の二辺の二乗の和に等しい。
{{</thmbox>}}