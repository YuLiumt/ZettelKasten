## Eccentric binary black hole inspiral-merger-ringdown gravitational waveform model from numerical relativity and post-Newtonian theory

- **Author**: [[Ian Hinder]], Kidder L E, Pfeiffer H P.
- **Summary**:
	- Gravitational waveforms for the inspiral, merger and ringdown of non-spinning eccentric binary black hole systems.
		- The inspiral waveform is computed using the post-Newtonian expansion.
		- The merger waveform is computed by interpolating a small number of quasi-circular NR waveforms.
			- The use of circular merger waveforms is possible because eccentric binaries circularize in the last few cycles before the merger.
- **Link**: [[Waveform Templates]], [[BBH - Orbital Eccentricity]], [[Post-Newtonian Theory]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2018PhRvD..98d4015H) Hinder I, Kidder L E, Pfeiffer H P. Eccentric binary black hole inspiral-merger-ringdown gravitational waveform model from numerical relativity and post-Newtonian theory. PRD, 2018, 98(4): 44015.
- **Code**: EccentricIMR

___

## Highlight

- We present a new set of 20 eccentric non-spinning NR simulations using the Spectral Einstein Code.
	- The NR waveforms are available in the SXS Public Waveform Catalog.
	- The NR waveforms are long enough that they start above $30 \mathrm{~Hz}(10 \mathrm{~Hz})$ for BBH systems with total mass $M \geq 80 M_{\odot}(230M_{\odot})$.
- We aim to simulate BBH configurations with a given initial frequency parameter $x$, eccentricity $e$ and mean anomaly $l$. We use the PN approximation to translate these quantities into the initial data parameters needed by SpEC.
	- This specification of initial data parameters is only an approximation, because the PN and NR quantities are expressed in different coordinate systems, and the NR initial data contains non-astrophysical junk radiation which perturbs the parameters of the binary away from those given in the initial data.
- We test our model against the NR simulations, quantifying the agreement in phase, amplitude, and faithfulness (a measure of how close the waveforms are when observed by a gravitational wave detector).
	- In the eccentric case, the situation is complicated by the fact that there is no clear general relativistic definition of eccentricity with which to label an NR waveform.
	- Since the waveforms do not agree perfectly, there is an ambiguity in the choice of PN parameters to use when comparing with a given NR waveform.
- An example of one of the eccentric waveforms.
	![[Pasted image 20210124162303.png]]
	- These modulations due to eccentricity persist at least up to $\sim 3$ cycles before the merger.
	- The instantaneous gravitational wave frequency (bottom panel) also shows oscillations due to eccentricity, where in the quasi-circular case, the frequency would vary monotonically.
- The amplitude and frequency of the gravitational wave for several eccentricities with mass ratio $q = 3$.
	![[Pasted image 20210124164928.png]]
	- We clearly see the effect of eccentricity as oscillations in both the frequency and amplitude of the waveform for $t<t_{\text {peak }}-30 M$. However, for $t>t_{\text {peak }}-30 M$, the waveforms are visually indistinguishable.
	- The lower panels of Fig. 3 show the relative difference between each eccentric configuration and the circular case. We see that for $t>t_{\text {peak }}-30 M$, the waveform amplitude and frequency differ by only $4 \%$ for all the different eccentricities at fixed mass ratio $q$.
- If the PN waveform agreed well with the NR waveform for $t<t_{\text {circ}}$, the model would now be complete, because we could match the circular waveform frequency and phase to the PN frequency and phase at $t=t_{\text {circ}}$. Unfortunately, the PN waveform cannot be extended reliably up to $t_{\text {circ}}$, and it disagrees with the circular NR waveform between $t_{\text {ref}}$ and $t_{\text {circ}}$, so this procedure would result in a merger waveform with a noticeable error in the time and phase of the peak. This is not surprising, because the PN approximation is not expected to be good so close to the merger.
	- Between $t_{\text {ref}}$ and $t_{\text {peak}}$, the IMR model is constructed by blending the PN and CMM quantities using $\alpha$.
		![[Pasted image 20210125222218.png]]


## PN Inspiral Model

Consider the relative orbit of two bodies at positions $\vec{x}_{1}$, $\vec{x}_{2}$ of masses $m_{1}$ and $m_{2}$. We restrict to the case where the bodies orbit in the $x y$ plane, since in the non-spinning case, BBH systems will orbit in a plane due to symmetry. The separation $r=\left|\vec{x}_{1}-\vec{x}_{2}\right|$ satisfies
$$
r=a[1-e \cos u] \tag{1}
$$
where $a$ is the semi-major axis of the orbit, $e$ is the eccentricity, which parametrizes the amplitude of the oscillations in $r$, and $u$ is the eccentric anomaly, an angular variable which represents the phase of the oscillation in $r$. Pericenter (point of closest approach) is at $u=0$, and $u=\pi$ corresponds to apocenter. The angular velocity of the orbit is given by
$$
\dot{\phi}=\frac{n \sqrt{1-e^{2}}}{[1-e \cos u]^{2}} \tag{2}
$$
where $n$ is the mean motion, defined as $2 \pi / P$, where $P$, the radial period, is the time between pericenter passages.

In Newtonian dynamics, the quantities $a$, $e$, $n$ and $P$ are constants, which can all be expressed in terms of the energy $E$ and angular momentum $L$; i.e. only two of them are independent. $u$ can be determined by solving the Kepler equation,
$$
l \equiv 2 \pi\left(t-t_{0}\right) / P=u-e \sin u \tag{3}
$$
a transcendental algebraic equation for $u$, where $l$ is called the mean anomaly, and $t_{0}$ is a time corresponding to pericenter passage. $l$ parametrizes the time elapsed since the preceding pericenter passage.

Each orbit can be parametrized by the four independent constants $a$, $e$, $\phi(\bar{t})$ and $l(\bar{t})$ at a time $t=\bar{t}$.

The post-Newtonian quasi-Keplerian representation of eccentric orbits is based on the above description, and utilizes the same quantities. However, the equations relating these quantities contain post-Newtonian corrections, expressed as powers of $v/c$.

Relativistic eccentric orbits have the new feature of precession of the pericenter. The azimuth of the pericenter increases by $\Delta \phi$ during one radial (pericenter to pericenter) period $P$, so that the azimuthal coordinate $\phi$ increases by $2 \pi+\Delta \phi$ during this time. $n$ no longer reduces to the angular velocity $\dot{\phi}$ in the circular limit, and instead we introduce the quantity $\omega \equiv(2 \pi+\Delta \phi) / P$, the average angular velocity. In the relativistic circular case, $\omega=\dot{\phi}$. When radiation reaction effects are neglected, $\omega$ is a constant.

In the PN model, Eq. 1 remains unchanged, but Eqs. 2–3 are modified by PN correction terms, expanded to 3 PN order. Relativistic orbits not only differ by pericenter precession and PN correction terms, but the energy and angular momentum, which in the Newtonian case are constants, also change due to the emission of gravitational waves.

We compute the gravitational wave using the restricted approximation
$$
h^{22} =-\frac{4 M \eta e^{-2 i \phi}}{R} \sqrt{\frac{\pi}{5}}\left(\frac{M}{r}+(\dot{\phi} r+i \dot{r})^{2}\right) \tag{4}
$$
