## Initial Data

Physically valid initial data have to satisfy the Hamiltonian and momentum constraints at the very least, and some quasiequilibrium assumptions are desired to be met for astrophysically realistic binary initial data.

## Spin

The two neutron stars cannot be tidal locked, because the viscosity of neutron star matter is too low. This means that initial data sequences of corotating configurations for different separations cannot be used to approximate the inspiral of two neutron stars. On the other hand, sequences of irrotational configurations can be used to approximate the inspiral of two neutron stars without spin. 

A typical neutron star has a mass of about $1.4 M_{\odot}$ and a radius on the order of $15 \mathrm{km}$. From Kepler’s law the orbital period

$$
    P_{o} \sim 6 \mathrm{ms} \left(\frac{d}{50 \mathrm{km}}\right)^{3 / 2}\left(\frac{M}{M_{\odot}}\right)^{-1 / 2} 
$$
is on the order of a few milliseconds during the last orbit before merger where the separation $d \sim 50 \mathrm{km}$ Thus systems with spin periods that are much larger than $P_{o}$ should be treatable as approximately irrotational, while systems with spin periods of a few milliseconds (such as millisecond pulsars) cannot be regarded as irrotational. This fact explains why irrotational initial data are far more popular today.

## Main Equations

We compute initial data of the induced metric $\gamma_{i j}$ and extrinsic curvature $K_{i j}$ in the extended conformal thin-sandwich formulation[^1]. A conformal transformation is defined by

[^1]: All the numerical computations of initial data are performed with a public multidomain spectral method library, [[Lorene]].

$$
\begin{aligned}
\gamma_{i j} &=\psi^{4} \hat{\gamma}_{i j}, \gamma^{i j}=\psi^{-4} \hat{\gamma}_{i j} \\
A^{i j} &=\psi^{-10} \hat{A}^{i j}, A_{i j}=\psi^{-2} \hat{A}_{i j}
\end{aligned} \tag{1}
$$
where $A_{i j}$ is the traceless part of the extrinsic curvature given as

$$
A_{i j} \equiv K_{i j}-\frac{1}{3} K \gamma_{i j}, K \equiv \gamma^{i j} K_{i j} \tag{2}
$$
We handle a weighted lapse function $\Phi \equiv \alpha \psi$ instead of the lapse function $\alpha$ itself in the computation of initial data for the sake of numerical accuracy. A traceless evolution tensor of the conformal induced metric,

$$
\hat{u}_{i j}=\partial_{t} \hat{\gamma}_{i j} \tag{3}
$$
with $\hat{\gamma}^{i j} \hat{u}_{i j}=0$ is also introduced as freely specifiable data in this formulation.

To obtain a quasiequilibrium configuration of binary neutron stars, we impose conditions,

$$
\hat{\gamma}_{i j}=f_{i j}, K=0, \hat{u}_{i j}=0, \partial_{t} K=0 \tag{4}
$$
on freely specifiable data. Here, $f_{i j}$ is the flat 3-metric.

One plausible way to incorporate an approaching velocity may be to add uniform contraction to the helical Killing vector in the manner

$$
\xi^{\mu}=\left(\partial_{t}\right)^{\mu}+\Omega\left(\partial_{\varphi}\right)^{\mu}+v \frac{r}{r_{0}}\left(\partial_{r}\right)^{\mu} \tag{5}
$$
Here, $v$ (negative for the approaching velocity) and $r_{0}$ should be regarded as the radial velocity and separation from the coordinate origin, respectively.

The equations to be solved for gravitational fields become

$$
\begin{aligned}
\stackrel{\circ}{D^{2}} \psi &=-\frac{1}{8} \psi^{-7} \hat{A}_{i j} \hat{A}^{i j}-2 \pi \psi^{5} \rho_{\mathrm{H}} \\
\stackrel{\circ}{D^{2}} \beta^{i}+\frac{1}{3}\stackrel{\circ}{D^{i}}\stackrel{\circ}{D_{j}} \beta^{j} &=2 \hat{A}^{i j}{\stackrel{\circ}{D}_{j}}\left(\Phi \psi^{-7}\right)+16 \pi \Phi{\psi}^{3} j^{i} \\
\stackrel{\circ}{D^{2}} \Phi &=\frac{7}{8} \Phi \psi^{-8} \hat{A}_{i j} \hat{A}^{i j}+2 \pi \Phi \psi^{4}\left(\rho_{\mathrm{H}}+2 S\right) \\
\hat{A}^{i j} &=\frac{\psi^{7}}{2 \Phi}\left(\stackrel{\circ}{D^{i}}\beta^{j}+\stackrel{\circ}{D^{j}} \beta^{i}-\frac{2}{3} f^{i j} \stackrel{\circ}{D_{k}} \beta^{k}\right)
\end{aligned} \tag{6}
$$
where $\stackrel{\circ}{D_{i}}$ is the covariant derivative associated with the flat metric, $f_{i j}$. The matter source terms are defined from the 3+1 decomposition of the energy-momentum tensor $T_{\mu \nu}$ in terms of a future-directed unit normal vector $n^{\mu}$ to the constant-time hypersurface as

