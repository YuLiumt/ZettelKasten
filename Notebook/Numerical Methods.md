## Numerical Methods

All numerical techniques is to approximate any function by polynomials, those being the only functions than a computer can exactly calculate. So a function $u$ will be approximate by

$$
\hat{u}=\sum_{n=0}^{N} \hat{u}_{n} \Phi_{n}
$$

where the $\Phi_{n}$ are polynomials and called the trial functions. Depending on the choice of trial functions, one can generate various classes of numerical techniques.

Two types of numerical methods:

- [[Spectral Methods]] - high order polynomials on a single domain.
- **Finite elements**: low order polynomials on many domains.

[[Finite difference methods]]

Because the computer is limited in memory, one cannot have infinite resolution. The "shape" of the spacetime has to be stored in some way in a finite-size memory. There are a number of methods to achieve this.

The continuum problem has to be discretised in space and time. Different ways to do the space discretisation are introduced below and the following sections.

The way how both methods are discretising the continuum is quite similar: while in finite difference methods the value of a variable at a certain point represents the value of the continuum variable at that point, in finite volume methods, it represents the average of the continuum variable over the cell around that point.

In spectral and finite element methods on the other hand, the continuum problem is discretised using a set of basis functions.