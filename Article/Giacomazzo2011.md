## Accurate evolutions of inspiralling and magnetized neutron stars: Equal-mass binaries

- **Author**: [[Bruno Giacomazzo]], Rezzolla L, Baiotti L.
- **Summary**:
	- Long-term simulations of magnetized, equal-mass neutron-star binaries. The calculations cover a range of magnetic fields from $B \approx 10^{8} \mathrm{G}$ up to $B \approx 10^{12} \mathrm{G}$, and two different masses.
		- Although NSs with magnetic fields as large as $10^{16}$ are widely expected to be behind the phenomenology associated with magnetars, it is unrealistic to expect that the old NSs comprising the binary have magnetic fields that are so large.
	- What is the role that magnetic fields play during the inspiral and merger on BNSs.
		- Realistic magnetic fields do not affect sensibly the dynamics of the inspiral, but they can influence that of the post-merger.
		- The evolution of the magnetic fields can influence the survival of the hypermassive-neutron star produced at the merger by accelerating its collapse to a black hole.
	- Magnetically induced modifications could become detectable in the case of small-mass binaries
- **Link**: [[Binary Neutron Star]], [[Numerical Relativity]], [[Gravitational Wave]], [[Magnetic Field]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2011PhRvD..83d4014G) Giacomazzo B, Rezzolla L, Baiotti L. Accurate evolutions of inspiralling and magnetized neutron stars: Equal-mass binaries. PRD, 2011, 83(4): 44014.

___

## Highlight

- Even if purely poloidal initially, the magnetic fields produced in the tori surrounding the black hole have toroidal and poloidal components of equivalent strength. [[BNS - Magnetic field amplification]]
	- Kelvin-Helmholtz instability develops during the merger, when the external layers of the two NSs enter into contact, i.e., roughly $2 \rm ms$ before the time of the merger. This purely hydrodynamical instability leads to the formation of vortices that can curl magnetic field lines that were initially purely poloidal and produce toroidal components.
		![[Pasted image 20201219102724.png]]
	- Despite the exponential growth caused by the Kelvin-Helmholtz instability, the overall amplification of the magnetic field is of an order of magnitude at most. In order to achieve convergence in the vortex region it is necessary to use resolutions that are much higher than those currently affordable in BNS simulations.
	- Since most of the simulations to date of magnetized accretion disks around BHs that model the central engine of short GRBs use initial conditions in which the magnetic field has only a poloidal component, it is of particular importance to remark that more realistic initial data should instead have a toroidal and a poloidal component of the comparable magnitude.
- Delay of the Collapse. [[BNS - Merger Fate]]
	- The delay time $\tau_{d}$, i.e., the time between the formation of the HMNS and its collapse to a BH, can be used to measure indirectly the magnetic fields of the progenitor NSs.
		![[Pasted image 20201218150934.png]]
	- In essence, magnetic fields can, via magnetic tension, redistribute the angular momentum, transporting it outwards and reducing the amount of differential rotation that is essential in supporting the HMNS against gravitational collapse. As a result, magnetic fields can "accelerate" the collapse of these models, but only if sufficiently strong so that the magnetic tension can be comparable or larger than the normal pressure gradients. This explains why the delay time is essentially unchanged for small magnetic fields, such as $B_{0} \lesssim 10^{8} \mathrm{G}$.
	- Since a very large magnetic field will also introduce a magnetic pressure which will provide an additional pressure support and thus either compensate or even dominate the angular-momentum redistribution. When simulating a binary with an initial magnetic field of $B_{0} \sim 10^{17} \mathrm{G}$ we have found that the delay time increases and is even larger than the one obtained in the absence of a magnetic field. This is not shown directly in Fig. 5, which has been restricted to realistic values of the magnetic field, but we have indicated with a dashed line the continuation of the delay times to ultra-high magnetic fields.
	- Because of this tight correlation between the degree of magnetization of the NS matter and the delay of the time of the collapse, the measurement of the latter via a GW detection will allow to infer the former.
- The difference in the time of the collapse produces small differences in the mass of the final BH and torus.
	- In all cases the mass of the BH is $M_{\mathrm{BH}} \approx 2.9 M_{\odot}$ and the spin is $a \equiv J / M^{2} \approx 0.8$, but the mass of the torus drops from about $0.063-0.085 M_{\odot}$ to $0.033 M_{\odot}$.
		$$
		\begin{array}{lcccc}
		\text { Binary } & M\left[M_{\odot}\right] & a \equiv J / M^{2} & M_{\text {tor }}\left[M_{\odot}\right] & r_{\text {tor }}[\mathrm{km}] \\
		\hline М1.62-В0 & 2.90 & 0.80 & 0.076 & 105 \pm 13 \\
		М1.62-В8 & 2.89 & 0.80 & 0.085 & 102 \pm 16 \\
		М1.62-В10 & 2.94 & 0.82 & 0.033 & 69 \pm 4 \\
		М1.62-В12 & 2.91 & 0.81 & 0.063 & 94 \pm 4
		\end{array}
		$$
		![[Pasted image 20201218152755.png]]
	- This is probably due to the fact that the magnetic ﬁeld causes some matter to move outside the core region and that will become a BH; as a result, the longer the delay time, the larger the tori.
