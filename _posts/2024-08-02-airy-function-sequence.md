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

**Another proof**

Using eq. 9.10.10 of the  [DLMF](https://dlmf.nist.gov/9.10#E10), integrated over the real line, we can try an alternative proof:

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


