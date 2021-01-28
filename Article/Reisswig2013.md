## Three-Dimensional General-Relativistic Hydrodynamic Simulations of Binary Neutron Star Coalescence and Stellar Collapse with Multipatch Grids

- **Author**: [[Christian Reisswig]], [[Roland Haas]], Ott C D, Abdikamalov E, Mösta P, [[Denis Pollney]], [[Erik Schnetter]].
- **Summary**:
	- A central Cartesian patch is surrounded by six "inflated cube" spherical grid patches.
		- This allows us to significantly enlarge our computational domains while still maintaining high resolution in the gravitational-wave extraction zone, the exterior layers of a star, or the region of mass ejection in merging neutron stars.
		- The outer boundary can be causally disconnected from the interior evolution and the gravitational-wave extraction zone.
		- We are able to extract convergent gravitational-wave modes up to $(\ell, m)=(6,6)$.
- **Link**: [[NR - Coordinate systems]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2013PhRvD..87f4023R) Reisswig C, Haas R, Ott C D, Abdikamalov E, Mösta P, Pollney D, Schnetter E. Three-dimensional general-relativistic hydrodynamic simulations of binary neutron star coalescence and stellar collapse with multipatch grids. PRD, 2013, 87(6): 64023.
- **Code**: [[Llama Thorn]]

___

## Highlight

- The symmetry of the computational problem, however, is essentially spherical, at least at some distance from the central region of the simulation. Thus, Cartesian grids are wasteful with respect to angular resolution when the problem becomes symmetrically spherical.
	- Various hydrodynamic instabilities (e.g. convection and instabilities of the shock) break this symmetry. The global features, however, remain approximately spherical or axisymmetric.
	- The computational effort when using spherical grids scales linearly with the number of radial points N, assuming constant angular resolution.