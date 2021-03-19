## Introduction to isolated horizons in numerical relativity

- **Author**: Dreyer O, Krishnan B, Shoemaker D, [[Erik Schnetter]].
- **Summary**:
	- We show how to find isolated horizons numerically, and how to implement the isolated horizon formulae for mass ($M_{\Delta}$) and angular momentum ($J_{\Delta}$).
- **Link**: [[QuasiLocalMeasures Thorn]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2003PhRvD..67b4018D) Dreyer O, Krishnan B, Shoemaker D, Schnetter E. Introduction to isolated horizons in numerical relativity. PRD, 2003, 67(2): 24018.
___

## Highlight

- Given a numerical simulation of a spacetime containing a black hole, one is faced with two immediate questions: Where is the black hole, and what are the values of its parameters, such as mass and angular momentum?
- In analytical considerations, a black hole is often defined via the event horizon, i.e. the future boundary of the causal past of future null infinity. While this notion is mathematically elegant and has led to powerful results in black hole physics, generally it is not directly useful in numerical evolutions of black hole spacetimes.
	- It can be constructed only after we have knowledge of the entire spacetime and spacetime is the end product of these simulations.
- It is more common to use apparent horizons to characterize a black hole.
	- Apparent horizons are closed two-surfaces on a spatial slice of the spacetime and are, therefore, well suited to numerical simulations that evolve data from one spatial slice to another.
	- A natural question we want to ask is: can one unambiguously associate black hole parameters to apparent horizons?
	- Isolated horizons provide a way to identify a black hole quasi-locally, and allow for the calculation of mass and angular momentum.

## Mass and angular momentum

In order to define the angular momentum, we need to assume that $S$ is axisymmetric, i.e. there is a vector field $\varphi^{a}$ tangent to $S$ such that it preserves $q_{a b}$

$$
\mathcal{L}_{\varphi} q_{a b} \triangleq 0
$$

Given $\varphi^{a}$ and $\omega_{a}$, the isolated horizon angular momentum ($J_{\Delta}$) is defined as the surface term at $\Delta$ in the Hamiltonian which generates diffeomorphisms along a rotational vector field which is equal to $\varphi^{a}$ at the horizon. The expression for $J_{\Delta}$ is:

$$
J_{\Delta}=-\frac{1}{8 \pi} \oint_{S}\left(\omega_{a} \varphi^{a}\right) \mathrm{d}^{2} V \tag{1}
$$
where $S$ is the apparent horizon.

Given $J_{\Delta}$, the horizon mass $M_{\Delta}$ is given by

$$
M_{\Delta}=\frac{1}{2 R_{\Delta}} \sqrt{R_{\Delta}^{4}+4 J_{\Delta}^{2}} \tag{2}
$$
where $R_{\Delta}$ is the area radius of the horizon: $R_{\Delta}=\left(A_{\Delta} / 4 \pi\right)^{1 / 2}$. This formula depends on $R_{\Delta}$ and $J_{\Delta}$ in the same way as in the Kerr solution. However, this is a result of the calculation and not an assumption. $M_{\Delta}$ is the mass left over after all the gravitational radiation has left the system.

To summarize: in order to calculate the mass and angular momentum of an isolated horizon, we need the following ingredients:
1. We must find the apparent horizon and check if the shear of the outward null normal vanishes within numerical errors. If it does, then the isolated horizon formulae are applicable.
2. We need to find the quantity $K_{a b} R^{b}$ on $S$ and the symmetry vector $\varphi^{a}$ (assuming it exists).
3. The angular momentum is then a simple integral over the apparent horizon given by Eq.(1), and the mass is a purely algebraic function given by Eq.(2).

The first and last steps are rather straightforward if we know the location of the apparent horizon. The only nontrivial step is the calculation of $\varphi^{a}$.

$J_{\Delta}$ is measured in units of $M^{2}$.