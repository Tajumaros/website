+++
title = '３回合成して恒等写像になる実数上の函数'
date = 2024-08-30T06:54:10+09:00
draft = false
tags = ['math']
+++
{{<thmbox title="命題">}}
実数上の連続函数 $f\colon\mathbb{R}\to\mathbb{R}$ で，$f\circ f\circ f=\mathrm{id}$ となるものは，恒等写像のみ．
{{</thmbox>}}

**証明**  
$f^{-1}=f^2$ となり，$f$ は全単射である．
よって，連続性より $f$ は狭義単調である．
議論は同様であるので，狭義単調増加のときのみ考える．
これから，任意の $x\in\mathbb{R}$ に対して $f(x)=x$ であることを背理法で示す．
もし $x\lt f(x)$ となる $x\in\mathbb{R}$ があるならば，仮定から
$$
x\lt f(x)\lt f^2(x)\lt f^3(x)=x
$$
となり矛盾する．
$x\gt f(x)$ の場合も同様である．
以上で示したいことがすべて示された．
{{<qed>}}
