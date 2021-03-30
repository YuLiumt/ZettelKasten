## QuasiLocalMeasures Thorn

Given a numerical simulation of a spacetime containing a black hole, one is faced with two immediate questions: Where is the black hole, and what are the values of its parameters, such as mass and angular momentum?

A natural question we want to ask is: can one unambiguously associate black hole parameters to apparent horizons?

The final mass can be computed from the Christodoulou formula in terms of the black hole (BH) angular momentum and AH area $A$ as

$$
M_{f}=\sqrt{M_{i r r}^{2}+\frac{S^{2}}{4 M_{i r r}^{2}}}, \quad M_{i r r}=\sqrt{\frac{A}{16 \pi}}
$$
where $M_{irr}$ is the irreducible mass. The dimensionless final spin can then be computed as $\chi_{f}=S / M_{f}^{2}$.

## Variable

- `qlm_area`: $A_{\Delta}$
- `qlm_radius`: $R_{\Delta}=\left(A_{\Delta} / 4 \pi\right)^{1 / 2}$
- `qlm_spin`: $J_{\Delta}$
- `qlm_mass`: $M_{\Delta}=\frac{1}{2 R_{\Delta}} \sqrt{R_{\Delta}^{4}+4 J_{\Delta}^{2}} \tag{2}$

qlm_adm_momentum_z(hn) = qlm_adm_momentum_z(hn) &
             & + adm_mom(3) / (8*pi) &
             &   * sqrt(dtq) * qlm_delta_theta(hn) * qlm_delta_phi(hn)

qlm_w_momentum_x(hn) = qlm_w_momentum_x(hn) &
             & + w_mom(1) / (-16*pi) &
             &   * sqrt(dtq) * weights(i)

## References

- [[Dreyer2003]] Introduction to isolated horizons in numerical relativity
- [[Ashtekar2003]] Dynamical Horizons and their Properties
- [[Schnetter2006]] Introduction to dynamical horizons in numerical relativity
- [[Szabados2004]] Quasi-Local Energy-Momentum and Angular Momentum in GR: A Review Article

