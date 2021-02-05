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
- The metric solver explicitly computes the metric components in the global frame and is thus generally incompatible with the hydrodynamic quantities defined in the local frame.
	- We therefore introduce the additional step of transforming the metric components to the local basis before each hydrodynamic RHS step.
	- Since the various analysis tools explicitly assume a global coordinate frame for the primitive variables, we introduce a separate set of global primitive variables. Effectively, this only requires extra memory for the primitive 3-velocity $\left\{\tilde{v}^{i}\right\}$, since the primitive density $\rho$ and $\tau$ are scalars. Once the primitive quantities are known in the global frame, the stress-energy tensor can be directly computed in the global frame.
		![[Pasted image 20210130113044.png]]
	- 
	
## Multipatches

- The central Cartesian patch is surrounded by six spherical inflated cube patches.
	![[Pasted image 20210121110809.png]]
	- The nominal grids of the spherical patches have inner radius $R_{\mathrm{S}}$, outer radius $R_{\mathrm{B}}$, radial spacing $\Delta R_{1}$, which is allowed to stretch to $\Delta R_{2}$ within some finite region, and angular resolution $(\Delta \rho, \Delta \sigma)$ per angular direction $(\rho, \sigma) .$ Note that the angles $(\rho, \sigma)$ used to define the local coordinates of each inflated-cube patch do not coincide with standard spherical-polar coordinates.
	- The central patch contains a hierarchy of refined regions, allowing to place resolution where necessary.
	- Each grid patch defines local uniform coordinates $(u, v, w)$ related to the global Cartesian $(x, y, z)$ coordinate space by a diffeomorphic relation.