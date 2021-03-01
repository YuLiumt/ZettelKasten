## Tracking the precession of compact binaries from their gravitational-wave signal

- **Author**: Schmidt P, Hannam M, Husa S, Ajith P.
- **Summary**:
	- Find the orbital-angular-momentum direction from the GW signal.
		- The GW signal is emitted in the direction of the orbital angular momentum.
		- Track the precession of the orbital plane by selecting a frame that maximizes the amplitude of the $l=|m|=2$ modes at each time.
	- In general a spinning binary's orbital angular momentum $\mathbf{L}$ is not orthogonal to the orbital plane. Evidence that our method locates the direction of $\mathbf{L}$ rather than the normal of the orbital plane is provided by comparison with post-Newtonian (PN) results.
		- Only the total angular momentum of the spacetime is unambiguously defined in General Relativity.
- **Link**: [[Gravitational Wave]], [[BBH - Orbital Precession]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2011PhRvD..84b4046S) Schmidt P, Hannam M, Husa S, Ajith P. Tracking the precession of compact binaries from their gravitational-wave signal. PRD, 2011, 84(2): 24046.

___

## Highlight

- The Weyl scalar $\Psi_{4}$ as calculated from the numerical code is decomposed into standard spin-weighted spherical harmonics. If the orbital angular momentum of the binary is parallel to the $z$-axis, then the GW signal will be dominated by the $(\ell=2,|m|=2)$ modes.
	![[Pasted image 20210218111746.png]]
	- We locate the direction of the orbital angular momentum by searching over a range of the Euler angles $(\beta, \gamma)$ to find a global maximum in $\Psi_{4,22}$.
		- We produce a first guess of the direction of $\mathbf{L}$ from the location of the black-hole punctures at that time.
			- In general this first guess may not be very accurate. It does not take into account the time lag from the source to the GW extraction sphere.
			- Newtonian orbital angular momentum $\mathbf{L}_{\mathbf{N}}$ calculated from the puncture motion is not in general parallel to the direction that maximizes the $(\ell=2,|m|=2)$ mode.
- The time evolution of the momentum vector $\mathbf{p}$ is given by the Hamiltonian evolution equation $$\frac{d \mathbf{p}}{d t}=-\frac{\partial H}{\partial \mathbf{r}}$$ If the Hamiltonian $H$ depends on the spins, then consequently the momentum also picks up a contribution from the spins, and the velocity vector $\dot{\mathbf{r}}$ is in general not parallel to the momentum $\mathbf{p}$. Consequently, the directions of the orbital frequency vector $\Omega$, $$\Omega=\frac{\mathbf{r} \times \mathbf{v}}{r^{2}}$$ is in general not aligned with the angular momentum $\mathbf{L}=\mathbf{r} \times \mathbf{p}$.
	![[Pasted image 20210218165627.png]]