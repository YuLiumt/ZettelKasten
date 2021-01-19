## Physics of eccentric binary black hole mergers: A numerical relativity perspective

- **Author**: [[Eliu Huerta]], [[Roland Haas]], Habib S, Gupta A, Rebei A, Chavva V, Johnson D, Rosofsky S, Wessel E, Agarwal B, Luo D, Ren W.
- **Summary**:
	- A catalog of 89 numerical relativity waveforms that describe binary systems of non-spinning black holes with mass-ratios $1 \leq q \leq 10,$ and initial eccentricities as high as $e_{0}=0.18$ fifteen cycles before merger.
	- We provide a systematic study of the circularization of eccentric BBH mergers with $q \leq 10$ and $e_{0} \lesssim 0.18$ fifteen cycles before merger.
- **Link**: [[Binary Black Hole]], [[Gravitational Wave]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2019PhRvD.100f4003H) Huerta E A, Haas R, Habib S, Gupta A, Rebei A, Chavva V, Johnson D, Rosofsky S, Wessel E, Agarwal B, Luo D, Ren W. Physics of eccentric binary black hole mergers: A numerical relativity perspective. PRD, 2019, 100(6): 64003.

___

## Highlight

- Characterizing the properties of the NR waveforms. [[Habib2019]]
	- We have used the inspiral-merger-ringdown ENIGMA waveform model to determine the eccentricity, mean anomaly and gauge-invariant frequency parameters, $\left(e_{0}, \ell_{0}, x_{0}\right)$.
- The importance of including higher-order waveform modes. [[GW - Higher-order modes]]
	- We do this through pair-wise comparisons between NR waveforms that include either all the modes listed above, or just the $\ell=|m|=2$ mode, using the relations
		$$
	\begin{aligned}
	\Delta E^{\prime} &=\frac{\Delta E(\ell,|m|)-\Delta E(\ell=|m|=2)}{\Delta E(\ell,|m|)} \\
	\Delta J^{\prime} &=\frac{\Delta J(\ell,|m|)-\Delta J(\ell=|m|=2)}{\Delta J(\ell,|m|)}
	\end{aligned}
	$$
	-  These results also show that that for systems with $q \geq 5$ it is essential to include higher-order waveform modes to accurately describe the dynamics of eccentric BBH mergers.
		![[Pasted image 20201217134250.png]]
- Final properties of the black hole remnant. [[BBH - Orbital Eccentricity]]
	- The final mass and spin of the BH remnant are nearly independent of eccentricity in the range $e_{0} \leq 0.2$.
		![[Pasted image 20201217184043.png]]
- The circularization of moderately eccentric BBH mergers.
	- The waveform circularizes very rapidly, from $e_{0}=0.18$ fifteen cycles before merger, turning into a quasi-circular waveform signal near the merger event.
		![[Pasted image 20201217184855.png]]
	- This is the reason why the results presented in Figure 3 are consistent with their quasi-circular counterparts.

## Parameters

- There is a central, mesh refined cubical region of the grid in which Cartesian coordinates are used, surround by 6 regions that make up a cubed sphere grid with constant angular resolution.
	- The cubical region employs mesh refinement with the resolution on the coarsest grid being $h_{\text {coarse }}=1.92 M$.
	- The resolution in the finest box containing the black hole $i$ is $1.2 M_{i} /\left(N_{l}-1\right)$ where $M_{i}$ is the initial mass parameter of black hole $i$ and $N_{l}$ is the number of points used for the resolution level $l$ simulation. In our simulations we used $N_{l}=32,36,40,44$, where $N_{l}=44$ was only used for simulations with a mass ratio $q>5$.
	- The finest box surrounding each black hole has a radius of $1.2 M_{i}$ and each coarser box has twice the radius of the next finer one.
	- In the spherical region we choose an angular resolution of $h_{\text {angular }}=\pi /\left(4 N_{l}\right)$ and a radial resolution of $1.92 M$ which matches the coarsest resolution in the Cartesian grid.
	- We use a time step $\Delta t=0.864 M$ on the coarsest level, corresponding to a Courant-Friedrichs-Lewy condition of $\Delta t / h_{\text {coarse }}=0.45$ which is held constant on the finer levels by decreasing their time step size.
- We extract gravitational waves using modes of the Weyl scalar $\psi_{4}$ extracted on coordinate spheres of radius $r_{\mathrm{det}, i}=100 M, 115 M, 136 M, 167 M, 214 M, 300 M, 500 M$.
- We use $8^{\mathrm{th}}$ order finite differencing operators to compute spatial derivatives of the spacetime quantities in the Einstein field equations.
	- 5 ghost zones
	- $4^{\mathrm{th}}$ order Runge-Kutta timestepper
	- each refined region is surrounded by 20 points that are filled in via prolongation from the next coarser region.
	- Vertex centered $5^{\mathrm{th}}$ order prolongation operators.

## Convergence of the numerical waveforms

To estimate the convergence of each waveform we simulated each set of physical parameters using at least 3 (4) simulations using increasing resolution for waveforms of mass ratio $q \leq 5$ ($q>5$). We then compute the gravitational wave phase $\phi^{(2,2)}$ from the complex $\ell=m=2$ mode of the spherical harmonic decomposition of the outgoing component of the Weyl scalar $\psi_{4}$ and studied its convergence properties.

Figure 5 shows the rescaled phase differences $\phi^{(2,2)}\left(h_{n}\right)-\phi^{(2,2)}\left(h_{\mathrm{high}}\right)$ between the gravitational wave phase obtained from the simulation with resolution $h_{n}$ and the highest resolved simulation.

![[Pasted image 20210116182721.png]]