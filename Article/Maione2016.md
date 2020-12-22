##  Binary neutron star merger simulations with different initial orbital frequency and equation of state.

* **Author**: Maione, F.; De Pietri, R.; Feo, A. & [[Frank Löffler]]
* **Summary**:
    - We present long-term equal-mass BNS simulations with four different nuclear EOSs, starting with four different values of the interbinary distance d (40, 44.3, 50, and 60 km).
	- The comparison of simulations starting from different initial orbital frequencies is a necessary and fundamental test to evaluate the accuracy of current numerical BNS simulations and their ability to model tidal effects.
	- We analyzed the effect of the different initial interbinary distance on the post-merger gravitational signal.
* **Link**: [[Binary Neutron Star]], [[Numerical Relativity]], [[Lorene]], [[Equation of State]], [[Gravitational Wave Extraction]]
* [ADS](https://ui.adsabs.harvard.edu/abs/2016CQGra..33q5009M) - Maione F, De Pietri R, Feo A, Löffler F. Binary neutron star merger simulations with different initial orbital frequency and equation of state. Classical and Quantum Gravity, 2016, 33(17): 175009.

___

## Highlight

* Long numerical simulations are needed. [[BNS - Inspiral phase]]
    * It is quite obvious from the figure that all simulations with the same EOS agree well during the first part of the coalescence, and start to diverge in the plunge phase, where simulations starting from closer interbinary distances have a slower phase evolution.
    	![[Pasted image 20201210192238.png]]
* Baryonic mass is always used as an input parameter in Lorene. [[Lorene - Binaire]]
	* Since the gravitational mass of each star is not conserved during the evolution but depends on the gravitational binding energy we decided to generate our initial models fixing the conserved Baryonic mass to $1.4 M_{\odot}$
* imprint of a small eccentricity in the orbital evolution. [[Lorene - Binaire]]
	* The amplitude of the gravitational wave strain shows a characteristic oscillation in all our simulations.
	* The effect of the orbital eccentricity is clearly recognizable in the distance oscillations.
		![[Pasted image 20201210194047.png]]
		$$
	\begin{array}{|c|ccc|}
	\hline & \mathrm{e} & \mathrm{e} & \mathrm{e} \\
	\mathrm{EOS} & d=60 \mathrm{~km} & d=50 \mathrm{~km} & d=44.3 \mathrm{~km} \\
	\hline \text { APR } 4 & 0.028 & 0.020 & 0.020 \\
	\hline \text { SLy } & 0.025 & 0.019 & 0.020 \\
	\hline \text { H4 } & 0.012 & 0.012 & 0.014 \\
	\hline \text { MS1 } & 0.014 & 0.014 & 0.007 \\
	\hline
	\end{array}
	$$
* Binary starting with zero radial velocity. [[BNS - Merger TIme]]
	* The simulations starting from a closer interbinary distance took longer to merge compared to ones starting from further apart, when comparing over the same distance before merger. 
	* This effective merger time difference was found to be higher for more compact stars.
* The post-merger effect should be checked again in simulations with higher resolutions and post-merger simulated time. [[BNS - Postmerger Spectrum]]
	* Simulations starting from $d = 60 km$ have the dominant peak at a somewhat lower frequency (but still consistent with the error) than the others. 
		 ![[Pasted image 20201212211152.png]]
		$$
	\begin{array}{|c|c|c|c|}
	\hline \text { Model } & f_{p}(\mathrm{kHz}) & f_{-}(\mathrm{kHz}) & f_{\text {merger }}(\mathrm{kHz}) \\
	\hline \text { APR4(a) } & 3.34 & 2.14 & 1.97 \\
	\text { APR4(b) } & 3.26 & 2.08 & 1.97 \\
	\text { APR4(c) } & 3.29 & 2.02 & 1.94 \\
	\text { APR4(d) } & 3.19 & 2.02 & 1.87 \\
	\hline \text { SLy(a) } & 3.19 & 2.15 & 1.92 \\
	\text { SLy(b) } & 3.24 & 2.08 & 1.88 \\
	\text { SLy(c) } & 3.13 & 2.03 & 1.87 \\
	\text { SLy(d) } & 3.07 & 1.92 & 1.72 \\
	\hline \text { H4(a) } & 2.38 & 1.64 & 1.44 \\
	\text { H4(b) } & 2.39 & 1.66 & 1.46 \\
	\text { H4(c) } & 2.35 & 1.64 & 1.44 \\
	\text { H4(d) } & 2.24 & 1.58 & 1.41 \\
	\hline \text { MS1(a) } & 2.05 & 1.42 & 1.29 \\
	\text { MS1(b) } & 2.05 & 1.43 & 1.33 \\
	\text { MS1(c) } & 2.07 & 1.39 & 1.32 \\
	\text { MS1(d) } & 1.93 & 1.37 & 1.26 \\
	\hline
	\end{array}
	$$

## Estimate Orbital Eccentricity

We computed the trajectories by following the dynamics of the star centers, defined as the points on the numerical grid with the maximum density $\rho$. Next, we computed the coordinate distance $D$ between the star centers at each time step, and fitted its derivative with the following Newtonian approximation for the orbital evolution:

$$
\dot{D}(t)=A_{0}+A_{1} t-e D_{0} \omega_{e} \sin \left(\omega_{e} t+\phi_{e}\right)
$$

where $e$ is the eccentricity and $D_{0}=d$ the initial coordinate interbinary distance.

The fit is performed in the time interval between $t_{\mathrm{ret}}=3 \mathrm{~ms}$ and $t_{\mathrm{ret}}=\frac{2}{3} t_{\mathrm{merger}}$, to avoid **the initial spurious radiation** and **the plunge phase** but having at least one eccentricity cycle included.

## Parameters

- Lorene
	- An equal mass binary system using four different EOSs for the cold nuclear matter, [[APR4 EOS]], [[SLy EOS]], [[H4 EOS]], and [[MS1 EOS]].
		$$
	\begin{array}{|c|ccc|c|cc|c|}
	\hline \text { EOS } & \Gamma_{4} & \Gamma_{5} & \Gamma_{6} & \rho_{3}\left(g / c m^{3}\right) & M_{\text {grav}}\left[M_{\odot}\right] & R(k m) & \text { C } \\
	\hline \text { APR4 } & 2.830 & 3.445 & 3.348 & 1.512 \times 10^{14} & 1.2755 & 11.33 & 0.1662 \\
	\hline \text { SLy } & 3.005 & 2.988 & 2.851 & 1.4622 \times 10^{14} & 1.2809 & 11.76 & 0.1608 \\
	\hline \text { H4 } & 2.909 & 2.246 & 2.144 & 0.8877 \times 10^{14} & 1.3003 & 14.00 & 0.1371 \\
	\hline \text { MS1 } & 3.224 & 3.033 & 1.325 & 0.9416 \times 10^{14} & 1.3048 & 14.90 & 0.1293 \\
	\hline
	\end{array}
	$$
	- The dynamical evolution from four different values of coordinate distance between the star centers.
		$$
	\begin{array}{|c|cccc|}
	\hline \text { Model name } & d_{0}(\mathrm{~km}) & M_{A D M}\left(M_{\odot}\right) & J_{A D M}\left(G M_{\odot}^{2} / c\right) & \Omega_{0}(\mathrm{rad} / \mathrm{s}) \\
	\text { APR4(a) } & 40 & 2.5255 & 6.3594 & 2036 \\
	\text { APR4(b) } & 44.3 & 2.5275 & 6.5771 & 1767 \\
	\text { APR4(c) } & 50 & 2.5298 & 6.8603 & 1492 \\
	\text { APR4(d) } & 60 & 2.5329 & 7.3385 & 1153 \\
	\hline \text { SLy(a) } & 40 & 2.5361 & 6.4051 & 2040 \\
	\text { SLy(b) } & 44.3 & 2.5382 & 6.6233 & 1770 \\
	\text { SLy(c) } & 50 & 2.5404 & 6.9073 & 1494 \\
	\text { SLy(d) } & 60 & 2.5435 & 7.3876 & 1155 \\
	\hline \text { H4(a) } & 40 & 2.5744 & 6.5876 & 2056 \\
	\text { H4(b) } & 44.3 & 2.5764 & 6.8024 & 1782 \\
	\text { H4(c) } & 50 & 2.5787 & 7.0876 & 1504 \\
	\text { H4(d) } & 60 & 2.5819 & 7.5740 & 1163 \\
	\hline \text { MS1(a) } & 40 & 2.5833 & 6.6434 & 2063 \\
	\text { MS1(b) } & 44.3 & 2.5852 & 6.8503 & 1786 \\
	\text { MS1(c) } & 50 & 2.5875 & 7.1313 & 1506 \\
	\text { MS1(d) } & 60 & 2.5907 & 7.6164 & 1164 \\
	\hline
	\end{array}
	$$
- Einstein Toolkit
	- The data are evolved on a Cartesian mesh with 6 levels of mesh refinement.
	- The outer boundary of the grid is set at 1063 km from its center, to be able to extract the gravitational signal far from the source.
	- The standard grid spacing on the innermost level used for this paper is $d x=369 \mathrm{~m}$.
	- We used a mirror symmetry across the $(x, y)$ plane consistent with the symmetry of the problem.
	- The time integration is performed with a fourth-order Runge-Kutta method with a constant Courant factor of 0.25.
	- The EOS is supplemented by a thermal component with $\Gamma_{\mathrm{th}}=1.8$.
	- We extracted $\psi_{4}$ components up to $l = 6$.
	- extracting $\psi_{4}$ at seven different equidistant radii from $R=400 \mathrm{CU}(591 \mathrm{~km})$ to $R=700 \mathrm{CU}(1034 \mathrm{~km})$.