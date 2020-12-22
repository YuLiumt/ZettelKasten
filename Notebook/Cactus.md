## Cactus

Cactus is an open–source component framework designed for collaborative development of complex codes in high–performance computing environments. Cactus components are called [[Thorns]] and the integrating framework is called the [[Flesh]]. The interface between thorns and the flesh is provided by a set of configuration files writing in the [[Cactus Configuration Language]].

![[Pasted image 20201220222608.png|200]]



One essential requirement is a consistent means of describing each individual component and how it relates to both other components and the whole framework. As component frameworks are designed to be flexible by nature, the description method should be simultaneously powerful, lead to efficient code, and be easy to use, so that new users can quickly adapt their own code to work with the framework.

The Cactus API supports C/C++ and F77/F90 programming languages for the thorns. This makes it easier for scientists to turn existing codes into thorns which can then make use of the complete Cactus infrastructure, and in turn be used by other thorns within Cactus.



## History

- 1997: 1st version of Cactus just for relativity (Funding from MPG/NCSA)
- 1999: Cactus 4.0: "Cactus Einstein" thorns
- 1999-2002: EU Network "Sources of Gravitational Waves"
	- Led to Whisky Code for GR Hydro in Cactus
- 2007: LSU/RIT/PennState/GeorgiaTech: NSF XiRel

## Cactus Configuration Language

The Cactus Configuration Language (CCL) 

Cactus depends on three configuration files and two optional files provided by each thorn to direct these tasks and provide inter–thorn APIs. These files are:

- `interface.ccl` - Defines the thorn interface and inheritance along with variables and aliased functions.
- `param.ccl` - Defines parameters which can be specified in a Cactus parameter file and are set at the start of a Cactus run.
- `schedule.ccl` - Defines when and how scheduled functions provided by thorns should be invoked by the Cactus scheduler.
- `configuration.ccl` - (optional) Defines build–time dependencies in terms of provided and required capabilities, e.g. interfaces to Cactus–external libraries.
- `test.ccl` - (optional) Defines how to test a thorn’s correctness via regression tests.