- Gravitational wave emission
	- High-mass binaries
		- The high-frequency oscillations in the post-merger phase are due to the cores of the two NSs that repeatedly bounce against each other until a sufficient amount of angular momentum is extracted via GWs emission or is moved to the external layers of the HMNS via the magnetic-field tension. When this happens, the centrifugal support becomes insufficient to balance the gravitational forces and the HMNS is induced to collapse to a rotating BH with dimensionless spin $J / M^{2} \simeq 0.80$.
			![[Pasted image 20201219101340.png]]
	- Low-mass binaries
		- The high-frequency oscillations in the postmerger phase are related to the formation of a bar-deformed HMNS, whose spinning frequency is not significantly affected by the presence of magnetic fields.
			![[Pasted image 20201219101527.png]]
		- Clearly, if the HMNS continues to exist for longer times (on the radiation-reaction timescale), then the small differences may grow sufficiently and lead to a detectable difference.
- Determining the level of magnetization of the progenitor stars will be very difficult, while it could be possible if the HMNS survives for sufficiently long times as a deformed and spinning bar. [[BNS - Postmerger Spectrum]]
	- It is unlikely that the degree of magnetization will be measurable by present and advanced detectors if the inspiral is the only part of the signal available. However, if the HMNS survives for sufficiently long times as a deformed and spinning bar, then the modifications introduced by the presence of magnetic fields could lead to waveforms which differ appreciably from those of non-magnetized binaries. In this case, detectors which have high sensitivities at frequencies larger than about 2 kHz, such as advLIGO and, more importantly, the Einstein Telescope, will be able to measure these effects for binaries up to distances of about 100 Mpc. 
		![[Pasted image 20201219104256.png]]

## Parameters

- Grid structure
	- $6$ levels of mesh refinement with the finest level having a resolution of $h=0.1500 M_{\odot} \simeq 221 \mathrm{~m}$.
	- The grid structure is such that the size of the finest grids is $24 M_{\odot} \simeq 35.4 \mathrm{~km}$, while a single refinement level covers the region between a distance $r=164 M_{\odot} \simeq 242.2 \mathrm{~km}$ and $r=254.4 M_{\odot} \simeq 375.7 \mathrm{~km}$ from the center of the domain. This region is the one in which our gravitational-wave extraction is carried out, with a resolution of $h=4.8 M_{\odot} \simeq 7.1 \mathrm{~km}$ (as a comparison, the gravitational wavelength is about $100 km$ and thus well-resolved on this grid).
	- After the merger, we enlarge the central grid that is formed by the merging of the two initial boxes. We do this in order to cover a cubical region with a side of about $88.6 \mathrm{~km}$ and so better resolve not only the whole HMNS, but also the BH-torus system which is produced by the collapse of the HMNS.
	- We have used a reflection-symmetry condition across the $z = 0$ plane and a $\pi$-symmetry condition across the $x = 0$ plane.
	- The timestep on each grid is set by the Courant condition (expressed in terms of the speed of light) and so by the spatial grid resolution for that level; the Courant coefficient is set to be $0.35$ on all refinement levels.
	- The time evolution is carried out using 4th-order–accurate Runge-Kutta integration algorithm.
	- Boundary data for finer grids are calculated with spatial prolongation operators employing 3rd-order polynomials for the matter variables and 5th-order polynomials for the spacetime variables. The prolongation in time employs 2nd-order polynomials.
- Initial data
	- The initial solutions for the binaries are obtained assuming a quasi-circular orbit, an irrotational fluid-velocity field, and a conformally flat spatial metric.
	- The matter is modeled using a polytropic EOS $p=K \rho^{\Gamma}$ with $K=123.6$ and $\Gamma=2$, in which case the maximum gravitational mass is $M_{\mathrm{ADM}} \simeq 1.82 M_{\odot}$ for a nonrotating star and $M_{\mathrm{ADM}} \simeq 2.09 M_{\odot}$ for a uniformly rotating one.
	- A poloidal magnetic field is added a-posteriori using the vector potential
		$$
	A_{\phi} \equiv \varpi^{2} A_{b} \max \left(p-p_{\mathrm{cut}}, 0\right)^{n_{\mathrm{s}}},
	$$where $\varpi \equiv \sqrt{x^{2}+y^{2}}, A_{b}>0$ parameterizes the strength of the magnetic field, $p_{\mathrm{cut}}$ defines where in the NS the magnetic field goes to zero, and $n_{\mathrm{s}}$ determines the degree of differentiability of the potential. Here we have set $p_{\mathrm{cut}}=0.04 \max (P)$, and $n_{\mathrm{s}}=2$ to enforce that both the magnetic field and its first derivative are zero at $p=p_{\mathrm{cut}}$.
	- Two classes of binaries differing in the initial masses. For each of these classes we have considered four different magnetizations.
		$$
	\begin{array}{lcccccccc}
	\text { Binary } & d / M_{\mathrm{ADM}} & M_{b}\left(M_{\odot}\right) & M_{\mathrm{ADM}}\left(M_{\odot}\right) & J\left(\mathrm{~g} \mathrm{~cm}^{2} / \mathrm{s}\right) & \Omega_{0}(\mathrm{rad} / \mathrm{ms}) & r_{e}(\mathrm{~km}) & r_{p} / r_{e} & \rho_{\max }\left(\mathrm{gm} / \mathrm{cm}^{3}\right) & B_{0}(\mathrm{G}) \\
	\hline \text { M1.45-B } \star & 14.4 & 1.445 & 2.680 & 6.5084 \times 10^{49} & 1.78 & 15.0 \pm 0.3 & 0.899 & 4.58 \times 10^{14} & 0 \text { or } 1.97 \times 10^{*} \\
	\text { M1.62-B } \star & 13.3 & 1.625 & 2.981 & 7.7806 \times 10^{49} & 1.85 & 13.6 \pm 0.3 & 0.931 & 5.91 \times 10^{14} & 0 \text { or } 1.97 \times 10^{*}
	\end{array}
	$$
- All the waveforms have been extracted at a radius $r_{\text {iso }}=200 M_{\odot} \approx 300 \mathrm{~km}$.