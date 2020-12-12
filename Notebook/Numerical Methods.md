# Numerical Methods

All numerical techniques is to approximate any function by polynomials, those being the only functions than a computer can exactly calculate. So a function $u$ will be approximate by

$$
\hat{u}=\sum_{n=0}^{N} \hat{u}_{n} \Phi_{n}
$$

where the $\Phi_{n}$ are polynomials and called the trial functions. Depending on the choice of trial functions, one can generate various classes of numerical techniques.

Two types of numerical methods:

- **Spectral methods**: high order polynomials on a single domain.
- **Finite elements**: low order polynomials on many domains.

## Spectral Methods

Let us consider an interval $\Lambda=\left[x_{\min }, x_{\max }\right]$. In order to talk about basis, one needs to define a scalar product on $\Lambda$. If $w$ is a positive function on $\Lambda$, one can define the scalar product of two functions $f$ and $g$, with respect to the measure $w$ as being

$$
(f, g)_{w}=\int_{\Lambda} f(x) g(x) w(x) \mathrm{d} x.
$$

Using this scalar product, one can find a set of orthogonal polynomials $p_{n}$, each of them of degree $n$. The set composed of those polynomials, up to a given degree $N$ is a basis of $\mathbb{P}_{N}$.

One can then hope to represent any function $u$ on $\Lambda$ by its projection on the polynomials $p_{n}$. Doing so, we define the projection of $u$ simply by

$$
P_{N} u=\sum_{n=0}^{N} \hat{u}_{n} p_{n}(x),
$$
where the coefficients of the projections are given by $\hat{u}_{n}=\frac{\left(u, p_{n}\right)}{\left(p_{n}, p_{n}\right)}$. 

The difference between $u$ and its projection is called the truncation error and one can show that it goes to zero when the order of the approximation increases:

$$
\left\|u-P_{n} u\right\| \longrightarrow 0 \quad \text { when } \quad N \longrightarrow \infty.
$$

This seems very appealing but for the fact that one needs to calculate the $\hat{u}_{n}$ by computing integrals like $\int_{\Lambda} u(x) p_{n}(x) w(x) \mathrm{d} x$.

### Gauss quadratures

There exist $N+1$ positive reals $w_{n}$ and $N+1$ reals $x_{n}$ in $\Lambda$ such that:

$$
\forall f \in \mathbb{P}_{2 N+\delta}, \quad \int_{\Lambda} f(x) w(x) \mathrm{d} x=\sum_{n=0}^{N} f\left(x_{n}\right) w_{n}.
$$
The $w_{n}$ are called the weights and the $x_{n}$ the collocation points. The exact degree of applicability depends on the quadrature. The three usual choices are:

- Gauss: $\delta=1$
- Gauss-Radau: $\delta=0$ and $x_{0}=x_{\min}$
- Gauss-Lobatto: $\delta=-1$ and $x_{0}=x_{\min}$ and $x_{N}=x_{\max}$

### Interpolation

If one applies the Gauss quadratures to approximate the coefficient of the expansion, one obtains

$$
\tilde{u}_{n}=\frac{1}{\gamma_{n}} \sum_{j=0}^{N} u\left(x_{j}\right) p_{n}\left(x_{j}\right) w_{j} \quad \text { with } \quad \gamma_{n}=\sum_{j=0}^{N} p_{n}^{2}\left(x_{j}\right) w_{j}.
$$
Let us precise that this is not exact in the sense that $\hat{u}_{n} \neq \tilde{u}_{n}$. However, the computation of $\hat{u}$ only requires to evaluate $u$ at the $N + 1$ collocation points.

The interpolant of $u$ is then defined as the following polynomial

$$
I_{N} u=\sum_{n=0}^{N} \tilde{u}_{n} p_{n}(x).
$$

One can simply approximate $u^{\prime}$ by the derivative of the interpolant:

$$
u^{\prime}(x) \approx\left[I_{N} u\right]^{\prime}=\sum_{n=0}^{N} \tilde{u}_{n} p_{n}^{\prime}(x)
$$
Such an approximation only requires the knowledge of the coefficients of $u$ and how the basis polynomials are derived. 

> The interpolation and the derivation are two operations that do not commute: $\left(I_{N} u\right)^{\prime} \neq I_{N}\left(u^{\prime}\right)$.

### Chebyshev polynomials

The Chebyshev polynomials $T_{n}$ are an orthogonal set on $[-1,1]$ for the measure $w=\frac{1}{\sqrt{1-x^{2}}}$. More precisely one has

$$
\int_{-1}^{1} \frac{T_{n} T_{m}}{\sqrt{1-x^{2}}} \mathrm{d} x=\frac{\pi}{2}\left(1+\delta_{0 n}\right) \delta_{m n}.
$$
Chebyshev polynomials can be computed by knowing that $T_{0}=1$, $T_{1}=x$ and by making use of the recurrence:

