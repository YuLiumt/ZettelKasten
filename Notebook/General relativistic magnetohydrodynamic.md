## General relativistic magnetohydrodynamic (GRMHD)

- [[GRMHD -Artificial Atmosphere]]

## Basic Equations

We introduce primitive variables in the form of the fluid density $\rho$, the fluid's specific internal energy $\epsilon$, and the fluid 3-velocity as seen by Eulerian observers at rest in the current spatial 3-hypersurface,

$$
v^{i}=\frac{u^{i}}{W}+\frac{\beta^{i}}{\alpha} \tag{1}
$$

where $u^{i}$ is the fluid 4-velocity, $W=\left(1-v^{i} v_{i}\right)^{-1 / 2}$ is the Lorentz factor, and $\alpha$ and $\beta^{i}$ are lapse and shift, respectively. In terms of the 3-velocity, the contravariant 4-velocity is then given by

$$
u^{0}=\frac{W}{\alpha}, \quad u^{i}=W\left(v^{i}-\frac{\beta^{i}}{\alpha}\right) \tag{2}
$$

and the covariant 4-velocity is

$$
u_{0}=W\left(v^{i} \beta_{i}-\alpha\right), \quad u_{i}=W v_{i} \tag{3}
$$

The evolution equations are written in the Valencia form of GR hydrodynamics as a first-order hyperbolic flux-conservative evolution system for the conserved variables $D$, $S^{i}$, and $\tau$ which are defined in terms of the primitive variables $\rho$, $\epsilon$, $v^{i}$

$$
\begin{aligned}
D &=\sqrt{\gamma} \rho W \\
S^{i} &=\sqrt{\gamma} \rho h W^{2} v^{i} \\
\tau &=\sqrt{\gamma}\left(\rho h W^{2}-P\right)-D
\end{aligned}  \tag{4}
$$

where $\gamma$ is the determinant of the 3-metric $\gamma_{i j}$, and the quantities $P$, and $h=1+\epsilon+P / \rho$ denote pressure, and specific enthalpy, respectively. The evolution system then becomes

$$
\frac{\partial \mathbf{U}}{\partial t}+\frac{\partial \mathbf{F}^{i}}{\partial x^{i}}=\mathbf{S}  \tag{5}
$$

with

$$
\begin{aligned}
\mathbf{U} &=\left[D, S_{j}, \tau\right] \\
\mathbf{F}^{i} &=\alpha\left[D \tilde{v}^{i}, S_{j} \tilde{v}^{i}+\delta_{j}^{i} P, \tau \tilde{v}^{i}+P v^{i}\right] \\
\mathbf{S} &=\alpha\left[0, T^{\mu \nu}\left(\frac{\partial g_{\nu j}}{\partial x^{\mu}}-\Gamma_{\mu \nu}^{\lambda} g_{\lambda j}\right),\alpha\left(T^{\mu 0} \frac{\partial \ln \alpha}{\partial x^{\mu}}-T^{\mu \nu} \Gamma_{\mu \nu}^{0}\right)\right]
\end{aligned}
$$

Here, $\tilde{v}^{i}=v^{i}-\beta^{i} / \alpha$, $\Gamma_{\mu \nu}^{\lambda}$ are the 4-Christoffel symbols, and $T^{\mu \nu}$ is the stress-energy tensor. The pressure $P=P\left(\rho, \epsilon,\left\{X_{i}\right\}\right)$ is obtained via our equation of state module. The $\left\{X_{i}\right\}$ are additional compositional variables of the matter such as the electron fraction $Y_{e}$, which are used for microphysical equations of state.

The above evolution equations are spatially discretized by means of a high-resolution shock-capturing (HRSC) scheme using a second-order accurate finite-volume algorithm.

## Open Source Code

- [[Spritz Thorn]]

