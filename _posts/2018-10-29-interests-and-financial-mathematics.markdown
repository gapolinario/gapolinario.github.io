---
layout: post
title:  "Interests and Financial Mathematics"
date:   2018-10-29 15:00:00 -0300
categories: math, finances
---

There are several blogs and internet channels teaching
best ways to invest and deal with money, both it is hard to
see the formulas involved. Though there are some web simulations
of specific applications.

What I'm going to do is describe the earnings of
a certain application, with the assumption that they
occur at a fixed rate. These calculations work for retirement,
where one has collected the amount $M_0$ and intends on living from its
earnings, or for someone starting to build this estate.

# Regular Deposits

If you make regular deposits of $w$, at interest $r$,
at the end of $t$ periods the total amount is

$$
M_t = w r^{t} + w r^{t-1} + \cdots + w r^2 + w r
$$

which is simply the sum of a geometric progression and can
be written

$$
M_t = w r \frac{1-r^t}{1-r}
$$

# Retirement

Suppose you have a starting amount $M_0$, invested with a yearly return rate of $i$,
also written as $r=1+i$, and the yearly expenses are $a$.
After one year, you're going to have

$$ M_1 = (M_0 - a) r $$

After $t$ years, the amount you're going to have is

$$ M_t = (M_{t-1} - a) r $$

This is a non-homogenous recurrence relation, and it can be solved
with the method of [symbolic differentiation][wiki].
We write the system of equations

$$
M_t = r M_{t-1} - a r \\
M_{t-1} = r M_{t-2} - a r
$$

And subtract both equations to find

$$
M_t = (1+r) M_{t-1} - r M_{t-2}
$$

Then write it as a matrix

$$
\begin{pmatrix} M_{t} \\ M_{t-1} \end{pmatrix}
=
\begin{pmatrix} 1+r & -r \\ 1 & 0 \end{pmatrix}
\begin{pmatrix} M_{t-1} \\ M_{t-2} \end{pmatrix}
$$

Then we can find the value at any time $t$,
which is

$$
\begin{pmatrix} M_{t} \\ M_{t-1} \end{pmatrix}
=
\begin{pmatrix} 1+r & -r \\ 1 & 0 \end{pmatrix}^{t-1}
\begin{pmatrix} M_{1} \\ M_{0} \end{pmatrix}
$$

The $(t-1)$-th power can be computed if we diagonalize this matrix.
Its eigenvalues are $1$ and $r$ and we find

$$
\begin{pmatrix} M_{t} \\ M_{t-1} \end{pmatrix}
=
\begin{pmatrix} 1 & r \\ 1 & 1 \end{pmatrix}
\begin{pmatrix} 1^{t-1} & 0 \\ 0 & r^{t-1} \end{pmatrix}
\begin{pmatrix} \frac{1}{1-r} & -\frac{r}{1-r} \\ -\frac{1}{1-r} & \frac{1}{1-r} \end{pmatrix}
\begin{pmatrix} M_{1} \\ M_{0} \end{pmatrix}
$$

$$
M_t = M_0 r^{t} - a r \frac{1-r^{t}}{1-r}
$$

One can live off these earnings forever if the amount never decreases,
this happens if, at every year,

$$
M_t \geq M_{t-1}
$$

where we consider real rates of growth (inflation has been discounted).
And this means you can spend at most

$$
a = M_{t-1} \frac{r-1}{r}
$$

at every year to maintain your assets. This means one cannot spend more
than the fraction $i/r$ of its assets.

# Building Assets

The same calculations are valid if one makes regular deposits of $w$,
where $w$ and $a$ have the same role, but the former accompanies minus signs, because it is an expense, whereas $w$ is a deposit.

$$
M_t = M_0 r^{t} + w r \frac{1-r^{t}}{1-r}
$$


[wiki]: https://en.wikipedia.org/wiki/Recurrence_relation