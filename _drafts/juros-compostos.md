---
layout: post
title:  "Interests and Formulas"
date:   2018-08-06 09:00:00 -0300
categories: math, finances
---

Esse post vale pro Brasil.
É comum achar blogs e canais que ensinam formas melhores de investir
e lidar com dinheiro, mas é difícil achar as fórmulas.
Sob o risco de perder leitores acrescentando fórmulas ao site, vamos lá

Suponha que vc trabalhou por anos e juntou o incrível montante $M_0$,
do qual você irá viver.
Esse dinheiro rende a uma taxa de $i$ ao ano, que também pode ser escrita como $r=1+i$.
Além disso você gasta $a$ por ano, desse dinheiro.

Após um ano, você terá

$$ M_1 = (M_0 - a) r $$


Após $t$ anos, você terá

$$ M_t = (M_{t-1} - a) r $$

Vamos resolver essa relação de recorrência, primeiro eliminamos
o termo linear (independente de $t$) do sistema

$$
M_t = M_{t-1}r - a r \\
M_{t-1} = M_{t-1} r - a r
$$

Encontramos

$$
M_t = M_{t-1}(1+r) - M_t r
$$

Escrevemos como uma matriz

$$
\begin{pmatrix} M_{t} \\ M_{t-1} \end{pmatrix}
=
\begin{pmatrix} 1+r & r \\ 1 & 0 \end{pmatrix}
\begin{pmatrix} M_{t-1} \\ M_{t-2} \end{pmatrix}
$$

E o resultado final é

$$
\begin{pmatrix} M_{t} \\ M_{t-1} \end{pmatrix}
=
\begin{pmatrix} 1+r & r \\ 1 & 0 \end{pmatrix}^{t-1}
\begin{pmatrix} M_{1} \\ M_{0} \end{pmatrix}
$$

É interessante observar que esse sistema depende
de $M_1$ e $M_0$, toda a informação sobre os saques $a$,
está em $M_1$.

Then we find

$$
M_t = M_0 r^t - a r \frac{1-r^t}{1-r}
$$

According to Wolfram Alpha, expectativa de vida ($V$) no Brasil é de 73.9 anos.

O mesmo cálculo vale para aportes anuais de $w$, partindo do zero.

$$
M_t = w r \frac{1-r^t}{1-r}
$$

