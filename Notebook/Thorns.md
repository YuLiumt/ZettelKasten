## Thorns

A thorn is the basic working module within [[Einstein Toolkit]]. All user supplied code goes into thorns, which are, by and large, independent of each other.

## Modules

- Grid
	- [[Carpet Thorn]]
		- Adaptive mesh refinement
	- [[MoL Thorn]]
		- Runge-Kutta time integration
- Initial Data
	- [[TwoPunctures Thorn]]
- GRMHD
	- [[McLachlan Thorn]]
		- BSSN
		- CCZ4
	- [[CTGamma Thorn]]
		- Z4c
	- [[GRHydro Thorn]]
		- piecewise polytropic equations of state
		- finite temperature tabulated equations of state
	- [[IllinoisGRMHD Thorn]]
		- magnetohydrodynamical instabilities
		- force-free electrodynamics
	- [[WhiskyTHC Thorn]]
		- large eddy simulations method for turbulent viscosity
		- piecewise polytropic equations of state
		- finite temperature tabulated equations of state
		- neutrino radiation via a leakage scheme
	- [[Spritz Thorn]]
- Analysis
	- GW signal
		- [[WeylScal4 Thorn]]
		- [[Multipole Thorn]]
	- Black Hole
		- [[AHFinderDirect Thorn]]
- CactusUtils
	- [[SystemStatistics Thorn]]