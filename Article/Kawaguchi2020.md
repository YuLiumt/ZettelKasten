## A low-mass binary neutron star: long-term ejecta evolution and kilonovae with weak blue emission

- **Author**: Kawaguchi K, Fujibayashi S, [[Masaru Shibata]], Tanaka M, Wanajo S.
- **Summary**:
	- To predict more realistic kilonova light curves, it is crucial to follow the hydrodynamics evolution of the multiple ejecta components until the homologously expanding phase.
		- First, we perform a hydrodynamics simulation of ejecta until the system reaches the homologously expanding phase.
			- We employ the outflow data of the NR simulations obtained in [[Fujibayashi2020]] as the initial conditions.
		- Then, we perform the radiative transfer simulation employing the ejecta profile in the homologously expanding phase obtained by our hydrodynamics simulation, and we discuss the property of the resulting light curves.
	- We found that the ejected material exhibits a mildly prolate shape.
		- A large amount of total ejecta with low lanthanide fraction does not always result in the bright optical emission.
	- Our results suggest that these light curve features could be used as an indicator for the presence of a long-lived remnant NS.
		- The remnant in GW170817/AT2017gfo is unlikely to be a long-lived NS, but might have collapsed to a black hole within $\mathcal{O}(0.1) \mathrm{s}$.
- **Link**: [[Binary Neutron Star]], [[Kilonova]], [[GW170817]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2020arXiv201214711K) Kawaguchi K, Fujibayashi S, Shibata M, Tanaka M, Wanajo S. A low-mass binary neutron star: long-term ejecta evolution and kilonovae with weak blue emission. arXiv:2012.14711.

___

## Highlight

- Based on or motivated by the knowledge of the ejecta profile and the element abundances obtained by numerical-relativity (NR) simulations, radiative transfer simulations with the realistic heating rate and/or the detailed opacity calculations are performed to predict the kilonova light curves. However, the ejecta profiles employed in the previous studies are highly simplified.
	- At the time of the kilonova emission, the ejecta are expected to be in the homologously expanding phase, as the internal energy is lost and becomes much smaller than the kinetic energy due to the adiabatic cooling.
	- In the NR simulations, the ejected material escapes from the computational domain during the evolution before it reaches the homologously expanding phase because the size of the domain and the simulation time are limited by the computational cost. At the time of ejecta evaluation, the ejected material still has non-negligible amount of internal energy compared to its kinetic energy, and the ejecta trajectory can be modified during the expansion due to the thermal pressure.
	- Hence, the ejecta profile at the stage of homologous expansion is not trivial only from the output of the NR simulations.
- The interaction of the multiple ejecta components can modify the ejecta profile as well as the property of the fall-back material.
	- The hydrodynamics profile of the ejecta containing both dynamical and post-merger components was obtained consistently; the former was driven in the first $\sim 50 \mathrm{~ms}$ after the onset of merger by shock heating in the collision surface and/or gravitational torque of the non-axisymmetric merger remnant, while the latter was launched subsequently from the remnant NS-torus system driven by the viscosity and neutrino irradiation.
	- The dynamical and post-merger ejecta masses for this fiducial model are $\approx 10^{-3} M_{\odot}$ and $\approx 10^{-1} M_{\odot}$, respectively.
- In the hydrodynamics simulation code, the effect of fixed-background gravity is taken into account by employing the non-rotating black-hole metric in the isotropic coordinates. We set the initial Arnowitt-Deser-Misner mass of the axisymmetric NR simulation $\approx 2.46 M_{\odot}$ as the black-hole mass of the metric.
	- The inner boundary of the long-term HD simulations is initially set to be $r_{\mathrm{ex}}=8000 \mathrm{~km}$, which agrees with the extraction radius in the NR simulation from which the ejecta information was obtained.
	- We employ the ideal-gas EOS with the adiabatic index of $\Gamma=4 / 3$ assuming that the total pressure is dominated by the radiation pressure.
	- To follow the long-term evolution of the system, we add the radial grid points to the outside of the originally outer boundary when the high velocity edge of the outflow reaches the outer boundary of our HD simulation. At the same time, the innermost radial grid points are removed to keep the total number of the radial grid points.
		- The total mass of the material lost by removing the innermost radial grid points is $<10^{-3} M_{\odot}$, which is less than $1 \%$ of the postmerger ejecta mass located around the inner boundary ($\sim 0.1 M_{\odot}$).
- Ejecta profile
	![[Pasted image 20210104151736.png]]
	- After the outflow data from the NR result run out, a fraction of the material falls back through $r=r_{\text {in}}$ and the total mass in the computational domain turns to decrease.
		- The fall back of the material happens because the pressure support from the inner boundary vanishes at the time when the outflow data run out.
		- A fraction of the material which was counted as ejecta in the NR simulation in the late phase may fail to escape from the system.
	- The radioactive heating plays only a minor role for the hydrodynamics evolution for our setup.
