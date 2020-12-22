## Modeling Equal and Unequal Mass Binary Neutron Star Mergers Using Public Codes

* **Author**: De Pietri R, Feo A, Maione F, [[Frank Löffler]]
* **Summary**:
	* The dynamics of binary neutron star (BNS) mergers from the late stage of the inspiral process (the stars at a separation of 40 km) up to $\sim 20$ ms after the system has merged.
		* Five equal mass models of total gravitational mass 2.207, 2.373, 2.537, 2.697 and 2.854 $M_{\odot}$, respectively
		* Four unequal mass models with $M_{\mathrm{ADM}} \simeq 2.53 M_{\odot}$ and $q \simeq$ 0.94, 0.88, 0.83, and 0.77.
		* Seven-segment piece-wise polytropic SLyPP with a thermal component given by $\Gamma_{t h}=1.8$.
	* We have compared the resulting dynamics (for one model) using both, the BSSN-NOK and CCZ4 methods for the evolution of the gravitational sector, and different reconstruction methods for the matter sector, namely PPM, WENO and MP5.
		* Our results show agreement and high resolution, but superiority of BSSN-NOK supplemented by WENO reconstruction at lower resolutions.
* **Link**: [[Binary Neutron Star]], [[Numerical Relativity]], [[Numerical Methods]]
* [ADS](https://ui.adsabs.harvard.edu/abs/2016PhRvD..93f4047D/abstract) - De Pietri R, Feo A, Maione F, Löffler F. Modeling equal and unequal mass binary neutron star mergers using public codes. PRD, 2016, 93(6): 64047.

___

## Highlight

- All computations have been done in normalized computational units (hereafter denoted as CU) in which $c=G=M_{\odot}=1$. [[Einstein Toolkit]]
- The density in the x-y plane during various stages of the evolution.
	- Equal mass models
		![[Pasted image 20201220095439.png]]
	- Unequal mass models
		![[Pasted image 20201220101410.png]]
- Accuracy in the Determination of Merger Time  [[BNS - Merger TIme]]
	- To investigate the effect of different numerical methods on the errors (especially in the determination of merger time) and gain confidence in the obtained results, we simulated the same model (SLy14vs14) using different combinations of numerical methods, but keeping all other parameters the same. [[BSSN]], [[CCZ4]], [[NM - WENO]], [[NM - PPM]], [[NM - MP5]]
		![[Pasted image 20201220100303.png]]
		- The combination WENO and BSSNNOK performs much better at lower resolutions, at least for systems like the one we investigate here. 
		- Despite all observed differences it is important to make sure that all tested methods lead to the same determination of the **"true" merger time**, denoted as $t_{\text {merger }}(d x=0)$ as it is the merger time computed using an unlimited resolution, i.e., $d x=0$.
		- If we assume the following dependence: 
			$$
	  t_{\text {merger }}(d x)=t_{\text {merger }}^{d x=0}+A \cdot d x^{\gamma}
	  $$, we obtain $t_{\text {merger }}^{d x=0} = (10.42 \pm 0.10)$ ms and $\gamma = 1.95 \pm 0.12$ for WENO-BSSN-NOK, which is consistent with the assumption of a second-order convergence for the simulation of the merger phase.
	- One can observe that the extrapolated merger time is always consistently lower than the approximation from an EOB for all models.
		![[Pasted image 20201220102212.png]]
		- This difference could be seen as an indication for the importance of **tidal effects** on the late stage of the merger, but **it could also stem from possible differences in the initial data**. We did not evolve a high enough number of orbits before the merger to draw any firm conclusion of which one is the case.
- Models Resulting in Collapse to a Black Hole [[BNS - Merger Fate]], [[r-process]]
	- The evolution of model SLy16vs16 results in a direct collapse and the formation of a BH just after the merger. Model SLy15vs15, instead, is characterized by a delayed collapse to a BH a few milliseconds after merger.
		![[Pasted image 20201220105343.png]]
		- After the merger and subsequent collapse to a BH, the remaining matter density drops quickly below neutron drip. The fact that the remnant matter is below the neutron drip threshold is an indication that a noticeable emission of neutrinos should occur within the 10 ms that follows the merger and of the importance of the study of the r-process that may occur in neutron star mergers and on the necessity to use real Nuclear Physics EOS in the study of the post-merger phase.
	- We need for a careful study of the influence of the numerical evolution schemes, but more so the dependency of the collapse on the EOS details, especially the adiabatic index at low densities and the choice of $\Gamma_{t h}$.
		- Even small differences in these choices could potentially lead to different predictions for the estimated total energy emission in gravitational waves, and with that, their detectability.
		- An increase of $\Gamma_{t h}$ significantly delays the collapse.
		- Using the Z4c formulation of Einstein’s equations and WENO reconstruction, with the same EOS, a quite long NS lifetime of 13 ms after the merger is reported.
	- Unlike for the inspiral phase, we are not able to do a complete study of the convergence properties during the post-merger and collapse phase, e.g. for the neutron star life time, without using a higher resolution (incurring a higher computational cost). 
		- Model SLy15vs15 shows no collapse for $d x=0.75 \mathrm{CU}$ even 49 ms after the merger, while the neutron star collapses at 6.11 ms, 11.81 ms, and 7.36 ms after merger at resolutions $dx = 0.50$, $dx = 0.375$, and $dx = 0.25 CU$, respectively.
		- Further analysis would be necessary to fully establish robust convergence for the collapse time in similar models.
- Angular momentum and mass budget.
	![[Pasted image 20201220111740.png]]

## Parameters

- Lorene
	- A semi-realistic seven-segment piecewise (isentropic)-polytropic approximant, namely the SLyPP EOS, is used. Such an approximant covers the whole range of density simulated, starting from the NR atmosphere of $6.18 \cdot 10^{6} \mathrm{~g} / \mathrm{cm}^{3}$ up to the density in the interior of the NS.
		![[Pasted image 20201219230208.png]]
		$$
	\begin{array}{lll}
	\text { i } & \Gamma_{i} & \begin{array}{l}
	\rho_{i} \\
	(\mathrm{CU})
	\end{array} & \begin{array}{l}
	\rho_{i} \\
	\left(g / \mathrm{cm}^{3}\right)
	\end{array} \\
	\hline 0 & 1.58425 & 1 \times 10^{-11} & \simeq 6.18 \times 10^{6} \\
	1 & 1.28733 & 3.951156 \times 10^{-11} & \simeq 2.43 \times 10^{7} \\
	2 & 0.62223 & 6.125960 \times 10^{-7} & \simeq 3.78 \times 10^{11} \\
	3 & 1.35692 & 4.254672 \times 10^{-6} & \simeq 2.63 \times 10^{12} \\
	4 & 3.005 & 2.367449 \times 10^{-4} & \simeq 1.46 \times 10^{14} \\
	5 & 2.988 & 8.114721 \times 10^{-4} & \simeq 5.01 \times 10^{14} \\
	6 & 2.851 & 1.619100 \times 10^{-3} & \simeq 1.00 \times 10^{15} \\
	\hline
	\end{array}
	$$
	- SLyPP supplemented by a thermal component $\Gamma_{\mathrm{th}}=1.8$.
		- In the low-density region $\Gamma_{\mathrm{th}}$ should approach $4 / 3$, since there the pressure is provided primarily by an ideal gas of ultra-relativistic electrons and photons, so we overestimate the pressure support.
		- A value of $\Gamma_{\mathrm{th}}=2.0$ seems to be too high, while a value of $\Gamma_{\mathrm{th}}=1.5$ might yield a too low pressure support in the core.
	- Equal and unequal mass binary neutron star mergers. All these models were generated to be at a relative physical distance of 40 km.
		![[Pasted image 20201219225633.png]]
- Einstein Toolkit
	- Fourth-order Runge-Kutta method with Courant factor 0.25. Kreiss-Oliger dissipation was applied to the curvature evolution quantities in order to damp high-frequency noise.
	- Fourth-order finite difference stencils for the curvature evolution, 1 + log slicing, and a $\Gamma$-driver shift condition. A Sommerfeld-type radiative boundary condition is applied.
	- An artificial low-density atmosphere with $\rho_{\mathrm{atm}}=10^{-11} \mathrm{CU}$ is used.
	- A mirror symmetry across the (x, y) plane.
	- Grid boundaries of refinement levels
		![[Pasted image 20201220104133.png]]

## Computational Cost

We needs a careful analysis of the computational cost of the simulations (the number of CPU core hours needed to perform each simulation) and a careful management of resources. In that, speed, and with that total runtime, however, are not the only variables to consider.

With the computational domain completely specified (i.e., the resolution and the size of the computational grid), the next step of an analysis of the computational cost is to asses the cost for a full simulation of a particular model at the desired resolution. Table VI shows the actual simulation cost as function of resolution.

![[Pasted image 20201220093656.png]]
