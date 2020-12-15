## Einstein Toolkit

Tags: #important 

The Einstein Toolkit is a free, publicly available, community-driven [[General Relativity]] (GR) code based on the Cactus Framework. 

Cactus is a component framework. Its components are called [[Thorns]] whereas the framework itself is called the [[Flesh]].

> The Cactus API supports C/C++ and F77/F90 programming languages for the thorns. This makes it easier for scientists to turn existing codes into thorns which can then make use of the complete Cactus infrastructure, and in turn be used by other thorns within Cactus.

## Computational Units (CU)

All computations have been done in normalized computational units (hereafter denoted as CU) in which $c=G=M_{\odot}=1$. 






The spacetime metric evolution is performed by the McLachlan module, implementing a 3 + 1 dimensional split of the Einstein Equations using the BSSN-NOK formalism.


The General Relativistic Hydrodynamics (GRHD) equations are solved by the module **GRHydro**. 

## Tools

- [[Simulation Factory]]
- Visualization
	- Visit
	- CactusTool
- Code Generate
	- [[Kranc]]
	- NRPy+