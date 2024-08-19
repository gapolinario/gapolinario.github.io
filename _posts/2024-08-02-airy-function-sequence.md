---
layout: post
title:  "The Airy function and a sequence of permutations"
date:   2024-08-02 17:00:00 +0200
categories: math, oeis
---

Let's explore the connection between the Airy function and the integer sequence [A052502](https://oeis.org/A052502).

The Airy function is defined as

$$
\mathrm{Ai}(x) = \int_{-\infty}^{\infty} \frac{d\tau}{2\pi} e^{-i\tau x - i \tau^3/3},
$$

therefore its Fourier transform is (see [Wikipedia](https://en.wikipedia.org/wiki/Airy_function#Fourier_transform))

$$
\int_{-\infty}^{\infty} e^{i\tau x} \mathrm{Ai}(x) \, \mathrm{d}x = e^{-i \tau^3/3}.
$$


Let $a_n$, with $n \in \mathbb{N}_0$, be the terms in the sequence A052502. The first identity we will show is

\begin{equation}
a_n = 3 \int_0^{\infty} x^{3n} \mathrm{Ai}(x) \, \mathrm{d}x
\label{eq:airy_positive}
\end{equation}

A generalization of this identity to real values of $n$ is in the [DLMF](https://dlmf.nist.gov/9.10#E17), but the connection to the above integer sequence is not mentioned.

To prove Eq. \ref{eq:airy_positive}, use the same strategy as in [this proof](https://math.stackexchange.com/a/2332853/595069) of

$$
\int_0^{\infty} \mathrm{Ai}(x) \, \mathrm{d}x = \frac13 .
$$


Say $H$ is the Heaviside step function, then

$$
\int_0^{\infty} x^{3n} \mathrm{Ai}(x) \, \mathrm{d}x = \int_{-\infty}^{\infty} x^{3n} H(x) \mathrm{Ai}(x) \mathrm{d}x .
$$

Using a limiting representation for the step function,

$$
H(x) \Big\lvert_{x \neq 0} = \lim_{\varepsilon \to 0^+} \int_{-\infty}^{\infty} \frac{e^{i \tau x}}{\tau - i \varepsilon} \frac{\mathrm{d}\tau}{2\pi i},
$$

we obtain

$$
\int_0^{\infty} x^{3n} \mathrm{Ai}(x) \mathrm{d}x = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} \frac{e^{i \tau x}}{\tau - i 0^+} \frac{\mathrm{d}\tau}{2\pi i} x^{3n} \mathrm{Ai(x)} \, \mathrm{d}x.
$$

Notice that

$$
\int_{-\infty}^{\infty} e^{i \tau x}  x^{3n} \mathrm{Ai(x)} \mathrm{d}x = (-i)^{3n} \frac{\mathrm{d}^{3n}}{\mathrm{d} \tau^{3n}} \int_{- \infty}^{\infty} e^{i \tau x} \mathrm{Ai(x)} \mathrm{d}x.
$$

So, exchanging the order of the integrals,

$$
\begin{split}
\int_0^{\infty} x^{3n} \mathrm{Ai}(x) \mathrm{d}x
&= \int_{-\infty}^{\infty} \frac{1}{\tau - i 0^+} \left[ \int_{-\infty}^{\infty} e^{i \tau x}  x^{3n} \mathrm{Ai(x)} \mathrm{d}x\right] \frac{\mathrm{d}\tau}{2\pi i} \\
&= \int_{-\infty}^{\infty} \frac{1}{\tau - i 0^+} \left[ (-i)^{3n} \frac{\mathrm{d}^{3n}}{\mathrm{d} \tau^{3n}} e^{-i \tau^3/3} \right] \frac{\mathrm{d}\tau}{2\pi i}.
\end{split}
$$

The term in brackets is equal to

$$
B_{3n}(0,0,2,0,\cdots,0) \, e^{-i \tau^3/3} =
\frac{\mathrm{d}^{3n}}{\mathrm{d} t^{3n}} e^{t^3/3}
= (-i)^{3n} \frac{\mathrm{d}^{3n}}{\mathrm{d} \tau^{3n}} e^{-i \tau^3/3}
$$

where $B$ is a complete exponential [Bell polynomial](https://en.wikipedia.org/wiki/Bell_polynomials).

It is interesting to notice that $B_{3n}(0,0,2,0,\cdots,0)$ is equal to the terms in the sequence A052502. To show that, we prove that the recursion relation for this Bell polynomial coincides with the recursion relation for the sequence, which is:

$$
\begin{split}
a_{n+1} &= (3n+2)(3n+1) a_n, \\
a_0 &= 1
\end{split}
$$

First, notice that $B_0 = a_0 = 1$.
And the general recursion relation for Bell polynomials, applied to our case, is

$$
B_{3n+3}(0,0,2,0,\cdots,0) = \sum_{i=0}^{3n+2} \binom{3n+2}{i} B_{3n+2-i}(0,0,2,0,\cdots,0,x_{3n+2-i}) x_{i+1}.
$$

But only one of the $x_i$ is different from zero, $x_3 = 2$, which makes $i=2$. Therefore,

$$
\begin{split}
B_{3n+3}(0,0,2,0,\cdots,0) &= 2 \binom{3n+2}{2} B_{3n}(0,0,2,0,\cdots,0) \\
&= (3n+2)(3n+1) B_{3n}(0,0,2,0,\cdots,0).
\end{split}
$$

And this shows that $a_n = B_{3n}(0,0,2,0,\cdots,0)$.

Let's go back to proving eq. \ref{eq:airy_positive}. With this identity for Bell polynomials, we write

$$
\int_0^{\infty} x^{3n} \mathrm{Ai}(x) \mathrm{d}x = a_n \times \int_{-\infty}^{\infty} \frac{e^{-i \tau^3/3}}{\tau - i 0^+} \frac{\mathrm{d}\tau}{2\pi i}.
$$

The same integral was needed in the original proof and is equal to 1/3. Therefore, we conclude that

$$
3 \int_0^{\infty} x^{3n} \mathrm{Ai}(x) \mathrm{d}x = a_n
$$


Next, we'll show another formula that connects the Airy function and this sequence:

\begin{equation}
a_n = \int_{-\infty}^{\infty} x^{3n} \mathrm{Ai}(x) \, \mathrm{d}x
\label{eq:airy_real}
\end{equation}


First notice the similarity between the two formulas below

\begin{equation}
a_n
=  \int_{-\infty}^{\infty} x^{3n} \mathrm{Ai}(x) \, \mathrm{d}x = 
3 \int_0^{\infty} x^{3n} \mathrm{Ai}(x) \mathrm{d}x
\label{eq:airy_both}
\end{equation}

and

\begin{equation}
1
=  \int_{-\infty}^{\infty} \mathrm{Ai}(x) \, \mathrm{d}x = 
3 \int_0^{\infty} \mathrm{Ai}(x) \mathrm{d}x
\label{eq:airy_norm}
\end{equation}

\ref{eq:airy_norm} is a special case of \ref{eq:airy_both} and is one of the basic properties of the Airy function.

To show this second identity, we'll use the Dirac delta function instead of the Heaviside:

$$
1 = \int_{-\infty}^{\infty} \delta(\tau) e^{i \tau x} \, \mathrm{d}\tau.
$$

The rest of the proof is very similar:

$$
\begin{split}
\int_{-\infty}^{\infty} x^{3n} \mathrm{Ai}(x) \mathrm{d}x
&= \int_{-\infty}^{\infty} \left[ \int_{-\infty}^{\infty}  \delta(\tau) e^{i \tau x} \mathrm{d}\tau \right] x^{3n} \mathrm{Ai(x)} \, \mathrm{d}x \\
&= \int_{-\infty}^{\infty} \delta(\tau) \left[ \int_{-\infty}^{\infty} e^{i \tau x} x^{3n} \mathrm{Ai(x)} \mathrm{d}x \right] \, \mathrm{d}\tau \\
&= \int_{-\infty}^{\infty} \delta(\tau) (-i)^{3n} \frac{\mathrm{d}^{3n}}{\mathrm{d}\tau^{3n}} e^{-i \tau^3/3} \, \mathrm{d}\tau \\
&= a_n \times \int_{-\infty}^{\infty} \delta(\tau) e^{-i \tau^3/3} \, \mathrm{d}\tau \\
&= a_n
\end{split}
$$


Since $y^n$ is a basis of functions in $\mathbb{R}$, one could naively say that

\begin{equation}
\int_{-\infty}^{\infty} F(x) \mathrm{Ai}(x) \, \mathrm{d}x = 3 \int_0^{\infty} F(x) \mathrm{Ai}(x) \, \mathrm{d}x
\label{eq:naive} 
\end{equation}

for any analytic function $F$. This is however *wrong*, and can be shown with a counterexample:
With $F(x) = e^{-x^2}$, both integrals can be computed analytically, and their difference is

$$
\int_{-\infty}^{\infty} e^{-x^2} \mathrm{Ai}(x) \, \mathrm{d}x - 3 \int_0^{\infty} e^{-x^2} \mathrm{Ai}(x) \, \mathrm{d}x \approx -0.0003168
$$

The analytical result was computed with Mathematica and confirmed with a numerical integration, using the `quad` and `quadosc` functions of the [mpmath library](https://mpmath.org/doc/current/calculus/integration.html#mpmath.quadosc). One can also see this difference with eqs. 9.10.14-15 of the [DLMF](https://dlmf.nist.gov/9.10) .

However, one could ask if the identity \ref{eq:naive} is only valid for polynomials or if there is any other analytic function, with an infinite number of terms in its expansion, for which this is valid.

The code for the analytical and numerical computations above is available [on Github](https://gist.github.com/gapolinario/d9417081dbbc156cca18f3199e282348).

**A proof from Olver**

Let us look at another proof, that does not involve distributions.

We'll compute the negative side of this integral:

$$
I(p) = \int_{-\infty}^0 x^{3p} \mathrm{Ai}(x) \mathrm{d}x.
$$

And the positive side is found in the [DLMF](https://dlmf.nist.gov/9.10#E17):

$$
\int_0^{\infty} x^{3p} \mathrm{Ai}(x) \mathrm{d}x = \frac{(3p)!}{3^{p+1} p!}.
$$

To compute $I(p)$, let us start with the function

$$
F(x) = \int_0^{\infty} \mathrm{Ai}(-xv) f(v) \mathrm{d}v.
$$

Repeated partial integrations produce (See Olver, Ref. 1, Chap 9, Example 8.1, p. 342):

$$
\begin{split}
F(x)
&= \left[ - \frac{A_1(xv)}{x} f(v) - \frac{A_2(xv)}{x^2} f'(v) - \cdots - \frac{A_n(xv)}{x^n} f^{(n-1)}(v)\right]_0^{\infty} \\
&+ \frac{1}{x^n} \int_0^{\infty} A_n(xv) f^{(n)}(v) \mathrm{d}v,
\end{split}
$$

where

$$
A_1(v) = \int_v^{\infty} \mathrm{Ai}(-t) \mathrm{d}t, \qquad \text{and} \qquad  
A_s(v) = \int_v^{\infty} A_{s-1}(t) \mathrm{d}t, \ s \geq 2.
$$

On p. 344 of the same reference we find an expression which will be useful:

$$
A_s(0) = \frac{2 \cos\left(\tfrac13 (s-1) \pi\right)}{3^{(s+2)/3} \Gamma\left(\frac13 s + \frac23\right)}
$$

Now, we set $f(v)=(−v)^{3p}$, $x=1$, and start with $p=0$:

$$
\begin{split}
I(p=0)
&= F(x=1) \\
&= \left[ - A_1(v) f(v) \right]_0^{\infty} + \int_0^{\infty} A_1(v) f^{(1)}(v) \mathrm{d}v \\
&= \left[ - A_1(v) f(v) \right]_0^{\infty} \\
&= - A_1(\infty) f(\infty) + A_1(0) f(0) \\
&= \frac23
\end{split}
$$

This matches what we [already knew](https://dlmf.nist.gov/9.10#E11).

In general,

$$
f^{(3p)}(v) = (-1)^{3p} (3p)!,
$$

and

$$
\begin{split}
I(p)
&= \int_0^{\infty} \mathrm{Ai}(-v) (-v)^{3p} \mathrm{d}v \\
&= A_{3p+1}(0) f^{(3p)}(0) \\
&= (-1)^{3p} A_{3p+1}(0) \times (3p)!
\end{split}
$$

Gathering the expression for $A$, we end with

$$
I(p) = \frac23 \frac{(3p)!}{3^{p} p!},
$$

and together with the positive integral, we have the final expression for 
sequence [A052502](https://oeis.org/A052502):

$$
\int_{-\infty}^{\infty} x^{3p} \mathrm{Ai}(x) dx = \frac{(3p)!}{3^{p} p!},
$$

The integral $I(p)$ can also be used to show that

$$
\int_{-\infty}^{\infty} x^{n} \mathrm{Ai}(x) dx = 0 , \ \text{if $n$ is an integer and not a multiple of 3}.
$$

Observe that

$$
\cos( n \pi/3) = 
\begin{cases}
(-1)^p, &\text{if $p$ is an integer and $n=3p$}, \\
(-1)^p/2, &\text{if $n=3p+1$} \\
(-1)^{p+1}/2, &\text{if $n=3p+2$} \\
\end{cases}
$$

Therefore, if $n=3p+1$

$$
\begin{split}
\int_{-\infty}^{\infty} x^n \mathrm{Ai}(x) \mathrm{d}x
&= I(n) + \frac{n!}{3^{n/3+1} (n/3+1)!} \\
&= \left( (-1)^{p+n} + 1 \right) \frac{n!}{3^{n/3+1} (n/3+1)!}
\end{split}
$$

which is zero for any integer $p$. The same happens if $n=3p+2$.

**An attempt at a proof**

Using eq. 9.10.10 of the  [DLMF](https://dlmf.nist.gov/9.10#E10), integrated over the real line, we can try another alternative proof:

$$
\begin{split}
\int_{\mathbb{R}} x^{3n+3} \mathrm{Ai}(x) \, \mathrm{d}x
&= x^{3n+2} \mathrm{Ai}'(x) \Big\lvert_{-\infty}^{\infty} - (3n+2) x^{3n+1} \mathrm{Ai}(x) \Big\lvert_{-\infty}^{\infty} \\
&+ (3n+1) (3n+2) \int_{\mathbb{R}} x^{3n} \mathrm{Ai}(x) \, \mathrm{d}x
\end{split}
$$

It is easy to show that

$$
\lim_{x \to \infty} x^{3n+2} \mathrm{Ai}'(x) - (3n+2) x^{3n+1} \mathrm{Ai}(x)= 0,
$$

but not as easy for the lower term:

$$
\lim_{x \to -\infty} x^{3n+2} \mathrm{Ai}'(x) - (3n+2) x^{3n+1} \mathrm{Ai}(x) \overset{?}{=} 0
$$


However we can use the same identity, with 0 as the lower limit, to show eq. \ref{eq:airy_positive}. As a result, we obtain the recursion relation for the [A052502](https://oeis.org/A052502) sequence.


**References**

1. Olver, F. (1997). _Asymptotics and special functions_. AK Peters/CRC Press. 
