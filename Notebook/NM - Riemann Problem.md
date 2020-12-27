## NM - Riemann Problem

The Riemann problem is a special initial value problem (IVP) consisting of a partial differential equation (PDE), here the linear advection equation,

$$
u_{t}+a u_{x}=0
$$
with $a$ being a constant, and initial data, which are given by

$$
u(x, 0)=u_{0}(x)=\left\{\begin{array}{ll}
u_{\mathrm{L}} & \text { if } x<0 \\
u_{\mathrm{R}} & \text { if } x>0
\end{array}\right.
$$
$u_{\mathrm{L}}$ and $u_{\mathrm{R}}$ are the left and the right, constant initial values. This initial data have a discontinuity at $x=0$ if $u_{\mathrm{L}} \neq u_{\mathrm{R}}$.

The Riemann problem is important for the numerical solution of the Euler equations. An exact, closed-form solution to the Riemann problem does not exist in this case. However, it is possible to use iterative schemes to obtain the solution to any desired accuracy. Those schemes are called "Riemann solvers".