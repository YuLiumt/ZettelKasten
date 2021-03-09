## TwoPunctures

Following York’s conformal-transverse-traceless decomposition method, we make the following assumptions for the metric and the extrinsic curvature

$$
\begin{aligned}
\gamma_{i j} &=\psi^{4} \delta_{i j} \\
K_{i j} &=\psi^{-2}\left(V_{j, i}+V_{i, j}-\frac{2}{3} \delta_{i j} \operatorname{div} V\right)
\end{aligned}
$$

The initial data described by this method are conformally flat and maximally sliced, $K=0$. With this ansatz the Hamiltonian constraint yields an equation for the conformal factor $\psi$

$$
\triangle \psi+\frac{1}{8} \psi^{5} K_{i j} K^{i j}=0
$$

while the momentum constraint yields an equation for the vector potential $V$

$$
\triangle V+\frac{1}{3} \operatorname{grad}(\operatorname{div} \not \nu)=0
$$

One can proceed by choosing a non-trivial analytic solution of the Bowen-York type for the momentum constraint,

$$
V=\sum_{n=1}^{2}\left(-\frac{7}{4\left|x_{n}\right|} P_{n}-\frac{x_{n} \cdot P_{n}}{4\left|x_{n}\right|^{3}} x_{n}+\frac{1}{\left|x_{n}\right|^{3}} x_{n} \times S_{n}\right)
$$

Hamiltonian constraint is obtained by writing the conformal factor $\psi$ as a sum of a singular term and a finite correction $u$

$$
\psi=1+\sum_{n=1}^{2} \frac{m_{n}}{2\left|x_{n}\right|}+u
$$

Note that the mass parameters $m_{n}$ are different from the actual physical masses of the black holes.

TwoPunctures has options to give the target black hole masses and it will iterate internally to find the corresponding "bare masses".

Note also that the initial data will have spurious gravitational radiation.

## Parameter

These data are characterized by mass parameters $m_{p 1 / 2}$, momenta $\vec{p}_{1 / 2}$, spins $\vec{S}_{1 / 2}$, and coordinate locations $\vec{x}_{1 / 2}$ of each hole.

![[Pasted image 20210309181818.png]]

We normalize our data such that the total Arnowitt-Deser-Misner (ADM) energy is $1M$ and the mass ratio, as measured by the horizons masses on the initial slice, has a given value. Because the BHs absorb energy during the first few M of evolution, the actual mass ratio will be altered.