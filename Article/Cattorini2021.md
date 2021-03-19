## Fully General Relativistic Magnetohydrodynamic Simulations of Accretion Flows onto Spinning Massive Black Hole Binary Mergers

- **Author**: Cattorini F, Giacomazzo B, Haardt F, Colpi M.
- **Summary**:
	- We consider binary black holes with spins of different magnitudes aligned to the orbital angular momentum, which are immersed in a hot, magnetized gas cloud.
	- We find that mass accretion rates onto BH horizons in magnetized fluids are generally smaller than in unmagnetized cases by a factor $\sim 2-3$.
	- Technical limitations in our analysis prevent more detailed predictions.
		- The accretion flows that we describe lack any radiative mechanism, including cooling and feedback.
- **Link**: 
- [ADS](https://ui.adsabs.harvard.edu/abs/2021arXiv210213166C) Cattorini F, Giacomazzo B, Haardt F, Colpi M. Fully General Relativistic Magnetohydrodynamic Simulations of Accretion Flows onto Spinning Massive Black Hole Binary Mergers. arXiv:2102.13166.

___

## Highlight

- Massive black hole binary (MBHB) mergers are natural outcome of galaxy collisions. These mergers may occur in gas rich environment.
- The structure of the accretion flows around coalescing MBHBs largely depends on the angular momentum content of the accreting gas conveyed in the galactic merger, and on its thermodynamical state.
	- The circumbinary disk (CBD) model, where a rotationally supported disk surrounds the binary, and in which viscous and gravitational torques balance to clear a central cavity at twice the MBHB separation.
	- If the surrounding gas is hot, tenuous, and not rotationally supported, the MBHs may find themselves embedded in a turbulent and radiatively inefficient accretion flow. We refer to this scenario as the gas cloud model.
- The binary evolutions are carried out with the Einstein Toolkit.
	- We adopt the "moving puncture" method, and our initial metric data are of the Bowen-York type, conditioned to satisfy the constraint equations using the TwoPunctures thorn.
- In general, non-radiative GRMHD simulations are scale-free. Thus, we will use length and time units that scale with the total mass of the system M.
	- The unitary values of mass, length and time in code units correspond to $$\begin{array}{c} \hat{m}=M=2 \cdot 10^{39} M_{6} \mathrm{~g} \\ \hat{l}=\frac{G}{c^{2}} M=1.48 \cdot 10^{11} M_{6} \mathrm{~cm} \\ \hat{t}=\frac{G}{c^{3}} M=4.94 M_{6} \mathrm{~s} \end{array}$$ where $M_{6} \equiv M / 10^{6} \mathrm{M}_{\odot}$.
- The BHs rotate around each other starting on quasi-circular orbits at an initial separation $d_{0} \simeq 12 M$.
	![[Pasted image 20210314193627.png]]
	
## Mass Accretion Rate

An important diagnostic of our simulations is the flux of rest-mass across the horizons of each BH. To study the mass accretion rate onto the BH horizons, we use the Outflow thorn, which computes the flow of rest-mass density across a given spherical surface. This quantity is calculated via

$$
\dot{M}=-\oint_{S} \sqrt{\gamma} D v^{i} d \sigma_{i}
$$
where $D \equiv \rho \alpha u^{0}$ is the fluid density measured in the observer frame, and $\sigma^{i}$ is the ordinary (flat) space directed area element of the surface enclosing the horizon.

![[Pasted image 20210314195007.png]]

The quantities are scaled from code to physical units as follows: since $M$ generally scales as $\rho M^{2}\left(\mathrm{~g}^{3} \mathrm{~cm}^{-3}\right)$, we multiply the rate in code units $\dot{M}_{\mathrm{c} . \mathrm{u} .}$ by a factor $G^{2} c^{-3}$ ($g^{-2} c m^{3} s^{-1}$) to obtain the rate in cgs units as

$$
\dot{M}_{\mathrm{cgs}}=6.6 \times 10^{21} \dot{M}_{\mathrm{c.u.}} \rho_{-11} M_{6}^{2} \mathrm{~g} \mathrm{~s}^{-1}
$$
and the rate in solar masses per year as

$$
\dot{M}_{\mathrm{M}_{\odot} \mathrm{yr}^{-1}}=4.17 \times 10^{-4} \dot{M}_{\text {c.u. }} \rho_{-11} M_{6}^{2} \mathrm{M}_{\odot} \mathrm{yr}^{-1}
$$
