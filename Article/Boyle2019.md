## The SXS Collaboration catalog of binary black hole simulations

- **Author**: SXS Collaboration
- **Summary**:
	- A major update of the Simulating eXtreme Spacetimes (SXS) Collaboration catalog of numerical simulations for merging black holes.
		- The catalog contains 2018 distinct configurations, including 1426 spin-precessing configurations, with mass ratios between 1 and 10, and spin magnitudes up to 0.998.
		- The full SXS catalog is publicly accessible at https://www.black-holes.org/waveforms.
	- Numerical accuracy can be assessed from the difference between different numerical resolutions. Precession does not change numerical accuracy of our runs, but different mass ratios and spin magnitudes do.
- **Link**: [[Binary Black Hole]], [[SXS Catalog]], [[SpEC]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2019CQGra..36s5006B) SXS Collaboration. The SXS collaboration catalog of binary black hole simulations. Classical and Quantum Gravity, 2019, 36(19): 195006.

___

## Highlight

- A number of numerical-relativity groups have begun building larger, more comprehensive catalogs, spanning more of the parameter space and including more orbits before merger.
	![[Pasted image 20201230194934.png]]
- We use the Spectral Einstein Code (SpEC) to model merging black holes and the gravitational waves they emit. [[SpEC]]
- Waveform post-processing
	- The code that we use to perform the entire extrapolation procedure is available in the open-source python module [GWFrames](https://github.com/moble/GWFrames).
	- We implement the measurement of and corrections to the COM using the open-source python module [scri](https://github.com/moble/scri).
		- All binary-black-hole systems simulated with SpEC contain essentially random offsets and drifts of the origin of coordinates relative to the COM, causing mode-mixing that manifests as irregular behavior in the waveform modes.
- Parameter space coverage
	![[Pasted image 20201230201518.png]]
	- The orbital eccentricities of these simulations are almost all below $6 \times 10^{-4}$.
		![[Pasted image 20201230201848.png]]
		- We tune our initial data via an iterative procedure to produce nearly quasicircular orbits.
		- We estimate orbital eccentricity by a least squares ﬁt of an analytic function to the time derivative of the orbital frequency $d \Omega / d t$.
	- Visualizing the coverage in spin space is difficult due to the high dimensionality, but we can focus on certain physically relevant combinations of the spin parameters.
		![[Pasted image 20201230203028.png]]
		- The effective spin $\chi_{\text {eff }} \equiv \frac{\left(m_{1} \vec{\chi}_{1}+m_{2} \vec{\chi}_{2}\right) \cdot \hat{L}}{m_{1}+m_{2}}=\frac{m_{1} \chi_{1 \|}+m_{2} \chi_{2 \|}}{m_{1}+m_{2}}$ Here $\hat{L}$ is the direction of the instantaneous Newtonian orbital angular momentum, and we carry out the projection of the spins onto $\hat{L}$ using the Euclidean metric.
			- When the effective spin is positive, the black holes merge more slowly, causing the gravitational-wave frequency to increase more slowly; conversely, when the effective spin is negative, the black holes merge more quickly, causing the gravitational-wave frequency to increase more quickly.
		- The in-plane components: $\vec{\chi}_{A \perp} \equiv \vec{\chi}_{A}-\left(\vec{\chi}_{A} \cdot \hat{L}\right) \hat{L}$
	- Compared to the properties of selected astrophysical measurements of coalescing black holes by the LIGO detectors
		![[Pasted image 20201230203903.png]]
