## Llama

- [Homepage](https://llamacode.bitbucket.io)

The Llama code is a 3-dimensional multiblock infrastructure with adaptive mesh-refinement for [[Cactus]] based on [[Carpet]]. It provides different patch systems that cover the simulation domain by a set of overlapping patches. Each of these patches has local coordinates with a well-defined relation to global Cartesian coordinates. However, all computations are carried out using a global Cartesian tensor basis such that complicated tensor transformations between patch systems can be avoided. Information between the different patches is communicated via interpolation in the overlap zones.

With topologically spherical grids in the wave-zone, it is possible to resolve the gravitational waves with high accuracy, while at the same time employing Cartesian adaptive mesh refinement grids around the black holes to provide a well established discretized representation of the strong field region.


## Multiblocks

In order to handle multiple regions of different symmetry within the same simulation, multipatch (sometimes also called multiblock) schemes have been developed for a wide range of physics and engineering applications.

![[Pasted image 20210121110809.png]]
- Each grid patch is locally Cartesian
- Need Jacobian transformations to transform between local and global frame. 
- Can keep original Cartesian code; only need to replace derivative operators!

## Implementation

Spherical grids have been widely used for many astrophysical problems

- Binary Black Hole
	- [[Pollney2011]] High accuracy binary black hole simulations with an extended wave zone
- Binary Neutron Star
	- [[Reisswig2013]] Three-Dimensional General-Relativistic Hydrodynamic Simulations of Binary Neutron Star Coalescence and Stellar Collapse with Multipatch Grids

## Parameter

- Setup of the 7-patch system
	```python
	Coordinates::coordinate_system   = "Thornburg04"
	Coordinates::h_cartesian         =                # Inner cube resolution
	Coordinates::h_radial            =         	      # Radial resolution
	Coordinates::n_angular           =                # Number of grid cells in the angular directions on the outer grids
	Coordinates::sphere_inner_radius =                # Inner radius for the spherical grids
	Coordinates::sphere_outer_radius =                # Location of the physical outer boundary
	```
- 8 order
	```python
	Driver::ghost_size                     = 5
	Coordinates::patch_boundary_size       = 5
	Coordinates::additional_overlap_size   = 3
	Coordinates::outer_boundary_size       = 5
	```
- Reflection symmetry at the lower z boundary
	```python
	CoordinatesSymmetry::reflection_z     = yes
	CoordinatesSymmetry::stagger          = no
	Coordinates::symmetry                 = "+z bitant"
	Coordinates::additional_symmetry_size = 1
	```

## Developer

- [[Denis Pollney]]
- [[Christian Reisswig]]
- [[Erik Schnetter]]
- [[Peter Diener]]
- [[Daniela Alic]]
- [[Ian Hinder]]
- [[Sascha Husa]]
- [[Philipp Moesta]]
- Jennifer Seiler 
- [[Barry Wardell]]