## Spritz: General Relativistic Magnetohydrodynamics with Neutrinos

- **Author**: Cipolletta F, Vijay Kalinani J, Giangrandi E, [[Bruno Giacomazzo]], [[Riccardo Ciolfi]], Sala L, Giudici B.
- **Summary**:
	- A new version of the publicly available general relativistic magnetohydrodynamic (GRMHD) code Spritz, which now includes an approximate neutrino leakage scheme able to handle neutrino cooling and heating.
		- The leakage scheme is based on the publicly available ZelmaniLeak code.
		- The new version of the Spritz code can be found on [Zenodo](https://zenodo.org/record/4350072#.X-FmIC0RrfY) as version 1.1.0.
- **Link**: [[Numerical Relativity]], [[General relativistic magnetohydrodynamic]], [[Numerical Methods]], [[Einstein Toolkit]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2020arXiv201210174C/abstract) Cipolletta F, Vijay Kalinani J, Giangrandi E, Giacomazzo B, Ciolfi R, Sala L, Giudici B. Spritz: General Relativistic Magnetohydrodynamics with Neutrinos. arXiv:2012.10174
- **Code**: [[Spritz Thorn]]

___

## Highlight

- In order to properly model the merger and post-merger evolution of binary neutron star (BNS) mergers and thus establish a reliable connection with their multimessenger observations, one needs to account not only for general relativistic effects, but also for other key physical ingredients such as magnetic fields, a temperature and composition dependent equation of state describing the behaviour of matter, and neutrino emission and re-absorption. [[BNS - Merger Phase]]
- We proposed a modification of the EOS_Omni thorn. This modification was accepted and it is now included in the publicly available Einstein Toolkit since May 2020.

## Basic Equations and Assumptions

We will mainly focus on the new additions to the code.

### Electron Fraction

In order to properly include neutrino emission and absorption, we need to add one evolution equation for the electron fraction, which we define as

$$
Y_{e}=\frac{n_{e}}{n_{p}+n_{n}} \tag{1}
$$
being $n_{e}$, $n_{p}$, and $n_{n}$ the electron, proton, and neutron number densities.


### Equation of State

The Spritz code can handle tabulated finite-temperature and composition dependent EOS via the [[EOS_Omni Thorn]] included in the Einstein Toolkit. This is crucial since a proper description of the matter composition depending on temperature is necessary in order to estimate the emission and absorption rates associated with the different processes involving neutrinos. Moreover, as a consequence of such processes, $Y_{e}$ necessarily undergoes changes that must be estimated accurately when dealing with dynamical scenarios.

### Neutrino Emission and Absorption

During the merger of BNS or NSBH systems, temperatures as high as $T \sim 10 \mathrm{MeV} \sim$ $10^{11} \mathrm{~K}$ can be produced and also the electron fraction $Y_{e}$ may change considerably. In this scenario, neutrinos play a key role in both the transport of energy and in determining the evolution of $Y_{e}$ and temperature, which are in turn crucial parameters for the r-process nucleosynthesis taking place in the ejected matter and the subsequent production of heavy elements.

The typical timescale for weak processes producing neutrinos can be estimated from the changing electron fraction as

$$
t_{\mathrm{WP}} \sim\left|\frac{Y_{e}}{\dot{Y}_{e}}\right| \ll t_{dyn} \tag{2}
$$
being $t_{dyn}$ the dynamical timescale of the simulated astrophysical event. By carrying away energy, neutrinos can significantly cool down the (meta)stable NS remnant of a BNS merger or the accretion disk around the spinning BH resulting from either a BNS or a NSBH merger. Moreover, a fraction of the emitted neutrinos may be reabsorbed by the outer material, inducing heating and leptonization of the material itself.

The surface where the neutrino optical depth is $\tau=2 / 3$ conventionally defines the "neutrinosphere", which separates the diffusive regime of the high-density interiors ($\gtrsim 10^{12} ~g~cm^{-3}$) and the nearly free streaming regime of the exterior. The intermediate region between $\tau \ll 1$ and $\tau \gg 1$ (i.e. where neutrinos are neither free to escape nor fully trapped) is the challenging one for neutrino transport. In its energy averaged version, the optical depth along each path $\gamma$ followed by neutrinos can be defined as

$$
\tau_{\gamma}=\int_{\gamma} \rho(\mathbf{x}) k(\mathbf{x}) \sqrt{\gamma_{i j} d x^{i} d x^{j}} \tag{3}
$$
being $k(\mathbf{x})$ the energy averaged opacity at position $\mathbf{x}$.

The complexity and extremely high computational cost of the full neutrino transport problem solved via the Boltzmann radiation transport equations forced the introduction of approximate schemes and simplifying assumptions. We consider here a so-called neutrino leakage scheme, already employed successfully in BNS and NSBH simulations.

In the neutrino leakage scheme adopted in this work, we consider three neutrino species, electron neutrino $\nu_{e}$, electron antineutrino $\bar{\nu}_{e}$, and heavy-lepton neutrinos $\nu_{x}$ (including $\nu_{\mu}, \bar{\nu}_{\mu}, \nu_{\tau}, \bar{\nu}_{\tau}$), and for each one we compute the local number and energy emission rates according to the following steps.

The neutrino optical depths, which are crucial to determine the emission rates, are computed under the assumption that neutrinos escape along radial paths from the center (ray-by-ray approach). For each species, we compute the local spectral averaged opacity as the sum of the opacities due to the scattering oﬀ nucleons, neutrinonucleus scattering, and neutrino absorption by free nucleons. Then, we use these mean opacities to compute the optical depths along each radial path.

In the diffusive regime, the number and energy rates (i.e. number and energy per unit volume, per unit time) can be written as

$$
\begin{aligned}
R_{\nu_{i}}^{\mathrm{diff}} &=\frac{4 \pi c g_{\nu_{i}}}{(h c)^{3}} \frac{\zeta_{\nu_{i}}}{3 \chi_{\nu_{i}}^{2}} T F_{0}\left(\eta_{\nu_{i}}\right) \\
Q_{\nu_{i}}^{\mathrm{diff}} &=\frac{4 \pi c g_{\nu_{i}}}{(h c)^{3}} \frac{\zeta_{\nu_{i}}}{3 \chi_{\nu_{i}}^{2}} T^{2} F_{1}\left(\eta_{\nu_{i}}\right)
\end{aligned} \tag{4}
$$
where $i=1,2,3$ and $\nu_{1}=\nu_{e}$, $\nu_{2}=\bar{\nu}_{e}$, $\nu_{3}=\nu_{x}$, while $g_{\nu_{1}}=g_{\nu_{2}}=1$ and $g_{\nu_{3}}=4$. Moreover, $\zeta=\left(E^{2} \lambda\right)^{-1}, \chi=\tau / E^{2}$, with $E$ the average neutrino energy (computed assuming a Fermi-Dirac distribution at the local temperature $T$) and $\lambda$ the mean free path, and $F_{0}(\eta), F_{1}(\eta)$ are the Fermi integrals. Energy and number rates are also computed for the free neutrino emission regime ($Q_{\nu_{i}}^{\mathrm{free}}$ and $R_{\nu_{i}}^{\mathrm{free}}$), taking into account capture processes, electron-positron pair annihilation, plasmon decay, and nucleon-nucleon bremsstrahlung. Finally, the actual emission rates are found by combining the free emission and diffusive ones as follows

$$
\begin{aligned}
R_{\nu_{i}}^{\mathrm{eff}} &=R_{\nu_{i}}^{\mathrm{free}}\left(1+\frac{R_{\nu_{i}}^{\mathrm{free}}}{R_{\nu_{i}}^{\mathrm{diff}}}\right) \\
Q_{\nu_{i}}^{\mathrm{eff}} &=Q_{\nu_{i}}^{\mathrm{free}}\left(1+\frac{Q_{\nu_{i}}^{\mathrm{free}}}{Q_{\nu_{i}}^{\mathrm{diff}}}\right) .
\end{aligned} \tag{5}
$$
For a given radial direction $(\theta, \phi)$, the isotropic-equivalent neutrino luminosity incoming from below at a distance $r$ can be computed (in the coordinate frame) as

$$
\begin{aligned}
L_{\nu_{i}}^{\mathrm{iso}}(r, \theta, \phi)=4 \pi \int_{0}^{r} &\left[\frac{\alpha\left(r^{\prime}, \theta, \phi\right)}{\alpha(r, \theta, \phi)}\right] Q_{\nu_{i}}^{\mathrm{eff}}\left(r^{\prime}, \theta, \phi\right) \alpha\left(r^{\prime}, \theta, \phi\right) W\left(r^{\prime}, \theta, \phi\right) \\
& \times\left[1+v^{r}\left(r^{\prime}, \theta, \phi\right)\right] \sqrt{g_{r r}\left(r^{\prime}, \theta, \phi\right)} r^{\prime 2} d r^{\prime}
\end{aligned} \tag{6}
$$
being $v^{r}$ the radial velocity. We can also define a fluid rest frame (FRF) luminosity as

$$
L_{\nu_{i}}^{\mathrm{iso}, \mathrm{FRF}}(r)=\frac{L_{\nu_{i}}^{\mathrm{iso}}(r)}{\alpha(r) W(r)\left[1+v^{r}(r)\right]} \tag{7}
$$
The heating and leptonization due to the reabsorption of a fraction of neutrinos by the material along their path (i,e, $\nu_{e}$ and $\bar{\nu}_{e}$ reabsorption on neutrons and protons, respectively) is taken into account via the local heating rate

$$
Q_{\left(\nu_{e}, \bar{\nu}_{e}\right)}^{\text {heat }}=f_{\text {heat }} \frac{L_{\left(\nu_{e}, \bar{\nu}_{e}\right)}^{\text {iso, } \mathrm{FRF}}}{4 \pi r^{2}} \sigma_{\left(\nu_{e}, \bar{\nu}_{e}\right)}^{\text {heat }} \frac{\rho}{m_{(n, p)}} X_{(n, p)}\left(4.275 \tau_{\left(\nu_{e}, \bar{\nu}_{e}\right)}+1.15\right) e^{-2 \tau_{\left(\nu_{e}, \bar{\nu}_{e}\right)}} \tag{8}
$$
where $f_{\text {heat}}$ is a scaling factor of order one, $\sigma_{\left(\nu_{e}, \bar{\nu}_{e}\right)}^{\text {heat}}$ is the reabsorption cross-section, $m_{(n, p)}$ and $X_{(n, p)}$ are the neutron or proton masses and mass fractions, and the factor $e^{-2 \tau_{\left(\nu_{e}, \bar{\nu}_{e}\right)}}$ is added to suppress heating at very large optical depths. For the reabsorption cross-section, we adopt the following expression

$$
\sigma_{\left(\nu_{e}, \bar{\nu}_{e}\right)}^{\text {heat }}=\frac{1+3 \alpha_{\mathrm{EC}}^{2}}{4} \sigma_{0} \frac{\left\langle E^{2}\right\rangle_{\left(\nu_{e}, \bar{\nu}_{e}\right)}^{N S}}{\left(m_{e} c^{2}\right)^{2}}\left\langle 1-f_{\left(e^{-}, e^{+}\right)}\right\rangle \tag{9}
$$
where $\alpha_{\mathrm{EC}}= −1.25$, $\sigma_{0}=1.76 \times 10^{-44} \mathrm{~cm}^{2}$, $\left\langle E^{2}\right\rangle^{N S}$ is the mean squared neutrino energy at the neutrinosphere, and $\left\langle 1-f_{\left(e^{-}, e^{+}\right)}\right\rangle$ are the blocking factors.

The full neutrino emission and reabsorption problem at a given time is solved along each radial direction by moving outwards from the center and, at each radius, subtracting the heating rate from the emission rate, i.e. $Q_{\nu_{i}}^{\mathrm{eff}} \rightarrow Q_{\nu_{i}}^{\mathrm{eff}}-Q_{\nu_{i}}^{\mathrm{heat}}$ and $R_{\nu_{i}}^{\mathrm{eff}} \rightarrow R_{\nu_{i}}^{\mathrm{eff}}-Q_{\nu_{i}}^{\mathrm{heat}} /\langle E\rangle_{\nu_{i}}^{N S}$, with $\langle E\rangle_{\nu_{i}}^{N S}$ the average neutrino energy at the neutrinosphere and $Q_{\nu_{i}}^{\mathrm{heat}}=0$.

In order to couple the result to the GRMHD evolution, the $Y_{e}$ and $\varepsilon$ are then modified as follows:

$$
Y_{e} \rightarrow Y_{e}+\Delta t \frac{\partial Y_{e}}{\partial t} \tag{10}
$$
being $\Delta t$ the local time step, and where

$$
\frac{\partial Y_{e}}{\partial t}=\frac{R_{\bar{\nu}_{e}}^{\mathrm{eff}}-R_{\nu_{e}}^{\mathrm{eff}}}{\rho} m_{n} \tag{11}
$$
being $m_{n}$ the rest-mass of the neutron, and

$$
\varepsilon \rightarrow \varepsilon+\Delta t \frac{\partial \varepsilon}{\partial t} \tag{12}
$$
where

$$
\frac{\partial \varepsilon}{\partial t}=-\frac{\Sigma_{i} Q_{\nu_{i}}^{\mathrm{eff}}}{\rho} \tag{13}
$$
