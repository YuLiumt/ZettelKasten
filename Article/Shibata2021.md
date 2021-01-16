## Alternative possibility of GW190521: Gravitational waves from high-mass black hole-disk systems

- **Author**: [[Masaru Shibata]], Kiuchi K, Fujibayashi S, Sekiguchi Y.
- **Summary**:
	- The source of GW190521 might not be a merger of binary black holes but a stellar collapse of a very massive star leading temporarily to a black hole of mass $\sim 50 M_{\odot}$ and a massive disk of several tens of solar mass that is dynamically unstable to the one-armed spiral-shape deformation.
		- Unfortunately, the electromagnetic counterparts of GW190521 were not seriously searched by the optical-infrared telescopes, because GW190521 was announced as a candidate for binary black holes.
	- We prepare an initial condition of a massive black hole and a massive disk supposing that it would be the outcome formed during the collapse of a rapidly-rotating very-massive stellar core.
		- For more realistic work, it is necessary to perform a simulation started from a rapidly-rotating very-massive progenitor star.
- **Link**: [[Numerical Relativity]], [[GW190521]], [[Black hole-disk systems]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2021arXiv210105440S) Shibata M, Kiuchi K, Fujibayashi S, Sekiguchi Y. Alternative possibility of GW190521: Gravitational waves from high-mass black hole-disk systems. arXiv:2101.05440

___

## Highlight

- We prepare an initial condition of a massive black hole and a massive disk supposing that it would be the outcome formed during the collapse of a rapidly-rotating very-massive stellar core.
	- We choose the black hole of initial mass $M_{\mathrm{BH}, 0}=50 M_{\odot}$ and the disk of rest mass $M_{\text {disk}}=15-50 M_{\odot}$.
		![[Pasted image 20210115214340.png]]
		- The initial dimensionless spin of the black hole is set to be approximately 0.8.
		- We set the inner coordinate radius of the disk to be close to the radius of the innermost stable circular orbit around the rapidly spinning black hole as $r_{\text {in}} \approx 2 G M_{\mathrm{BH}, 0} / c^{2}$, and the outer edge is varied in the range of $r_{\text {out}} /\left(G M_{\mathrm{BH}, 0} c^{-2}\right)=21-53$ (see Table I). These are the plausible sizes of the dense region of the disk formed during the collapse of rotating very-massive stellar cores
	- We employ a tabulated equation of state based on the DD2 equation of state for a relatively high-density part and the Timmes (Helmholtz) equation of state for the low-density part.
	- We do not consider the neutrino emission and weak interaction.
		- In the presence of the neutrino emission, the disk shrinks by the neutrino cooling and its compactness is increased. This effect makes the dependence of the growth timescale of the disk instability and resulting gravitational waveforms on the disk morphology obscure.
	- We determine the angular velocity profile from the relation $j \propto \Omega^{-n}$, where $j=c^{-2} h u_{\varphi}$ is the specific angular momentum. $\Omega$ is the angular velocity defined by $u^{\varphi} / u^{t}$ with $u^{\mu}$ the fluid four-velocity. $n$ is a constant that determines the profile of the angular velocity, for which we choose $n=1 / 7$ to obtain a profile of $\Omega$ close to the Keplerian one that does not result in the geometrically thick disks.
- Understand the nature of the non-axisymmetric instability of the massive disks orbiting a black hole and resulting gravitational waves emitted.
	- The snapshots of the rest-mass density profile of the disk in the equatorial plane for model M14.
		![[Pasted image 20210115225111.png]]
		- A small numerical noise introduced during the simulation triggers the subsequent exponential growth of the one-armed spiral-shape deformation mode.
		- After the significant growth of the spiral-shape deformation, the angular momentum transport inside the disk, which is caused by the gravitational torque from the non-axisymmetric density perturbation as well as by the black-hole tidal field, is enhanced.
			- As a result, a significant mass accretion onto the black hole proceeds. During the initial growth of the one-armed spiral-shape deformation until its saturation, $20-30 \%$ of the total rest mass of the disk falls into the black hole.
			- The gravitational torque is exerted continuously to the matter in the outer part of the disk, which is expanded significantly. We find that $1-2 \%$ of the total mass of the disk is ejected from the system.
- The waveforms are characterized by initial burst waves of a high amplitude and subsequent quasi-periodic waves of a low amplitude.
	- Less massive disks with $15 M_{\odot} \leq M_{\text {disk }} \leq 25 M_{\odot}$
		![[Pasted image 20210116102230.png]]
	- More Massive disks with $30 M_{\odot} \leq M_{\text {disk }} \leq 50 M_{\odot}$
		![[Pasted image 20210116103044.png]]
- The compactness and mass of the disk are the key parameters for determining the type of the waveforms.
	![[Pasted image 20210116104357.png]]
	- For the type I waveform, the amplitude of the burst-wave part is appreciably larger than the quasi-periodic waves subsequently emitted. 
		- If gravitational waves of this type are detected by gravitational-wave detectors with a low signal-to-noise ratio, it would not be very easy to confirm the detection of the quasi-periodic wave part, and essentially, the attention would be paid only to the burst-waves part.
		- GW190521 is similar to this type of waveform. This indicates a possibility that the source of GW190521 may not be a merger of high-mass binary black holes but an outcome of the collapse of a rapidly-rotating very-massive stellar core leading to a black hole and a massive disk with moderate compactness.
	- For the type II waveform, i.e., for the case of less compact and less massive disks, the amplitude of the initial burst waves is not much higher than the subsequent quasi-periodic waves.


