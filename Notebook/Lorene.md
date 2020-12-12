# Lorene

LORENE is a set of C++ classes. It provides tools to solve partial differential equations by means of multi-domain spectral methods. [[Numerical Methods#Spectral Methods]]

[RIT Binary Neutron Star Initial Data Library](https://aspire.rit.edu/content/data/bns-initial-data)

Our initial data are generated with the open source **LORENE** library, which is able to compute quasi-equilibrium configurations for binary irrotational neutron stars in quasi-circular orbits.

## LORENE's class




### Bin_star

Generating corotating and irrotational quasiequilibrium [[Binary Neutron Star]] with various [[Equation of State]].

Required executables and parﬁles before run it.

1. The parameter files for the code `init_bin.C` are: `par_eos[1, 2].d`, `par_grid[1, 2].d`, and `par_init.d`.
	```bash
	make init_bin
	./init_bin
	```
2. There is only one parameter file for the code `coal.C`: `parcoal.d`.
	```bash
	make coal
	./coal
	```

`./init_bin` output is the unrelaxed binary configuration with given stellar models and specified binary separation. To generate a relaxed binary configuration, we need the `./coal`.

![[Pasted image 20201210193230.png]] 
The most stable results begin from low mass configurations, moving inwards to the desired radius, and then slowly increasing the target mass of the binary.

The output result is contained in a binary file called `resu.d`, which is readable by appropriate routines in [[Einstein Toolkit]].

```C++
// Saveguard of the whole configuration
FILE * fresu = fopen("resu.d", "w") ;

star.get_mp().get_mg()->sauve(fresu) ; // writing of the grid
star.get_mp().sauve(fresu) ;           // writing of the mapping
star.get_eos().sauve(fresu) ;          // writing of the EOS
star.sauve(fresu) ;                    // writing of the star

fclose(fresu) ;
```

Check the outputs at the end, make sure there are no `NaN`. Only then use the `resu.d` for evolving the binary.

* Lorene cannot generate consistent initial data with (noncorotating) spin with specified eccentricities.
* When one evolves quasicircular initial data, one obtains an eccentricity of ~0.01. [[Maione2016]]
* There is no known way of including magnetic fields consistently in binary neutron star initial data.
* they also generally have difficulty reaching large compactness and high mass ratios.
	* The BNS system with the pulsar J043+1559 has a high total mass and a large mass asymmetry (with a mass ratio of $0.75$, never observed before). The discovery of this system has been very important, because it testifies the need for studying with numerical simulations also binaries with large mass asymmetry.


* Adjust the parameter of baryonic mass to obtain the desired chirp mass and mass ratio. [[Maione2016]]