$$
\begin{aligned}
\rho_{\mathrm{H}} &=T_{\mu \nu} n^{\mu} n^{\nu} \\
j_{i} &=-\gamma_{i \mu} T^{\mu \nu} n_{\nu} \\
S_{i j} &=\gamma_{i \mu} \gamma_{j \nu} T^{\mu \nu}
\end{aligned} \tag{7}
$$
The scalar elliptic equations are solved with boundary conditions,

$$
\psi, \Phi \rightarrow 1(r \rightarrow \infty) \tag{8}
$$
derived from the asymptotic flatness. The boundary condition on the shift vector determines the frame in which the equations are solved, and we can simply set

$$
\beta^{i} \rightarrow 0(r \rightarrow \infty) \tag{9}
$$
The energy-momentum tensor takes the form

$$
T_{\mu \nu}=\rho h u_{\mu} u_{\nu}+P g_{\mu \nu} \tag{10}
$$
where $\rho, P, h,$ and $u^{\mu}$ are the rest-mass density, pressure, specific enthalpy, and 4-velocity of the fluid, respectively. The specific enthalpy is defined by $h=1+\varepsilon+P / \rho$, where $\varepsilon$ is the specific internal energy. The hydrodynamic equations comprise the continuity equation

$$
\nabla_{\mu}\left(\rho u^{\mu}\right)=0 \tag{11}
$$
and the local energy-momentum conservation equation

$$
\nabla_{\nu} T^{\mu \nu}=0 \tag{12}
$$
where $\nabla_{\mu}$ is the covariant derivative associated with the spacetime metric. Because we focus only on the irrotational velocity field, a velocity potential $\Psi$ such that

$$
\nabla_{\mu} \Psi=h u_{\mu} \tag{13}
$$
The time component of Eq. (12) in the comoving frame of the fluid merely gives Eq. (11) for a zero-temperature perfect fluid, and the spatial components of Eq. (12), or the relativistic Euler equation, are shown to be integrable for an irrotational flow in the presence of symmetry.

A hydrostatic equilibrium can be obtained when a symmetry for hydrodynamical fields exists. The symmetry naturally arises in a spacetime equipped with a Killing vector field such as the helical Killing vector. We do not assume, however, the existence of Killing vector fields, because the approaching velocity is not compatible with the spacetime symmetry. Instead, we only assume that all the hydrodynamical fields are conserved when they are Lie dragged along a symmetry vector field $\xi^{\mu}$.

A potential caveat with Eq. (5), however, is the fact that the radial velocity term, $r\left(\partial_{r}\right)^{i}$, is not divergence free. This suggests that a neutron star with the approaching velocity represented by this form has a contracting density profile. Such initial data might introduce unphysical oscillations of neutron stars. This problem does not arise in computations of quasicircular initial data with the helical Killing symmetry, which is represented by a divergence-free vector field.

This undesired possibility may be avoided by adopting a different symmetry vector for the hydrodynamical fields from that for the gravitational fields. Specifically, we can adopt a divergence-free vector,

$$
\xi^{\mu}=\left(\partial_{t}\right)^{\mu}+\Omega\left(\partial_{\varphi}\right)^{\mu}+v_{\pm}\left(\partial_{x}\right)^{\mu} \tag{14}
$$
where neutron stars are assumed to lie on the $x$ axis and $v_{+}$ and $v_{-}$ apply to neutron stars at $x>0$ and $x<0$, respectively. The values of $v_{\pm}$ should be chosen to satisfy $v_{+}-v_{-}=2 v$, and the partition may be done according to their locations relative to the rotational axis or masses in isolation.

From our experience, no noticeable difference is found between results obtained with these two symmetry vectors, including the oscillation of neutron stars during time evolution, for an equal-mass binary. We still prefer to adopt Eq. (14), because this symmetry vector may be useful in computing low-eccentricity initial data of unequal-mass binaries.