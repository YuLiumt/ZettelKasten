## A new public code for initial data of unequal-mass, spinning compact-object binaries

- **Author**: [[Ludwig Jens Papenfort]], Tootle S D, Grandclément P, [[Elias Roland Most]], [[Luciano Rezzolla]].
- **Summary**:
	- A new open-source collection of spectral elliptic solvers that are capable of exploring the major parameter space of binary black holes (BBHs), binary neutron stars (BNSs), and mixed binaries of black holes and neutron stars (BHNSs).
		- The solvers are codes built around the Kadath library.
		- Handle neutron stars that are either irrotational or with an intrinsic spin angular momentum that is parallel to the orbital one.
		- Supporting both analytic and tabulated equations of state at zero or finite temperature.
		- The new solvers are able to reach the most extreme corners in the physically plausible space of parameters, including extreme mass ratios and spin asymmetries, thus representing the most extreme BNS computed to date.
		- The solvers are able to construct quasi-equilibrium and eccentricity-reduced initial data for BBHs, BNSs, and BHNSs, achieving spectral convergence in all cases.
- **Link**: [[NR - Initial Data]]
- **Code**: [[Kadath]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2021arXiv210309911P) Papenfort L J, Tootle S D, Grandclément P, Most E R, Rezzolla L. A new public code for initial data of unequal-mass, spinning compact-object binaries. 2021-03-17.

#in-progress 
___

## HighLight

- Several codes have been developed over the years to compute generic quasi-equilibrium configurations of binaries comprising either two black holes, or two neutron stars, or a black hole and a neutron star, these codes are often not publicly available or they provide only a limited capability in terms of mass ratios and spins of the components in the binary.
	- However, publicly available solvers are severely limited in their capabilities and, even in the case of LORENE, some subsequent developments are not shared publicly.
	- Most notably, there is no open-source code including the treatment of spinning neutron stars and eccentricity reduction.
- The Kadath library has been chosen since it is a highly parallelised spectral solver written in C++ and designed for numerical-relativity applications.
- In all cases, we are able to obtain consistent measurements and corrections from $r(t)$ and $\dot{r}(t)$ up to an eccentricity $\lesssim 10^{-3}$. For eccentricities smaller than these and up to an eccentricity $\lesssim 10^{-4}$, we obtain more reliable results using only the parameters fitted from $\dot{r}(t)$, since the fitting parameters for $r(t)$ are unreliable due to the eccentricity having a weak impact on the separation distance – the oscillations are too small to fit – when using the ansatz.

## Quasi-local quantities

The quasi-local spin angular momentum is quantified by

$$
\mathcal{S}:=\frac{1}{8 \pi} \int_{S_{\mathrm{BH}}} \hat{A}_{i j} \xi_{\mathrm{BH}}^{i} d S^{j}
$$

being a surface integral on the black-hole horizon.

Additionally, the irreducible mass of the black hole is measured by computing the surface area of the horizon. In the case of conformal flatness, this calculation is purely a function of the conformal factor on $\mathcal{S}_{\mathrm{BH}}$

$$
M_{\mathrm{irr}}^{2}:=\frac{1}{16 \pi} \int_{S_{\mathrm{BH}}} \Psi^{4} d S
$$

With $\mathcal{S}$ and $M_{\mathrm{irr}}$, the Christodoulou mass $M_{\mathrm{CH}}$ can be computed, which gives the total mass of the black hole incorporating the contribution from the spin angular momentum

$$
M_{\mathrm{CH}}^{2}:=M_{\mathrm{irr}}^{2}+\frac{\mathcal{S}^{2}}{4 M_{\mathrm{irr}}^{2}}
$$

from which the dimensionless spin of the black hole can be defined as

$$
\chi:=\frac{\mathcal{S}}{M_{\mathrm{CH}}^{2}}
$$

