## Thorns

The thorns are the basic modules of [[Cactus]]. They are largely independent of each other and communicate via calls to the [[Flesh]] API. Thorns are collected into logical groupings called arrangements.

## Modules

- Grid
	- [[Carpet Thorn]]
		- Adaptive mesh refinement
	- [[MoL Thorn]]
		- Runge-Kutta time integration
- Initial Data
	- TOVSolver Thorn
	- [[TwoPunctures Thorn]]
	- Meudon
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
- Equation of State
	- [[EOS_Omni Thorn]]
- Analysis
	- GW signal
		- [[WeylScal4 Thorn]]
		- [[Multipole Thorn]]
	- Black Hole
		- [[AHFinderDirect Thorn]]
		- PunctureTracker Thorn
	- Matter
		- Outflow Thorn
- CactusUtils
	- [[SystemStatistics Thorn]]