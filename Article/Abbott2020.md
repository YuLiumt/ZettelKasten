## Diving below the spin-down limit: Constraints on gravitational waves from the energetic young pulsar PSR J0537-6910

- **Author**: [[LIGO Collaboration]], [[Virgo Collaboration]], [[KAGRA Collaboration]]
- **Summary**:
	- A search for continuous gravitational-wave signals from the young, energetic X-ray pulsar PSR J0537-6910.
		- PSR J0537-6910 has the largest spin-down luminosity of any pulsar and is highly active with regards to glitches.
		- Analyses of its long-term and inter-glitch braking indices provided intriguing evidence that its spin-down energy budget may include gravitational-wave emission from a time-varying mass quadrupole moment.
		- Its 62 Hz rotation frequency also puts its possible gravitational-wave emission in the most sensitive band of LIGO/Virgo detectors.
	- We find no signal, however, and report our upper limits.
		- Assuming a rigidly rotating triaxial star, our constraints limit gravitational waves from the $l = m = 2$ mode to account for less than 14% of the spin-down energy budget.
		- The fiducial equatorial ellipticity is limited to less than about $3 \times 10^{-5}$.
- **Link**: [[Gravitational Wave]], [[Pulsar]], [[LIGO]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2020arXiv201212926T/abstract) LIGO Collaboration. Diving below the spin-down limit: Constraints on gravitational waves from the energetic young pulsar PSR J0537-6910. arXiv:2012.12926.

___

## Highlight

- PSR J0537-6910 is a particularly intriguing potential gravitational-wave source.
	- It is the fastest-spinning known young pulsar (with rotation frequency $f_{rot}=62$ Hz, which places its gravitational-wave frequency $f$ in the most sensitive band of ground-based gravitational-wave detectors.
	- PSR J0537−6910 also has the highest spin-down luminosity ($\dot{E}=4.9 \times 10^{38} \mathrm{erg} \mathrm{s}^{-1}$) among the $\sim 2900$ known pulsars in the ATNF Pulsar Catalogue.
	- Its spin-down behavior appears to be driven by a process other than pure electromagnetic dipole radiation loss (at constant stellar magnetic field and moment of inertia).
	- This behavior provides tantalizing suggestions that perhaps PSR J0537−6910 is losing some of its rotational energy to gravitational-wave emission.
	- Investigations of r-mode gravitational-wave emission (n = 7) are not presented here; such searches are more technically challenging and require different methods that search over a range of frequencies due to uncertainty in gravitational-wave frequency for a given rotation frequency.
- No evidence for gravitational-wave emission from PSR J0537−6910
	- If a loud continuous gravitational-wave signal was present, we would expect to see a narrow line feature in the spectrum.
		![[Pasted image 20201228201617.png]]
	- Though no gravitational waves are detected, we can still determine upper limits on possible gravitational-wave emission from PSR J0537−6910.
		![[Pasted image 20201229145251.png]]
		- For the single harmonic search, $h_{0}$ can be mapped to a limit on the maximum ellipticity $\varepsilon$ using equation (3).
		- The posteriors show significant support at ellipticities of zero, indicating no evidence of a signal at current sensitivities.

## Search Method

The amplitudes of each harmonic at once and twice the spin frequency of the star, denoted $h_{21}(t)$ and $h_{22}(t)$, respectively, can be written as

$$
\begin{aligned}
h_{21}=&-\frac{C_{21}}{2}\{F_{+}^{D}(\alpha, \delta, \psi ; t) \sin \iota \cos \iota \cos \left[\Phi(t)+\Phi_{21}^{C}\right] \\
&+F_{\times}^{D}(\alpha, \delta, \psi ; t) \sin \iota \sin \left[\Phi(t)+\Phi_{21}^{C}\right]\} \\
h_{22}=&-C_{22}\{F_{+}^{D}(\alpha, \delta, \psi ; t)\left(1+\cos ^{2} \iota\right) \cos \left[2 \Phi(t)+\Phi_{22}^{C}\right] \\
&+2 F_{\times}^{D}(\alpha, \delta, \psi ; t) \cos \iota \sin \left[2 \Phi(t)+\Phi_{22}^{C}\right]\}
\end{aligned} \tag{1}
$$
Here, $C_{21}$ and $C_{22}$ are dimensionless constant component amplitudes, and $\Phi_{21}^{C}$ and $\Phi_{22}^{C}$ are phase angles. $F_{+}^{D}$ and $F_{\times}^{D}$ are antenna or beam functions and describe how the two polarization components of the signal project onto the detector. Angles $(\alpha, \delta)$ are the right ascension and declination of the source, while angles $(\iota, \psi)$ specify the orientation of the star's spin axis relative to the observer. $\Phi(t)$ is the rotational phase of the source.

For a special case (i.e., $C_{21}=0$), it is simpler to write the gravitational-wave amplitude in terms of the dimensionless value $h_{0}$. The cause of such gravitational-wave emission is a deviation from axial symmetry, which can be written in terms of a dimensionless equatorial ellipticity $\varepsilon$, defined in terms of the star’s principal moments of inertia ($I_{x x}, I_{y y}, I_{z z}$):

$$
\varepsilon \equiv \frac{\left|I_{x x}-I_{y y}\right|}{I_{z z}} \tag{2}
$$
The gravitational-wave amplitude is directly proportional to the ellipticity:

$$
h_{0}=\frac{16 \pi^{2} G}{c^{4}} \frac{I_{z z} \varepsilon f_{\mathrm{rot}}^{2}}{d} \tag{3}
$$
where $d$ is the star's distance from the Earth.

The gravitational-wave amplitude $h_{0}$ can be compared to the spin-down limit amplitude $h_{0}^{sd}$, which is the gravitational-wave amplitude produced assuming that the entire rotational energy loss of the pulsar is converted into gravitational waves:

$$
h_{0}^{\mathrm{sd}}=\frac{1}{d}\left(\frac{5 G I_{z z}}{2 c^{3}} \frac{\left|\dot{f}_{\mathrm{rot}}\right|}{f_{\mathrm{rot}}}\right)^{1 / 2} \tag{4}
$$