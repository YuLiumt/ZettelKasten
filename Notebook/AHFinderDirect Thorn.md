## AHFinderDirect Thorn

The apparent horizon (AH) of the black hole is computed with the AHFinderDirect Cactus thorn.

Mass and spin of the BH are computed by means of the isolated horizon formalism implemented in the QuasiLocalMeasures module.

It is important to be able to locate the black hole horizons on the grid.

A marginally trapped surface is a 2-surface in the slice, whose future pointing outgoing null geodesics have zero expansion $\Theta$

$$
\Theta \equiv \nabla_{i} n^{i}+K_{i j} n^{i} n^{j}-K=0
$$

Parameterizing the surface as $r=h(\theta, \phi)$ this can be rewritten as an elliptic equation for $h$ as a function of $\theta$ and $\phi$ where $\gamma_{i j}, \partial_{k} \gamma_{i j}$ and $K_{i j}$ has to be interpolated to the surface.

The thorn needs a reasonable good initial guess for the surface, since it uses Newton iteration to solve the elliptic equations.

 If the black hole spin is oriented in the $z$-direction, the horizon circumference ratios can be used to determine the spin of the black hole.

When the spin of the black hole is not aligned with the $z$-axis, the spin can not be estimated using the horizon circumferences. Within this framework, formulas have been derived for the angular momentum, mass, multi-pole moments and energy fluxes across the horizon.