## Finite difference methods

Finite difference methods express continuous differential operators with their Taylor-expanded expressions which are suitably truncated at the desired order. In practice, differential operators acting on a given function are then replaced by algebraic expressions of the values of the function at specific points. These points are called "grid points". For convenience, they are often uniformly separated. One very simple example is calculating the slope of $u$ at a cell $i$ by

$$
\partial_{x} u_{i}=\frac{1}{\Delta x}\left(u_{i+1}-u_{i}\right)+O(\Delta x)
$$
with $\Delta x=x_{i+1}-x_{i}$ being the grid spacing. This introduces an error of the order of $\Delta x$, which depends on the resolution. Using a higher resolution (a smaller $\Delta x$) helps to keep this error small.

To save computational resources, modern finite differencing codes often do something called [[Adaptive mesh refinement]].

## The CFL condition

