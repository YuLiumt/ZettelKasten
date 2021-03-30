## Surrogate models for precessing binary black hole simulations with unequal masses

- **Author**: Varma V, Field S E, Scheel M A, Blackman J, Gerosa D, Stein L C, Kidder L E, Pfeiffer H P.
- **Summary**:
	- We present two new fast and accurate surrogate models: the first model, NRSur7dq4, predicts the gravitational waveform and the second model, NRSur7dq4Remnant, predicts the properties of the remnant black hole.
		- The waveform model, NRSur7dq4, which begins about 20 orbits before merger, includes all $\ell \leq 4$ spin-weighted spherical harmonic modes, as well as the precession frame dynamics and spin evolution of the black holes.
		- The final black hole model, NRSur7dq4Remnant, models the mass, spin, and recoil kick velocity of the remnant black hole.
	- They are trained against 1528 precessing NR simulations with mass ratios $q \leq 4$, spin magnitudes $\chi_{1}, \chi_{2} \leq 0.8$, and generic spin directions.
		- All fits are performed using Gaussian Process Regression (GPR).
- **Link**: [[surfinBH]], [[Gaussian Process Regression]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2019PhRvR...1c3015V) Varma V, Field S E, Scheel M A, Blackman J, Gerosa D, Stein L C, Kidder L E, Pfeiffer H P. Surrogate models for precessing binary black hole simulations with unequal masses. Physical Review Research, 2019, 1(3): 33015.

___

## Highlight

- Only numerical relativity simulations can capture the full complexities of binary black hole mergers. These simulations, however, are prohibitively expensive for direct data analysis applications such as parameter estimation.
- The most important outputs of NR simulations are the gravitational waveform and the mass, spin, and recoil kick velocity of the remnant BH left after the merger.
	- The recoil kick is astrophysically important because it can cause the remnant BH to be ejected from its host galaxy.
- Among BBHs, systems with BH spins that are misaligned with respect to the orbital angular momentum are complicated to model analytically or semi-analytically. For these systems, the spins interact with both the orbital angular momentum and each other, causing the system to precess about the direction of the total angular momentum. This precession is imprinted on the waveform as characteristic modulations in the amplitude and frequency of the GWs, and can be used to extract information about the spins of the source.
	- One important application of the extracted spins is to distinguish between formation channels of BBHs.
- In fact, since most precessional effects are accounted for by the frame rotation, the waveform in the coprecessing frame is qualitatively similar to that of a nonprecessing system.
- Although NRSur7dq4Remnant is parameterized internally by input spins specified in the coorbital frame at $t=-100 M$, we allow the user to specify input spins at earlier times, and in the inertial frame. Given the inertial-frame input spins at an initial orbital frequency $f_{0}$.


The dimensionless orbital angular frequency used to determine t\_ref, which is the time derivative of the orbital phase in the coprecessing frame.