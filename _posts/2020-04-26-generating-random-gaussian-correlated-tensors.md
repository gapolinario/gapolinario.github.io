---
layout: post
title:  "Generating Random Gaussian Correlated Tensors"
date:   2020-04-24 14:00:00 -0300
categories: physics
---

The Recent Fluid Deformation model for Lagrangian velocity gradients in turbulent flows was introduced in [Chevillard and Meneveau (2016)][prl-rfd]. It is a stochastic model which reproduces many statistical trends of the velocity gradient tensor. Here, I am interested in the generation of the tensorial noise, $W_{ij}(t)$, where the indices run from 1 to 3, representing the spatial dimensions of the problem.

The tensorial noise is Gaussian, hence it can be defined by its mean
$$ \langle W_{ij}(t) \rangle = 0 $$
and by its autocovariance matrix
$$ \langle W_{ij}(t) W_{kl}(t') \rangle = G_{ijkl} \delta(t-t') $$.
The tensor $ \mathbf{G}$ is the only possible choice for an isotropic, homogeneous and traceless tensorial field:

$$ G_{ijkl} = 2 \delta_{ik} \delta_{jl} - \frac12 \delta_{ij} \delta_{kl} - \frac12 \delta_{il} \delta_{jk} $$

To generate noise with a given autocovariance matrix, the Cholesky decomposition method can be applied. The Cholesky decomposition is an algorithm which breaks down the $$ \mathbf{G} $$ tensor into the product $$ \mathbf{G} = \mathbf{L} \mathbf{L}^* $$, where $\mathbf{L}$ is a lower triangular matrix and $ \mathbf{L}^* $ is its Hermitian conjugate.

Then, one can generate an array of i.i.d. standard Gaussian random variables, which we call $z$. The product $x = \mathbf{L} z$ has the desired statistical properties. Using the statistical properties of $z$:

$$ \langle z_i \rangle = 0 \ \mbox{and} \ \langle z_i z_j \rangle = \delta_{ij} $$

$$ \langle x_i \rangle = \sum_j L_{ij} \langle z_j \rangle = 0 $$

$$ \langle x_i x_j \rangle = \sum_k \sum_l L_{ik} L_{jl} \langle z_k z_l \rangle =  \sum_k L_{ik} L_{kj}^* = G_{ij} $$

But this method can only be applied for positive-definite matrices, which is not the case for this autocovariance. This has been tested on Mathematica by creating the explicit autocovariance tensor:

```Mathematica
G = ConstantArray[0, {9, 9}];

Do[G[[3 i + j + 1, 3 k + l + 1]] = 
  2 KroneckerDelta[i, k] KroneckerDelta[j, l] - 
   1/2 KroneckerDelta[i, l] KroneckerDelta[j, k] - 
   1/2 KroneckerDelta[i, j] KroneckerDelta[k, l], {i, 0, 2}, {j, 0, 
  2}, {k, 0, 2}, {l, 0, 2}]

Eigenvalues[G]
```

In this code, the 4-dimensional tensor was transformed into a 2-dimensional tensor by joining some of the coordinates, so that standard linear algebra algorithms can be applied.

It is found that one of the eigenvalues of $ \mathbf{G} $ is zero, while all the others are positive, hence $ \mathbf{G} $ is not positive-definite. But a similar decomposition, the LDL decomposition, can be performed. It splits a matrix into a lower triangular matrix, an upper triangular matrix, and a diagonal matrix, as $ \mathbf{G} = \mathbf{L} \mathbf{D} \mathbf{L}^* $.

The Mathematica implementation of LDL decomposition algorithm is from this [Stack Exchange question][matha-ldl].

```Mathematica
LDLT[mat_?SymmetricMatrixQ] := 
 Module[{n = Length[mat], mt = mat, v, w}, 
  Do[If[j > 1, w = mt[[j, ;; j - 1]]; 
    v = w Take[Diagonal[mt], j - 1];
    mt[[j, j]] -= w.v;
    If[j < n, mt[[j + 1 ;;, j]] -= mt[[j + 1 ;;, ;; j - 1]].v]];
   mt[[j + 1 ;;, j]] /= mt[[j, j]], {j, n}];
  {LowerTriangularize[mt, -1] + IdentityMatrix[n], Diagonal[mt]}]

LD = LDLT[G];

L = LD[[1]]

d = LD[[2]]

B = L.DiagonalMatrix[Sqrt[d]];
```

With this decomposition, a sequence of random tensors can be generated as $$ W = \mathbf{B} z $$.
The analytical result of the $\mathbf{B}$ matrix above is used in a C code which generates long sequences of tensors $W$ with the given autocovariance tensor. The result was compared to the analytical predictions, and the results are very similar: The lists below show numerical and theoretical results for the variance of each component of the $W$ tensor:

||$\langle W_{11}^2 \rangle $|$\langle W_{12}^2 \rangle $| $\langle W_{13}^2 \rangle $ | $\langle W_{21}^2 \rangle $ | $\langle W_{22}^2 \rangle $ | $\langle W_{23}^2 \rangle $ | $\langle W_{31}^2 \rangle $ |$\langle W_{32}^2 \rangle $ | $\langle W_{33}^2 \rangle $ |
|:--|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
|Theoretical|1|2|2|2|1|2|2|2|1|
|Numerical|0.980067|1.97681|2.0147|1.99601|1.00855|2.03126|2.0365|1.989|1.00601|

The Mathematica code for the matrix decomposition and the C code for the generation of the sequence of random tensors is available on [Github][tensor-git].

[prl-rfd]: https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.97.174501
[matha-ldl]: https://mathematica.stackexchange.com/questions/83469/mathbf-l-mathbf-d-mathbf-l-top-cholesky-decomposition
[tensor-git]: https://github.com/gapolinario/tensor-noise