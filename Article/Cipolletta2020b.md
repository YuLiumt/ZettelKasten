## Spritz: General Relativistic Magnetohydrodynamics with Neutrinos

- **Author**: Cipolletta F, Vijay Kalinani J, Giangrandi E, [[Bruno Giacomazzo]], [[Riccardo Ciolfi]], Sala L, Giudici B.
- **Summary**:
	- A new version of the publicly available general relativistic magnetohydrodynamic (GRMHD) code Spritz, which now includes an approximate neutrino leakage scheme able to handle neutrino cooling and heating.
		- The leakage scheme is based on the publicly available ZelmaniLeak code.
		- The new version of the Spritz code can be found on [Zenodo](https://zenodo.org/record/4350072#.X-FmIC0RrfY) as version 1.1.0.
- **Link**: [[Numerical Relativity]], [[General relativistic magnetohydrodynamic]], [[Numerical Methods]], [[Einstein Toolkit]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2020arXiv201210174C/abstract) Cipolletta F, Vijay Kalinani J, Giangrandi E, Giacomazzo B, Ciolfi R, Sala L, Giudici B. Spritz: General Relativistic Magnetohydrodynamics with Neutrinos. arXiv:2012.10174
- **Code**: [[Spritz Thorn]]

#in-progress
___

## Highlight

- In order to properly model the merger and post-merger evolution of binary neutron star (BNS) mergers and thus establish a reliable connection with their multimessenger observations, one needs to account not only for general relativistic effects, but also for other key physical ingredients such as magnetic fields, a temperature and composition dependent equation of state describing the behaviour of matter, and neutrino emission and re-absorption. [[BNS - Merger Phase]]

## Basic Equations and Assumptions

We will mainly focus on the new additions to the code.

Electron Fraction

In order to properly include neutrino emission and absorption, we need to add one evolution equation for the electron fraction, which we define as

$$
Y_{e}=\frac{n_{e}}{n_{p}+n_{n}}
$$
being $n_{e}$, $n_{p}$, and $n_{n}$ the electron, proton, and neutron number densities.


Equation of State

The Spritz code can handle tabulated finite-temperature and composition dependent EOS via the EOS_Omni thorn included in the Einstein Toolkit.

This is crucial since a proper description of the matter composition depending on temperature is necessary in order to estimate the emission and absorption rates associated with the different processes involving neutrinos. Moreover, as a consequence of such processes, $Y_{e}$ necessarily undergoes changes that must be estimated accurately when dealing with dynamical scenarios.

Neutrino Emission and Absorption

During the merger of BNS or NSBH systems, temperatures as high as $T \sim 10 \mathrm{MeV} \sim$ $10^{11} \mathrm{~K}$ can be produced and also the electron fraction $Y_{e}$ may change considerably. In this scenario, neutrinos play a key role in both the transport of energy and in determining the evolution of $Y_{e}$ and temperature, which are in turn crucial parameters for the r-process nucleosynthesis taking place in the ejected matter and the subsequent production of heavy elements.

The complexity and extremely high computational cost of the full neutrino transport problem solved via the Boltzmann radiation transport equations forced the introduction of approximate schemes and simplifying assumptions. We consider here a so-called neutrino leakage scheme, already employed successfully in BNS and NSBH simulations.