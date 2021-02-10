## The Third RIT binary black hole simulations catalog

- **Author**: [[James Healy]], [[Carlos Lousto]].
- **Summary**:
	- The third release of the RIT public catalog of numerical relativity black-hole-binary waveforms consists of 777 accurate simulations that include 300 precessing and 477 nonprecessing binary systems with mass ratios $q=m_{1} / m_{2}$ in the range $1 / 15 \leq q \leq 1$ and individual spins up to $s / m^{2}=0.95$.
		- The catalog also provides initial parameters of the binary, trajectory information, peak radiation, and final remnant black hole properties.
- **Link**: [[RIT Catalog]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2020PhRvD.102j4018H) Healy J, Lousto C O. Third RIT binary black hole simulations catalog. PRD, 2020, 102(10): 104018.

___

## Highlight

- The simulations in the RIT Catalog were evolved using the LazEv code.
	- The LazEv code uses the Cactus / Carpet / EinsteinToolkit infrastructure.
- Various simulations in this catalog were studied in detail in previous papers.
	- Resolutions are given in terms of $\mathrm{n} XYY$, where the grid spacing in the wavezone is given by $h=m / X . Y Y$, e.g., $\mathrm{n} 120$ corresponds to $h=m / 1.2$.
- The main sources of numerical errors in this catalog are due to finite difference truncation, finite extraction radii, use of finite number of modes, the non-zero residual initial eccentricities, and displacement of the center of mass.
	- Since full numerical simulations of binary black hole are started at a finite separation they include non-physical initial data effects, such as radiation content absorbed by the holes adding to their masses and spins, and an initial kick due to the net linear momentum of the initial radiation content.
	- The impact of a shifting center or mass during full numerical evolutions has on the mode decomposition of the gravitational waveforms, even if extrapolated to infinite resolution and infinite observer location.
	- For our current simulations we monitor accuracy by measuring the conservation of the individual horizon masses and spins during evolution, as well as the level of satisfaction of the Hamiltonian and momentum constraints, to ensure reaching an accuracy consistent with our main applications.
- For each simulation in the catalog there are three files:
	- One contains the metadata information in ASCII format
		- The associated metadata include the initial orbital frequencies, ADM masses, initial waveform frequencies from (2,2) mode, black hole masses, momenta, spins, separations, and eccentricities, as well the black-hole masses and spins once the initial burst of radiation has left the region around the binary. These relaxed quantities (at $t_{\text {relax}}=200 m$ after the initial burst of radiation has mostly dissipated) are more accurate and physically relevant for modeling purposes.
		- In addition, we also include the final remnant black hole masses, spins and recoil velocity.
	- The other two are a `tar.gz` files containing ASCII files with up to and including $\ell=4$ modes of $m r \psi_{4}$ and $h$.
	- In the near future, data will be available in the Numerical Relativity Injection format.
