## Remnant of binary black-hole mergers: New simulations and peak luminosity studies

- **Author**: [[James Healy]], [[Carlos Lousto]].
- **Summary**:
	- 
- **Link**: 
- [ADS](https://ui.adsabs.harvard.edu/abs/2017PhRvD..95b4037H) Healy J, Lousto C O. Remnant of binary black-hole mergers: New simulations and peak luminosity studies. PRD, 2017, 95(2): 24037.

___

## Highlight

- The Carpet mesh refinement driver provides a "moving boxes" style of mesh refinement. In this approach, refined grids of fixed size are arranged about the coordinate centers of both holes. The Carpet code then moves these fine grids about the computational domain by following the trajectories of the two BHs.
- Note that once we have the horizon spin, we can calculate the horizon mass via the Christodoulou formula $m_{H} = \sqrt{m_{\mathrm{irr}}^{2}+S_{H}^{2} /\left(4 m_{\mathrm{irr}}^{2}\right)}$, where $m_{\mathrm{irr}}=\sqrt{A /(16 \pi)}$. $A$ is the surface area of the horizon, and $S_{H}$ is the spin angular momentum of the BH.
- Because the puncture initial data we use assumes a conformally flat 3-metric it has a non-physical (albeit generally small) wave content that gets radiated away or absorbed by the holes. In order to provide a more physical set of initial parameters to be used into the remnant formulae, we extract the parameters of the black holes after the values of the horizon masses and spin settles. We observe that evaluating those at a time $t=150 m$ after the beginning of the simulation is very accurate.
- The recoil velocity and peak luminosity as directly computed from the waveforms (adding up to $\ell=6$ modes).

## Fitting final mass and spin

The fitting formula for  is given by,

$$
\begin{array}{r}
\frac{M_{\text {rem }}}{m}=(4 \eta)^{2}\left\{M_{0}+K_{1} \tilde{S}_{\|}+K_{2 a} \tilde{\Delta}_{\|} \delta m+K_{2 b} \tilde{S}_{\|}^{2}+\right. \\
K_{2 c} \tilde{\Delta}_{\|}^{2}+K_{2 d} \delta m^{2}+K_{3 a} \tilde{\Delta}_{\|} \tilde{S}_{\|} \delta m+ \\
K_{3 b} \tilde{S}_{\|} \tilde{\Delta}_{\|}^{2}+K_{3 c} \tilde{S}_{\|}^{3}+ \\
K_{3 d} \tilde{S}_{\|} \delta m^{2}+K_{4 a} \tilde{\Delta}_{\|} \tilde{S}_{\|}^{2} \delta m+ \\
K_{4 b} \tilde{\Delta}_{\|}^{3} \delta m+K_{4 c} \tilde{\Delta}_{\|}^{4}+K_{4 d} \tilde{S}_{\|}^{4}+ \\
K_{4 e} \tilde{\Delta}_{\|}^{2} \tilde{S}_{\|}^{2}+K_{4 f} \delta m^{4}+K_{4 g} \tilde{\Delta}_{\|} \delta m^{3}+ \\
\left.K_{4 h} \tilde{\Delta}_{\|}^{2} \delta m^{2}+K_{4 i} \tilde{S}_{\|}^{2} \delta m^{2}\right\}+ \\
{\left[1+\eta\left(\tilde{E}_{\mathrm{ISCO}}+11\right)\right] \delta m^{6}}
\end{array}
$$

and the fitting formula for the final spin has the form,

$$
\begin{array}{r}
\alpha_{\text {rem }}=\frac{S_{\text {rem }}}{M_{\text {rem }}^{2}}=(4 \eta)^{2}\left\{L_{0}+L_{1} \tilde{S}_{\|}+\right. \\
L_{2 a} \tilde{\Delta}_{\|} \delta m+L_{2 b} \tilde{S}_{\|}^{2}+L_{2 c} \tilde{\Delta}_{\|}^{2}+L_{2 d} \delta m^{2}+ \\
L_{3 a} \tilde{\Delta}_{\|} \tilde{S}_{\|} \delta m+L_{3 b} \tilde{S}_{\|} \tilde{\Delta}_{\|}^{2}+L_{3 c} \tilde{S}_{\|}^{3}+ \\
L_{3 d} \tilde{S}_{\|} \delta m^{2}+L_{4 a} \tilde{\Delta}_{\|} \tilde{S}_{\|}^{2} \delta m+L_{4 b} \tilde{\Delta}_{\|}^{3} \delta m+ \\
L_{4 c} \tilde{\Delta}_{\|}^{4}+L_{4 d} \tilde{S}_{\|}^{4}+L_{4 e} \tilde{\Delta}_{\|}^{2} \tilde{S}_{\|}^{2}+ \\
L_{4 f} \delta m^{4}+L_{4 g} \tilde{\Delta}_{\|} \delta m^{3}+ \\
\left.L_{4 h} \tilde{\Delta}_{\|}^{2} \delta m^{2}+L_{4 i} \tilde{S}_{\|}^{2} \delta m^{2}\right\}+ \\
\tilde{S}_{\|}(1+8 \eta) \delta m^{4}+\eta \tilde{J}_{\mathrm{ISCO}} \delta m^{6}
\end{array}
$$

Here we use the notation

$$
\begin{array}{r}
m=m_{1}+m_{2} \\
\delta m=\frac{m_{1}-m_{2}}{m} \\
\tilde{S}=\left(\vec{S}_{1}+\vec{S}_{2}\right) / m^{2} \\
\tilde{\Delta}=\left(\vec{S}_{2} / m_{2}-\vec{S}_{1} / m_{1}\right) / m
\end{array}
$$

where $m_{i}$ is the mass of $\mathrm{BH} i=1,2$ and $S_{i}$ is the spin of $\mathrm{BH} i$. Here the index $\perp$ and $\|$ refer to components perpendicular to and parallel to the orbital angular momentum.

## Convergence studies

Since the final mass and spin are calculated locally on the apparent horizon, where the grid resolution is highest, the finite resolution error is very low and there is no associated finite observer error, hence those quantities can be determined to high accuracy.

In order to calculate the finite resolution error, we would need the same binary configuration at three different resolutions. For 107 runs, this would be very expensive computationally. Instead, we choose a simulation from each mass ratio at three different resolutions and use this run to calculate the finite resolution error.