## Implementation of Monte-Carlo transport in the general relativistic SpEC code

- **Author**: Foucart F, Duez M D, Hebert F, Kidder L E, Pfeiffer H P, Scheel M A.
- **Summary**:
	- A detailed description of the Monte-Carlo radiation transport algorithm implemented in the SpEC merger code.
		- We discuss in particular the approximations used to circumvent known issues with the use of Monte-Carlo algorithms in optically thick regions, which are the main difficulty encountered when attempting to use Monte-Carlo methods in neutron star mergers.
- **Link**: [[Spectral Einstein Code]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2021arXiv210316588F) Foucart F, Duez M D, Hebert F, Kidder L E, Pfeiffer H P, Scheel M A. Implementation of Monte-Carlo transport in the general relativistic SpEC code. arXiv:2103.16588

___

## Highlight

- Numerical simulations of neutron star mergers play an important role in our ability to predict the amount of matter ejected, as well as the composition, velocity, and geometry of the outflows.
	- Three important problems continue to limit our ability to reliably predict the properties of matter outflows:
		- our inability to resolve magnetic fields
		- our approximate treatment of neutrino transport
		- a lack of consistency between merger and post-merger simulations that makes it difficult to interpret the result of the longest 3D post-merger simulations currently at our disposal
- Neutrino transport and neutrino-matter interactions are known to play an important role in the evolution of neutron star mergers, and of their post-merger remnants.
	- Neutrinos cool remnants, drive post-merger winds, and deposit energy in the low-density polar regions where relativistic jets may eventually form.
	- Neutrinos also modify the composition of the ejected material, impacting the outcome of nucleosynthesis in merger outflows and the properties of the optical/infrared transients that they power (kilonovae).
	- Neutrino-antineutrino pair annihilation in the low-density polar regions can deposit a significant amount of energy above the remnant, and may contribute to the formation of a baryon-free zone in that region and the eventual production of a relativistic jet.
- So far, merger simulations have largely relied on approximate treatments of the neutrinos (leakage, moments) that simplify the equations of radiation transport in a way that makes simulations more affordable, but also introduces unquantifiable errors in the results.
	- The total neutrino luminosity can be captured within factors of a few by a leakage scheme, but the composition of the outflows cannot be reliably measured in leakage simulations. Leakage schemes however have the distinct advantage of being inexpensive to use in simulations, and remain a common way to approximately treat neutrino-matter interactions.
- Going to an actual evolution of Boltzmann’s equations of radiation transport is generally a more expensive proposition. Boltzmann’s equation requires the evolution in time of a 6-dimensional distribution function for each species of neutrinos, with stiff source terms that couple neutrinos to the fluid, as well as couplings between neutrinos of different energy, direction of propagation, and/or species.
	- A brute force discretization of this equation on a 6D finite difference grid is unlikely to be affordable any time soon.