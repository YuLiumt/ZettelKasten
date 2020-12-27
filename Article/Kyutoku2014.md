## Reducing orbital eccentricity in initial data of binary neutron stars

* **Author**: Kyutoku K, [[Masaru Shibata]], Taniguchi K.
* **Summary**:
	* We develop a method to reduce orbital eccentricity in initial data of binary neutron stars.
	* The eccentricity can be reduced by an order of magnitude compared to standard quasicircular initial data, specifically from $\sim 0.01$ to $\lesssim 0.001$.
	* Low eccentricity initial data exhibit smaller modulations in evolution of the orbital separation, gravitational-wave amplitude, and gravitational-wave frequency than quasicircular initial data.
	* The eccentricity could affect properties of remnant massive neutron stars and mass ejection from the system, and hence electromagnetic signals.
* **Link**: [[Binary Neutron Star]], [[NR - Initial Data]]
* [ADS](https://ui.adsabs.harvard.edu/abs/2014PhRvD..90f4006K) Kyutoku K, Shibata M, Taniguchi K. Reducing orbital eccentricity in initial data of binary neutron stars. PRD, 2014, 90(6): 64006.

___

## Highlight

- Reducing the orbital eccentricity is an urgent task in numerical relativity.
	- High demand to derive accurate gravitational waveforms. Although mismatch due to the orbital eccentricity in quasicircular initial data is reported to be merely $\sim 1 \%$ in binary black hole simulations if we focus only on the numerical-relativity waveforms, the eccentricity complicates comparisons between gravitational waveforms obtained by numerical simulations and those derived by analytic methods both for binary black holes and binary neutron stars.
	- The extraction of tidal deformability from gravitational waves is fairly sensitive to the accuracy of templates, and thus reducing the orbital eccentricity is critical to maximizing the precision with which we can extract neutron-star parameters and constrain the neutron-star equations of state from gravitational-wave observations.
- We demonstrated the ability of our eccentricity reduction by simulating two families of equal-mass binary neutron stars. [[BNS - Orbit Eccentricity]]
	- Brieﬂy summarize the setup of numerical simulations
		![[Pasted image 20201219170318.png]]
	- The amplitude of modulations in $\dot{\Omega}(t)$ decreases monotonically as the iterative eccentricity reduction proceeds.
		![[Pasted image 20201219171214.png]]
	- Low eccentricity initial data exhibit smaller modulations in evolution of the orbital separation. This sharp decline in modulation is clear evidence of the efficacy of our eccentricity reduction method.
		![[Pasted image 20201219181820.png]]
	- The time to merger increases as the eccentricity decreases.
		![[Pasted image 20201219180058.png]]
		- This cannot be explained by strong gravitational radiation from an eccentric binary, because the quadrupole formula predicts that the time to merger from a given semimajor axis is proportional to $1-(157 / 43) e^{2}$ at leading order of $e$. The actual difference in the time to merger is, however, $\sim 5 \%$ between QC and Iter3 and is thus too large.
		- Instead, this difference is ascribed to the initial semimajor axis of the binary. Numerical results suggest that apastron distances are approximately the same irrespective of the eccentricity reduction, and the semimajor axis is shorter by $1-e$. Thus, the time to merger should be proportional to $1-4 e$ at leading order of $e$. This approximately explains the difference of the time to merger.
	- The modulations in the amplitude evolution is roughly consistent with the expectation that the amplitude should vary by $(3 / 2) e$ at leading order of $e$ in the quadrupole approximation.
		![[Pasted image 20201219182712.png]]
	- Low-eccentricity initial data may yield smoother spectra than quasicircular ones, and characteristics of remnant massive neutron stars do not depend strongly on the eccentricity.
		![[Pasted image 20201219183858.png]]
	- Because this reduction factor is common to both the H4-135 and APR4-14 families, we believe it will not depend on the compactness of the neutron star.
- The ejecta mass seems to vary by $O(10 \%)$ between quasicircular and low-eccentricity initial data. [[BNS - Dynamical ejecta]]
	- This variation is not always systematic with respect to the eccentricity, possibly because the velocity at the contact of binary neutron stars can fluctuate within the eccentricity-driven modulation in each particular simulation.
	- We do not present results for them in detail here, because quantitative conclusions require systematic investigations with convergence analysis.

## Estimate Orbital Eccentricity

We define the location of a stellar center $x_{\mathrm{NS}}^{i}=\left(x_{\mathrm{NS}}, y_{\mathrm{NS}}, 0\right)$ at each time step by a point of the maximum conserved rest-mass density $\rho_{*}=\rho \alpha u^{t} \sqrt{\gamma}$ on computational grids, where two distinct points corresponding to two stars are tracked during the inspiral. The coordinate orbital separation $d(t)$ and orbital phase $\phi(t)$ are directly computed as

$$
\begin{array}{l}
d(t)=\sqrt{\left(x_{\mathrm{NS}, 1}-x_{\mathrm{NS}, 2}\right)^{2}+\left(y_{\mathrm{NS}, 1}-y_{\mathrm{NS}, 2}\right)^{2}} \\
\phi(t)=\arctan \left(\frac{y_{\mathrm{NS}, 1}-y_{\mathrm{NS}, 2}}{x_{\mathrm{NS}, 1}-x_{\mathrm{NS}, 2}}\right)+2 \pi N
\end{array}
$$
where the label 1 or 2 stands for a member of the binary. The orbital phase has a freedom of adding an integer multiple of $2 \pi$, and it is fixed to be continuous by appropriately choosing an integer $N$, which is essentially the number of orbits.

The time derivative of the orbital separation $\dot{d}(t)$, orbital angular velocity $\Omega(t) \equiv \dot{\phi}(t)$, and its time derivative $\dot{\Omega}(t)$ are computed from them by fourth-order finite differentiation. we use $\dot{\Omega}(t)$ for the orbital analysis, because this should vanish in the absence of radiation reaction for a genuinely circular orbit. This should also be true of $\dot{d}(t)$.

Because our numerical grids are discrete, the orbital evolution determined in this manner inevitably contains a spurious high-frequency oscillation of the order of the grid separation. we considered as an alternate definition of the coordinate center of each neutron star the integral form

$$
x_{\mathrm{NS}, \mathrm{integ}}^{i} \equiv \frac{\int \rho_{*} x^{i} d^{3} x}{\int \rho_{*} d^{3} x}
$$
This determination is found to be fully consistent with $x_{\mathrm{NS}}^{i}$ described above and is less subject to the high-frequency oscillations due to the discrete grids.

We assume that $\dot{\Omega}(t)$ is modeled by

$$
\dot{\Omega}(t)=A_{0}+A_{1} t+B \cos \left(\omega t+\phi_{0}\right)
$$
where $\left\{A_{0}, A_{1}, B, \omega, \phi_{0}\right\}$ are fitting parameters. The numerical evolution data are fitted to determine these parameters. The modulation term $B \cos \left(\omega t+\phi_{0}\right)$ should be ascribed to the eccentricity, whereas the secular terms $A_{0}+A_{1} t$ should result from gravitational radiation reaction.

A time interval has to be chosen carefully to perform the fitting. First, the duration has to be long enough to include more than one modulation cycle associated with the eccentricity. Next, it has to be short enough to avoid strong influence of long-term secular evolution. Taking these issues, we use $t \in[0.5 P: 3 P]$ for the fitting, where $P \equiv 2 \pi / \Omega$ is the initial orbital period and $\Omega$ is the orbital angular velocity.

The eccentricity is estimated from the modulation term using the knowledge of Newtonian two-body dynamics with $e \ll 1$. We estimate the eccentricity of initial data mainly from the fitting parameters as

$$
e \approx \frac{|B|}{2 \omega \Omega}
$$
which is derived by an expected Newtonian relation $\Omega(t) \approx \Omega\left[1+2 e \sin \left(\omega t+\phi_{0}\right)\right]$ at $e \ll 1$.

## Eccentricity Reduction

Computations of quasicircular binary neutron stars have been carried out assuming the existence of a helical Killing vector field with the orbital angular velocity $\Omega$. Because this formulation neglects the gravitational radiation reaction and does not appropriately incorporate the approaching velocity, a binary prepared in this manner evolves as a slightly but appreciably eccentric binary once a numerical simulation is launched.

One plausible way to incorporate an approaching velocity may be to add uniform contraction to the helical Killing vector in the manner

$$
\xi^{\mu}=\left(\partial_{t}\right)^{\mu}+\Omega\left(\partial_{\varphi}\right)^{\mu}+v \frac{r}{r_{0}}\left(\partial_{r}\right)^{\mu} \tag{5}
$$
Here, $v$ (negative for the approaching velocity) and $r_{0}$ should be regarded as the radial velocity and separation from the coordinate origin, respectively.

> The radial velocity term, $r\left(\partial_{r}\right)^{i}$, is not divergence free. This suggests that a neutron star with the approaching velocity represented by this form has a contracting density profile. Such initial data might introduce unphysical oscillations of neutron stars.

We compute low-eccentricity initial data by modifying the orbital angular velocity, $\Omega$, and approaching velocity, $v$, of given binary initial data. 

$$
\begin{aligned}
\delta \Omega &=-\frac{B \omega \sin \phi_{0}}{4 \Omega^{2}} \\
\delta v &=\frac{B d \cos \phi_{0}}{2 \times 2 \Omega}
\end{aligned}
$$

The eccentricity can be reduced by an order of magnitude by three successive iterations.