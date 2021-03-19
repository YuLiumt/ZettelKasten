## High-Accuracy Mass, Spin, and Recoil Predictions of Generic Black-Hole Merger Remnants

- **Author**: Varma V, Gerosa D, Stein L C, Hébert F, Zhang H.
- **Summary**:
	- We present accurate fits for the remnant properties of generically precessing binary black holes, trained on large banks of numerical-relativity simulations.
		- Precessing black-hole binaries with mass ratios $q \leq 2$, and spin magnitudes $\chi_{1}, \chi_{2} \leq 0.8$.
- **Link**: [[surfinBH]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2019PhRvL.122a1101V) Varma V, Gerosa D, Stein L C, Hébert F, Zhang H. High-Accuracy Mass, Spin, and Recoil Predictions of Generic Black-Hole Merger Remnants. PRL, 2019, 122(1): 11101.

___

## Highlight

- As two black holes (BHs) come together and merge, they emit copious gravitational waves (GWs) and leave behind a BH remnant.
	- From very far away, the merger can be viewed as a scattering problem.
		![[Pasted image 20210310084730.png]]
		- The complicated dynamics of the near zone can be overlooked in favor of the gauge invariant observables of the in- and out-states: the initial BH masses and spins, the outgoing GWs, and the final BH remnant.
		- This final BH is fully characterized by its mass, spin, and recoil velocity.
- The importance of building fits for the remnant properties was realized soon after the NR breakthrough and has been periodically revisited by several groups.
	- There are two important shortcomings in all existing fitting formulae.
		- NR-calibrated coefficients are physically motivated, but lack a rigorous mathematical justification.
		- Current expressions for remnant mass and spins are calibrated on aligned-spin simulations and therefore fail to fully capture the rich physics of precessing systems.
- We construct surrogate models that fit the remnant properties from a large sample of generic, precessing, quasi-circular binary BH simulations performed with the Spectral Einstein Code (SpEC).
	- Surrogates are trained directly against the NR simulations, using Gaussian process regression (GPR) without any phenomenological ansätz, and achieve accuracies comparable to those of the NR simulations themselves.
- We present two models:
	- surfinBH7dq2: a fit trained against precessing systems with mass ratios $q \leq 2$ and dimensionless spin magnitudes $\chi_{1}, \chi_{2} \leq 0.8$.
	- surfinBH3dq8: an aligned-spin model trained against systems with mass ratios up to $q \leq 8$ and (anti-)aligned spin magnitudes $\chi_{1}, \chi_{2} \leq 0.8$.
- We construct fits for the BH remnant mass $m_{f}$, spin vector $\chi_{f}$, and recoil kick vector $\boldsymbol{v}_{f}$ as functions of the binary mass ratio $q$ and spin vectors $\chi_{1}$, $\chi_{2}$.
	- The fits are performed in the coorbital frame at $t=-100 M$, with $t=0$ at the peak of the total waveform amplitude. The coorbital frame is defined such that the $z$-axis lies along the direction of the orbital angular momentum, the $x$-axis runs from the smaller BH to the larger BH, and the $y$-axis completes the triad.
	- All fits are performed using GPR. Notably, GPR naturally returns estimates of the errors of the fitted quantities across the parameter space.