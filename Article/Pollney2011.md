## High accuracy binary black hole simulations with an extended wave zone

- **Author**: [[Denis Pollney]], [[Christian Reisswig]], [[Erik Schnetter]], Dorband N, [[Peter Diener]].
- **Summary**:
	- A regular Cartesian near zone, with adapted spherical grids covering the wave zone.
		- The efficiencies resulting from the use of adapted coordinates allow us to maintain sufficient grid resolution to an artificial outer boundary location which is causally disconnected from the measurement.
- **Link**: [[NR - Coordinate systems]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2011PhRvD..83d4045P) Pollney D, Reisswig C, Schnetter E, Dorband N, Diener P. High accuracy binary black hole simulations with an extended wave zone. PRD, 2011, 83(4): 44045.
- **Code**: [[Llama Thorn]]

___

## Highlight

- We want to extend our grids to a distance such that the measurements are included in the future domain of dependence of the initial data (causally disconnected outer boundaries), and the waves are reasonably well resolved over this entire domain so that internal reflections are minimised.
- The problem of increasing the grid size can be significantly reduced if, rather than a Cartesian coordinate system, one uses a discretisation which has a radial coordinate.
	- For a Cartesian grid, the number of computational points scales as $r^{3}$, so that requiring a sufficient resolution to 200M already comes at significant expense, and increasing this distance further becomes impractical.
	- For a radial coordinate, the number of points on the discrete grid increases simply as a linear function of $r$.
- The absence of artificial boundaries, as well as dissipative regions in the wave zone, removes an important source of potential error in solving the Einstein equations as an initial boundary value problem. The remaining errors can be categorised in three forms.
	- First, numerical error due to the discretisation. This can be reduced through the use of higher order methods for the operations performed in various parts of the code, and fortunately is also easy to quantify by performing tests at multiple resolutions.
	- The second source of error is a physical error, inherent in the choice of initial data parameters for the binary evolution.
	- The final source of error arises in the measurement of $\psi_{4}$, which is done at a finite radius, and then extrapolated to $r \rightarrow \infty$ by some procedure. We have attempted to minimise this error by placing detectors at large radii.
- Cartesian mesh-refined region covering the near zone in which the bodies orbit, and a set of adapted radial grids which efficiently cover the wave zone.
	- The gravitational wave-zone has spherical topology and therefore, a numerical approximation would be most efficiently represented by employing a spherical grid.
	- For the near-zone, Cartesian coordinates is useful to have homogeneous resolution in each direction in situations where there is no obvious symmetry.
- Black hole evolutions via the "moving puncture" approach.
	- The usual approach is to discretise using Cartesian grids which cover the black holes with an appropriate resolution, without special treatment or boundary conditions for the black hole interiors.



## Coordinate systems

- Cartesian mesh-refined region covering the near zone in which the bodies orbit, and a set of adapted radial grids which efficiently cover the wave zone.
	![[Pasted image 20210121194535.png]]
	- Each patch consists of a uniformly spaced (in local coordinates) grid which can be refined (though in practise we will only use this feature for the interior grid). 
- The outer patches have a local coordinate system $(\rho, \sigma, R)$. 
	- The local angular coordinates $(\rho, \sigma)$ range over $(-\pi / 4,+\pi / 4) \times(-\pi / 4,+\pi / 4)$ and can be related to global angular coordinates $(\mu, \nu, \phi)$ which are given by$$\begin{array}{l}\mu=\arctan (y / z) \\ \nu=\arctan (x / z) \\ \phi=\arctan (y / x) \end{array}$$
		![[Pasted image 20210126202232.png]]
	- The local radial coordinate, $R$, is determined as a function of the global coordinate radius, $r$. We can use this degree of coordinate freedom to increase the physical (global) extent of the wave-zone grids, at the cost of some spatial resolution. In practise, we use a function of the form  $$f(r)=A\left(r-r_{0}\right)+B \sqrt{1+\left(r-r_{0}\right)^{2} / \epsilon}$$ with $$R=f(r)-f(0)$$ in order to transition between two almost constant resolutions (determined by the parameters $A$ and $B$) over a region whose width is determined by $\epsilon$, centred at $r_{0}$.
		![[Pasted image 20210126203035.png]]
