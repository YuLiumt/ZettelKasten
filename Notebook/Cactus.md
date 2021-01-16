## Cactus

Cactus is an open–source component framework designed for collaborative development of complex codes in high–performance computing environments. Cactus components are called [[Thorns]] and the integrating framework is called the [[Flesh]]. The interface between thorns and the flesh is provided by a set of configuration files writing in the [[Cactus Configuration Language]].

![[Pasted image 20201220222608.png|200]]



One essential requirement is a consistent means of describing each individual component and how it relates to both other components and the whole framework. As component frameworks are designed to be flexible by nature, the description method should be simultaneously powerful, lead to efficient code, and be easy to use, so that new users can quickly adapt their own code to work with the framework.

The Cactus API supports C/C++ and F77/F90 programming languages for the thorns. This makes it easier for scientists to turn existing codes into thorns which can then make use of the complete Cactus infrastructure, and in turn be used by other thorns within Cactus.



## History

- The first version of Cactus was written at the [[AEI]] around 1995.
- By 1999 it was completely redesigned and rewritten.

## Cactus Configuration Language

The Cactus Configuration Language (CCL) 

Cactus depends on three configuration files and two optional files provided by each thorn to direct these tasks and provide inter–thorn APIs. These files are:

- `interface.ccl` - Defines the thorn interface and inheritance along with variables and aliased functions.
- `param.ccl` - Defines parameters which can be specified in a Cactus parameter file and are set at the start of a Cactus run.
- `schedule.ccl` - Defines when and how scheduled functions provided by thorns should be invoked by the Cactus scheduler.
- `configuration.ccl` - (optional) Defines build–time dependencies in terms of provided and required capabilities, e.g. interfaces to Cactus–external libraries.
- `test.ccl` - (optional) Defines how to test a thorn’s correctness via regression tests.


## Developer

- [Gabrielle Allen](https://www.cactuscode.org/about/team/gallen)
- [[Frank Löffler]]
- [Steven R. Brandt](https://www.cactuscode.org/about/team/sbrandt)
- [David Rideout](https://www.cactuscode.org/about/team/drideout)
- [[Erik Schnetter]]
- [[Roland Haas]]
- [Ian Hinder](https://www.cactuscode.org/about/team/hinder)
- [Eloisa Bentivegna](https://www.cactuscode.org/about/team/ebentivegna)

## Citation

The BibTeX entry:

```bibtex
@InProceedings{Goodale2002a, 
	author = {Tom Goodale and Gabrielle Allen and Gerd Lanfermann and Joan Mass{\\'o} and Thomas Radke and Edward Seidel and John Shalf}, 
	title = {The {Cactus} Framework and Toolkit: Design and Applications}, 
	booktitle = {Vector and Parallel Processing -- VECPAR'2002, 5th International Conference, Lecture Notes in Computer Science}, 
	year = 2003, 
	address = {Berlin}, 
	publisher = {Springer}, 
	url = {http://edoc.mpg.de/3341}, 
}
```