$$
T_{n+1}(x)=2 x T_{n}(x)-T_{n-1}(x).
$$

The derivatives of Chebyshev polynomial:
$$
T_{n}^{\prime}(x)=2 n T_{n-1}(x)+\frac{n}{n-2} T_{n-2}^{\prime}(x), \quad n>2
$$
as well as $T_{2}^{\prime}(x)=4 T_{1}(x)$, $T_{1}^{\prime}(x)=T_{0}$ and, evidently, $T_{0}^{\prime}(x)=0$.

### The weights and collocation points

The weights and collocation points associated with Chebyshev polynomials can be computed:

- Chebyshev-Gauss: $x_{i}=\cos \frac{(2 i+1) \pi}{2 N+2}$ and $w_{i}=\frac{\pi}{N+1}$
- Chebyshev-Gauss-Radau: $x_{i}=\cos \frac{2 \pi i}{2 N+1}$. The weights are $w_{0}=\frac{\pi}{2 N+1}$ and $w_{i}=\frac{2 \pi}{2 N+1}$
- Chebyshev-Gauss-Lobatto: $x_{i}=\cos \frac{\pi i}{N}$. The weights are $w_{0}=w_{N}=\frac{\pi}{2 N}$ and $w_{i}=\frac{\pi}{N}$

### Methods of weighted residuals

Let us consider a differential equation of the form

$$
L u(x)=S(x), \quad x \in[-1,1]
$$
where $L$ is a linear differential operators.

The action of $L$ on $u$ can be expressed by a matrix $L_{i j}$. If the coefficients of $u$ with respect to a given basis are the $\tilde{u}_{i}$ then

$$
L(\sum_{k=0}^{N}  \tilde{u}_{k} T_{k}(x)) \sim S(x)
$$

$$
\sum_{k=0}^{N} \tilde{u}_{k} \sum_{m=0}^{N} L_{m k} T_{m}(x) \sim S(x), \quad x \in[-1,1]
$$

A function $u$ is then an admissible solution of this system, if and only if 1) it fulfills the boundary conditions exactly (up to machine accuracy) 2) it makes the residual $R \equiv L u-S$ small. 

In order to quantify what this "small" means, the weighted residual method relies on $N+1$ tests functions $\xi_{n}$ and one asks that the scalar product of $R$ with those functions is exactly zero:

$$
\left(\xi_{k}, R\right)=0, \quad \forall k \leq N
$$
Depending on the choice of spectral basis and of test functions, one can generate various different types of spectral solvers.

## The collocation method

In the collocation method one uses continuous functions that are zero at all but one collocation point. They can be written as $\xi_{i}\left(x_{j}\right)=\delta_{i j}$. With such test functions, the residual equations are

$$
\sum_{k=0}^{N} \tilde{u}_{k} \sum_{m=0}^{N} L_{m k} T_{m}(x_{n})=S\left(x_{n}\right), \quad \forall n \leq N
$$
the unknowns being the $\tilde{u}_{k}$. However, as such, this system does not admit a unique solution, due to the homogeneous solutions of $L$ (i.e. the matrix associated with $L$ is not invertible) and one has to impose boundary conditions.

In the collocation method, this is done by relaxing two equations (i.e. for $n=0$ and $n=N$) and replacing them by the boundary conditions at $x=-1$ and $x=1$.

### General PDE solvers

$$
H_{i} f_{i}=S_{i}\left(f_{1}, f_{2} \ldots f_{k}\right) \quad \forall 0 \leq i<k
$$
where $H_{i}$ are differential operators (typically second order).

Iteration technique:

- Give an initial guess for the $f_{i}$;
- Computes the sources $S_{i}\left(f_{1}, f_{2} \ldots . f_{k}\right)$;
- Invert the operators $H_{i}$;
- If the relative change in the $f_{i}$ is small stop, else compute the new sources and loop.

We slow the change from step to step by using relaxation like:

$$
f_{i}^{\mathrm{new}}=\lambda H_{i}^{-1}\left[S_{i}\right]+(1-\lambda) f_{i}^{\mathrm{old}}
$$
where typical values $\lambda \approx 0.5$.

### Multi-domain Spectral Method

Spectral methods lose much of their accuracy when non-smooth functions are treated because of the so-called Gibbs phenomenon. The multi-domain spectral method circumvents the Gibbs phenomenon. The basic idea is to divide the space into domains chosen so that the physical discontinuities are located onto the boundaries between the domains.

> The simplest example is the case of a perfect fluid star, where two domains may be distinguished: the interior and the exterior of the star.