- Data on each patch are evaluated at grid-points which are placed at uniformly spaced points of a Cartesian grid. Thus, local derivatives can be calculated via standard finite difference techniques. These are then transformed to a common underlying Cartesian coordinate system by applying an appropriate Jacobian which relates the local to global coordinates.
	- That is, the global (Cartesian) coordinates, $x_{i}$, are related to the local coordinates, $a_{i}$, by $$x_{i}=x_{i}\left(a_{j}\right), \quad i, j=0,1,2$$ and derivatives, $\partial / \partial a_{i}$, of fields are determined using finite differences in the regularly spaced $a_{i}$ coordinates, which are then transformed using $$\begin{aligned} \frac{\partial}{\partial x_{i}} &=\left(\frac{\partial a_{j}}{\partial x_{j}}\right) \frac{\partial}{\partial a_{j}} \\ \frac{\partial^{2}}{\partial x_{i} \partial x_{j}} &=\left(\frac{\partial^{2} a_{k}}{\partial x_{i} \partial x_{j}}\right) \frac{\partial^{2}}{\partial a_{k}^{2}}+\left(\frac{\partial a_{k}}{\partial x_{i}} \frac{\partial a_{l}}{\partial x_{j}}\right) \frac{\partial^{2}}{\partial a_{k} \partial a_{l}} \end{aligned}$$ in order to determine their values in the global frame.
- We store and evaluate tensor components and their evolution equations in the common global frame.
	- The coordinates used on each patch are largely independent of the others.
	- Since the data is represented in the common global basis, analysis tools do not need to know anything about the local grid structures or coordinates.
	- This is complicated in the case of non-tensorial quantities (such as $\tilde{\Gamma}^{i}$) which have quite complicated basis transformation rules involving spatial derivatives.
- Data is communicated between patches by interpolating onto overlapping points.
	![[Pasted image 20210126204830.png]]
	- The use of additional overlap points makes this inter-patch interpolation algorithm somewhat simpler than the one implemented by Thornburg.
	- The number of ghost points in $\mathcal{G}_{p}$ can be reduced using finite difference stencils which become lop-sided towards the boundaries of the patch, and may provide an important optimisation since interpolation between grids can be expensive, particularly if processor communication is involved.
- A number of quantities of physical interest are measured by projecting them onto closed surfaces surrounding the source.
	- In particular, gravitational wave measurements rely on computations on constant coordinate spheres $S^{2}$, parameterized by local spherical-polar coordinates $(\theta, \phi)$ with constant coordinate radius $r$.
	- Interpolation can be used to obtain data at points on the measurement spheres.
	
## Grid setup

- The inner boundary of the radial grids was placed at $r_{t}=35.2M$ relative to the centre of the Cartesian grid. As a general rule, this boundary should be made as small as possible to improve efficiency in terms of memory usage.
- The time step $dt$ of the coarsest Cartesian grid determines the timestep of the radial grids, and thus the wave zone.
	- Updates of the radial grids tend to be expensive, as they are large, so that if $dt$ is too small, computation time may be spent over-resolving (in time) the wave zone.
- The outer boundary for the spherical grids was chosen based on the expected time duration of the measurement and radius of the furthest detector, in order to remove any influence of the artificial outer boundary condition.
	![[Pasted image 20210122113911.png]]
	- In particular, given that the evolution takes a time $T_{m}$ for the entire inspiral, merger and ringdown, and gravitational wave measurements taken at a finite radius $r_{d}$, we place the boundary at $$r_{b}>T_{m}+2 r_{d}$$
- The near-zone grids incorporate 5 levels of mesh refinement, covering regions centred around each of the black holes.
- The wave-zone grids have an inner radial resolution which is commensurate with the coarse Cartesian grid resolution. This resolution is maintained essentially constant to the outermost measurement radius.
- We have carried out evolutions at three resolutions in order to estimate the convergence of our numerical methods.
	![[Pasted image 20210126214204.png]]
	- During the early inspiral, it is difficult to evaluate a convergence order due to high frequency noise which is large relative to the waveform amplitude. However, a measurable signal is clear in the last orbit, merger and ringdown phase.