- The top and middle panels of Figure 4, respectively, show the rest-mass density and $Y_{\mathrm{e}}$ value at the temperature of 5 GK for each fluid element in the ejecta profile at $t \approx 0.1$ days. The bottom panel of Figure 4 shows the distribution of the lanthanide ($57 \leq Z \leq 71$) mass fraction of the ejecta profile at 1 day, where $Z$ denotes the atomic number.
	![[Pasted image 20210104153544.png]]
	- The ejecta are already approximately in the homologously expanding phase at $t \approx 0.1$ day, and thus, $r / c t$ approximately shows the velocity of the fluid.
	- Both early ($t_{\mathrm{in}} \lesssim 1 \mathrm{~s}$) and late ($t_{\mathrm{in}} \gtrsim 1 \mathrm{~s}$) time ejecta components exhibit mildly prolate morphology. The former component  ($t_{\mathrm{in}} \lesssim 1 \mathrm{~s}$) distributes from $\approx 0.1 c$ to $0.3 c$ for the equatorial region and from $\approx 0.2 c$ to $0.4 c$ for the polar region. The latter component ($t_{\mathrm{in}} \gtrsim 1 \mathrm{~s}$) exhibits more elongated shape, and it is entirely surrounded by the former component. The higher ejecta velocity in the polar direction, which is the origin of the prolate shape, is due to neutrino irradiation from the remnant NS.
	- This indicates that the ejecta from a BNS merger that results in a long-lived remnant NS would always have a prolate shape.
	- The $Y_{\mathrm{e}}$ profile of the early-time ejecta component ($t_{\mathrm{in}} \lesssim 1 \mathrm{~s}$) shows a clear angular dependence.
	- A large value of the lanthanide fraction is realized in the equatorial region of the early-time ejecta component.
	- r-process nucleosynthesis takes place only weakly in the late-time ejecta due to the high values of $Y_{\mathrm{e}}$.
- We calculate the light curves from the obtained ejecta profile using a wavelength-dependent radiative transfer simulation code.
	![[Pasted image 20210104160307.png]]
	- The radiative transfer simulations are performed from $t=0.1$ days to 30 days.
	- We employ the snapshot of our HD simulation at 0.1 days and the density profile is mapped to the velocity space in the Cartesian coordinates assuming the homologous expansion.
	- The luminosity remains nearly constant until $t \approx 3$ days and steeply declines at $t \approx 7$ days.
	- The viewing angle dependence vanishes after $\approx 10$ days, which suggests that the entire ejecta are optically thin for such a phase.
	- The fainter emission in the early phase ($\approx 1$ days) indicates that the diffusion time scale of photons is longer than in AT2017gfo. The brighter emission in the late phase ($\approx 7$ days) indicates that the total ejecta mass of AT2017gfo would be smaller than that of the fiducial ejecta model ($\approx 0.1 M_{\odot}$) unless the uncertainty of the thermalization efficiency is significantly large.
		- The progenitor of AT2017gfo is not likely to be a system like our fiducial model, that is, a BNS merger that results in a long-lived remnant NS.
- The ugrizJHK-band light curves observed from various viewing angles.
	![[Pasted image 20210104175709.png]]
	- The kilonova light curves for the fiducial model are relatively faint in the optical wavelengths and rather bright in the infrared wavelengths compared to AT2017gfo.
		- The future observation of a kilonova with such features will be a good indicator for the formation of a long-lived remnant NS.
		- BNS mergers that result in long-lived remnant NSs may be detected in the future, as a low-mass NS binary indeed exists.
	- There are three reasons that cause the faint optical and bright infrared emission.
		- The first reason is in the prolate morphology of the late-time ejecta component. For the prolate morphology, photons diffuse preferentially toward the equatorial direction, in which the optical depth is small. In such a situation, optical photons emitted from the late-time ejecta component are efficiently reprocessed into infrared photons in the lanthanide-rich early-time ejecta component located around the equatorial plane.
		- The second reason is in the presence of Y ($Z=39$) and Zr ($Z = 40$) in the high velocity edge of the ejecta. Y and Zr are categorized as d-shell elements, and they significantly contribute to the opacity in the optical wavelength as they have a large number of low-lying energy levels.
		- The third reason is in the relatively low specific heating rate of the late-time ejecta component.
	- Since the high velocity components in the polar region is enhanced by neutrino irradiation from the long-lived remnant NS, the high-velocity ejecta components in the polar region could be suppressed if the remnant NS collapses into a black hole in a shorter time scale after the merger.
