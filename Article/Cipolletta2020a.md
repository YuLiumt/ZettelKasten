## Spritz: a new fully general-relativistic magnetohydrodynamic code

- **Author**: Cipolletta F, Kalinani J V, [[Bruno Giacomazzo]], [[Riccardo Ciolfi]]. 
- **Summary**:
	- Here, we present our new code named Spritz that solves the GRMHD equations in 3D Cartesian coordinates and on a dynamical spacetime.
		- Spritz code can use modern tabulated equations of state.
		- Spritz also implements a staggered version of the vector potential formulation instead of the magnetic field.
- **Link**: [[Numerical Relativity]], [[General relativistic magnetohydrodynamic]], [[Numerical Methods]], [[Einstein Toolkit]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2020CQGra..37m5010C) Cipolletta F, Kalinani J V, Giacomazzo B, Ciolfi R. Spritz: a new fully general-relativistic magnetohydrodynamic code. Classical and Quantum Gravity, 2020, 37(13): 135010.
- **Code**: [[Spritz Thorn]]

___

## Highlight

- Check the correctness of the approximate Riemann solvers
	![[Pasted image 20201225110250.png]]
	- All tests show an excellent agreement between the numerical results and the exact solutions.
- Check the capability of the code to follow a shock front on the equatorial plane
	![[Pasted image 20201225110955.png]]
	- Considers a uniformly magnetized domain consisting of a dense, over–pressured cylinder in the central region expanding in a surrounding ambient medium.
- Testing the evolution of the magnetic field in the presence of rotation.
	![[Pasted image 20201225111311.png]]
	- A magnetized circular field loop is propagated within the surrounding non–magnetized ambient medium with a constant velocity in a two–dimensional periodic grid.
- Check the robustness of our code to handle 3D spherical shock waves
	![[Pasted image 20201225112012.png]]
- The evolution of non-rotating NSs
	![[Pasted image 20201225112107.png]]
	
## Basic Equations

### 3+1 spacetime formulation

The form of the line element is:

$$
d s^{2}=g_{\mu \nu} d x^{\mu} d x^{\nu}=-\left(\alpha^{2}-\beta^{i} \beta_{i}\right) d t^{2}+2 \beta_{i} d x^{i} d t+\gamma_{i j} d x^{i} d x^{j} \tag{1}
$$
where the usual Einstein notation is adopted. Here $g_{i j}$ is the metric tensor, $\gamma_{i j}$ its purely spatial part, and $\alpha$ and $\beta^{i}$ are respectively the lapse and the shift vector. Our coordinate setting considers $x^{0} \equiv t$.

Spritz makes use of the Valencia formulation. Here, the natural observer is called the Eulerian observer and its four–velocity $\boldsymbol{n}$ is normal to the 3–dimensional hypersurface of constant $t$ with the following components:

$$
\begin{aligned}
n^{\mu} &=\frac{1}{\alpha}\left(1,-\beta^{i}\right) \\
n_{\mu} &=(-\alpha, 0,0,0)
\end{aligned} \tag{2}
$$
When considering matter, the spatial components of the fluid velocity measured by the Eulerian observer read

$$
v^{i}=\frac{h_{\mu}^{i} u^{\mu}}{-\boldsymbol{u} \cdot \boldsymbol{n}}=\frac{u^{i}}{\alpha u^{t}}+\frac{\beta^{i}}{\alpha}=\frac{u^{i}}{W}+\frac{\beta^{i}}{\alpha} \tag{3}
$$
where $\boldsymbol{u}$ is the fluid four–velocity, $h_{\mu \nu}=g_{\mu \nu}+n_{\mu} n_{\nu}$ is the projector onto the aforementioned hypersurface at constant $t$, $W=1 / \sqrt{1-v^{2}}$ is the Lorentz factor, and $v^{2} \equiv \gamma_{i j} v^{i} v^{j}$ is the square norm of $\boldsymbol{v}$.


### Electromagnetic field

The general relativistic formulation describes the electromagnetic field via the Faraday tensor and its dual, given respectively by

$$
\begin{aligned}
F^{\mu \nu} &=U^{\mu} E^{\nu}-U^{\nu} E^{\mu}-\eta^{\mu \nu \lambda \delta} U_{\lambda} B_{\delta} \\
{ }^{*} F^{\mu \nu} &=\frac{1}{2} \eta^{\mu \nu \lambda \delta} F_{\lambda \delta}=U^{\mu} B^{\nu}-U^{\nu} B^{\mu}-\eta^{\mu \nu \lambda \delta} U_{\lambda} E_{\delta}
\end{aligned} \tag{4}
$$
being $E^{\mu}$ the electric field, $B^{\mu}$ the magnetic field, $U^{\mu}$ a generic observer's four-velocity, and $\eta^{\mu \nu \lambda \delta}$ the volume element.

The equations governing the electromagnetic field and its evolution are the well known Maxwell's equations

$$
\begin{array}{l}
\nabla_{\nu}^{*} F^{\mu \nu}=0 \\
\nabla_{\nu} F^{\mu \nu}=4 \pi \mathcal{J}^{\mu}
\end{array} \tag{5}
$$
where $\mathcal{J}$ is the four–vector current density, which can be expressed through the Ohm's law as

$$
\mathcal{J}^{\mu}=q u^{\mu}+\sigma F^{\mu \nu} u_{\nu} \tag{6}
$$
with $q$ the proper charge density and $\sigma$ the electric conductivity. In the ideal MHD regime (i.e., when $\sigma \rightarrow \infty$ and $F^{\mu \nu} u_{\nu} \rightarrow 0$) Equation (4) can be expressed as

$$
\begin{aligned}
F^{\mu \nu}&=\eta^{\alpha \beta \mu \nu} b_{\alpha} u_{\beta},  \\
\quad{ }^{*}F^{\mu \nu}&=b^{\mu} u^{\nu}-b^{\nu} u^{\mu}=\frac{u^{\mu} B^{\nu}-u^{\nu} B^{\mu}}{W}
\end{aligned} \tag{7}
$$
where $\boldsymbol{b}$ is the magnetic field according to the comoving observer, which can be written component–wise as follows:

$$
\begin{aligned}
b^{0}&=\frac{W B^{i} v_{i}}{\alpha}, \\
b^{i}&=\frac{B^{i}+\alpha b^{0} u^{i}}{W}, \\
b^{2} &\equiv b^{\mu} b_{\mu}=\frac{B^{2}+\alpha^{2}\left(b^{0}\right)^{2}}{W^{2}}
\end{aligned} \tag{8}
$$
Here, $B^{2} \equiv B^{i} B_{i}$, where $\boldsymbol{B}$ is now the magnetic field measured by the Eulerian observer. With Equation (7), the Maxwell’s equations considering the dual of Faraday tensor can be written as

$$
\nabla_{\nu}^{*} F^{\mu \nu}=\frac{1}{\sqrt{-g}} \partial_{\nu}\left(\sqrt{-g}\left(b^{\mu} u^{\nu}-b^{\nu} u^{\mu}\right)\right)=0 \tag{9}
$$
Splitted in its different components, Equation (9) provides the equations governing the magnetic field constraints and evolution, namely the divergence–free condition

$$
\partial_{i} \tilde{B}^{i}=0 \tag{10}
$$
where $\tilde{B}^{i} \equiv \sqrt{\gamma} B^{i}$, and the magnetic field induction equations

$$
\partial_{t} \tilde{B}^{i}=\partial_{j}\left(\tilde{v}^{i} \tilde{B}^{j}-\tilde{v}^{j} \tilde{B}^{i}\right) \tag{11}
$$
where $\tilde{v}^{i} \equiv \alpha v^{i}-\beta^{i}$.

### Conservative approach

The stress–energy tensor, considering a perfect fluid and the contribution of the magnetic field, can be written as

$$
T^{\mu \nu}=\left(\rho h+b^{2}\right) u^{\mu} u^{\nu}+\left(p_{\mathrm{gas}}+p_{\mathrm{mag}}\right) g^{\mu \nu}-b^{\mu} b^{\nu} \tag{12}
$$
being $\rho$ the rest–mass density, $p_{gas}$ the gas pressure, $p_{mag} \equiv \frac{b^{2}}{2}$ the magnetic pressure, $h=1+\varepsilon+\frac{p_{gas}}{\rho}$ the relativistic specific enthalpy, and $\varepsilon$ the specific internal energy.

The energy-momentum conservation

$$
\nabla_{\nu} T^{\mu \nu}=0 \tag{13}
$$
the conservation of baryon number

$$
\nabla_{\nu}\left(\rho u^{\nu}\right)=0 \tag{14}
$$
Maxwell's equations for the magnetic field (11), and an equation of state give together the complete set of equations describing the evolution of the primitive variables, i.e., $\boldsymbol{U}=\left[\rho, v_{j}, \varepsilon, B^{k}\right]$. As usual, these equations can be written in the following conservative form:

$$
\frac{1}{\sqrt{-g}}\left[\partial_{t}\left(\sqrt{\gamma} \boldsymbol{F}^{0}\right)+\partial_{i}\left(\sqrt{-g} \boldsymbol{F}^{i}\right)\right]=\boldsymbol{S} \tag{15}
$$
being $\boldsymbol{F}^{0} \equiv\left[D, S_{j}, \tau, B^{k}\right]$ the vector of conserved variables, defined in terms of the primitive ones as

$$
\begin{aligned}
D & \equiv \rho W \\
S_{j} & \equiv\left(\rho h+b^{2}\right) W^{2} v_{j}-\alpha b^{0} b_{j} \\
\tau & \equiv\left(\rho h+b^{2}\right) W^{2}-\left(p_{gas}+p_{mag}\right)-\alpha^{2}\left(b^{0}\right)^{2}-D \\
B^{k} & \equiv B^{k}
\end{aligned} \tag{16}
$$
$\boldsymbol{F}^{i}$ the vector of fluxes defined as

$$
\boldsymbol{F}^{i} \equiv\left[\begin{array}{c}
D \tilde{v}^{i} / \alpha \\
S_{j} \tilde{v}^{i} / \alpha+\left(p_{gas}+p_{mag}\right) \delta_{j}^{i}-b_{j} B^{i} / W \\
\tau \tilde{v}^{i} / \alpha+\left(p_{gas}+p_{mag}\right) v^{i}-\alpha b^{0} B^{i} / W \\
B^{k} \tilde{v}^{i} / \alpha-B^{i} \tilde{v}^{k} / \alpha
\end{array}\right] \tag{17}
$$
and $\boldsymbol{S}$ the vector of sources that reads

$$
\boldsymbol{S} \equiv\left[\begin{array}{c}
0 \\
T^{\mu \nu}\left(\partial_{\mu} g_{\nu j}-\Gamma_{~\nu \mu}^{\delta} g_{\delta j}\right) \\
\alpha \left(T^{\mu 0} \partial_{\mu} \ln \alpha-T^{\mu \nu} \Gamma_{~\nu \mu}^{0}\right) \\
0^{k}
\end{array}\right] \tag{18}
$$

### Electromagnetic gauge conditions

In order to accurately describe the magnetic field and its evolution, it can be convenient to formulate the problem in terms of the vector potential. Considering $\nabla$ as a purely spatial operator, one may write

$$
\boldsymbol{B}=\nabla \times \boldsymbol{A} \tag{19}
$$
so that 

$$
\nabla \cdot \boldsymbol{B}=\nabla \cdot(\nabla \times \boldsymbol{A})=0 \tag{20}
$$
and thus evolving the vector potential $\boldsymbol{A}$ will automatically satisfy Equation (10).

We then introduce the four–vector potential

$$
\mathcal{A}_{\nu}=n_{\nu} \Phi+A_{\nu} \tag{21}
$$
being $A_{\nu}$ the purely spatial vector potential and $\Phi$ the scalar potential. With this, Equation (10) and Equation (11) become respectively

$$
B^{i}=\epsilon^{i j k} \partial_{j} A_{k} \tag{22}
$$
and

$$
\partial_{t} A_{i}=-E_{i}-\partial_{i}\left(\alpha \Phi-\beta^{j} A_{j}\right) \tag{23}
$$
where $\epsilon^{i j k}=n_{\nu} \epsilon^{\nu i j k}$ is the three–dimensional spatial Levi–Civita tensor.

However, the choice of the four-vector potential $\mathcal{A}^{\nu}$ is not unique and one has to choose a specific gauge.

The first GRMHD simulations that employed the vector potential as an evolution variable were performed using the algebraic gauge where the scalar potential satisfy the following equation:

$$
\Phi=\frac{1}{\alpha}\left(\beta^{j} A_{j}\right) \tag{24}
$$
In this way Equation (23) is strongly simplified, being reduced to
$$
\partial_{t} A_{i}=-E_{i} \tag{25}
$$
and therefore it does not require to evolve the scalar potential $\Phi$.

More recently, GRMHD simulations started to use the Lorenz gauge, which consists of imposing the constraint $\nabla_{\nu} \mathcal{A}^{\nu}=0$. This gauge requires now to solve also the evolution equation for the scalar potential:

$$
\partial_{t}(\sqrt{\gamma} \Phi)+\partial_{i}\left(\alpha \sqrt{\gamma} A^{i}-\sqrt{\gamma} \beta^{i} \Phi\right)=0 \tag{26}
$$

The Lorenz gauge has been shown to perform better in those simulations that implement adaptive mesh refinement. The algebraic gauge may indeed cause interpolation errors at the boundaries between refinement levels and thus produce spurious magnetic fields. An even more robust gauge choice is generalized Lorenz gauge:

$$
\nabla_{\nu} \mathcal{A}^{\nu}=\xi n_{\nu} \mathcal{A}^{\nu} \tag{27}
$$
where $\xi$ is a parameter that is typically set to be equal to $1.5 / \Delta t_{\max }$, being $\Delta t_{\max }$ the timestep of the coarsest refinement level. When employing this gauge choice the evolution equation for the scalar potential becomes

$$
\partial_{t}(\sqrt{\gamma} \Phi)+\partial_{i}\left(\alpha \sqrt{\gamma} A^{i}-\sqrt{\gamma} \beta^{i} \Phi\right)=-\xi \alpha \sqrt{\gamma} \Phi \tag{28}
$$

In Spritz we adopt the generalized Lorenz gauge.

## Numerical Implementation

### Riemann Solvers

The Spritz code adopts High Resolution Shock Capturing (HRSC) methods to solve Equation (15). These methods are based on the choice of reconstruction algorithms, to compute the values of primitive variables at the interface between numerical cells, and of approximate Riemann solvers, to finally compute the fluxes.

Our default Riemann solver is the Harten–Lax–van–Leer–Einfeldt (HLLE), where the numerical fluxes at cell interfaces are computed as follows:

$$
\boldsymbol{F}^{i}=\frac{c_{\min } \boldsymbol{F}_{\mathrm{r}}^{i}+c_{\max } \boldsymbol{F}_{l}^{i}-c_{\max } c_{\min }\left(\boldsymbol{F}_{\mathrm{r}}^{0}-\boldsymbol{F}_{l}^{0}\right)}{c_{\max }+c_{\min }} \tag{29}
$$
where a subscript $r(l)$ means that the function is computed at the right (left) side of the cell interface and $c_{\max } \equiv \max \left(0, c_{+, 1}, c_{+, \mathrm{r}}\right)$, $c_{\min } \equiv-\min \left(0, c_{-, l}, c_{-, r}\right)$, where $c_{\pm, r}\left(c_{\pm, l}\right)$ are the right-going ($+$) and left-going ($-$) maximum wave speeds computed from the primitive variables $\boldsymbol{U}$ at the right (left) side.

We decided also to implement the Lax–Friedrichs (LxF) scheme, that is

$$
\boldsymbol{F}^{i}=\frac{\boldsymbol{F}_{\mathrm{r}}^{i}+\boldsymbol{F}_{l}^{i}-c_{\mathrm{wave}}\left(\boldsymbol{F}_{\mathrm{r}}^{0}-\boldsymbol{F}_{l}^{0}\right)}{2} \tag{30}
$$
where $c_{\text {wave }}=\max \left(c_{\max }, c_{\min }\right)$. This scheme is a very dissipative one and it can be useful in cases where strong jumps in pressure must be considered.

In order to compute the values of $\boldsymbol{F}^{0}$ at right and left sides of cell's interfaces from the primitive variables, we adopt the third–order Piece-wise Parabolic Method (PPM ). In addition, for those cases that require more dissipative methods, for example in presence of strong shocks, we also implemented the second–order total variation diminishing (TVD) minmod method.

### Electromagnetic Field Evolution

We will also use the following definition for simplicity:

$$
\Psi_{\mathrm{mhd}} \equiv \sqrt{\gamma} \Phi \tag{31}
$$

Usually, the vector potential $\boldsymbol{A}$ are staggered. The electric and magnetic field components are not evolved variables. The electric field is computed at cell's edges using the flux-CT approach. The magnetic field is instead computed at the cell faces using the vector potential component stored at cell's edges and then linearly interpolated at the center of the cell. The precise storage location on the grid–cells of various quantities is reported in Table 1.

![[Pasted image 20201227214004.png]]
![[Pasted image 20201227214024.png]]

### Boundary Conditions

For each grid–point in the outer boundary we apply the following linear extrapolation formula:

$$
F_{i}^{j}=\left\{\begin{array}{ll}
2 F_{i-1}^{j}-F_{i-2}^{j} & \text { for } i=N^{j}-2, N^{j}-1, N^{j} \\
2 F_{i+1}^{j}-F_{i+2}^{j} & \text { for } i=3,2,1
\end{array}\right. \tag{32}
$$
where $F \in\left\{\boldsymbol{A}, \Psi_{\mathrm{mhd}}\right\}$, $j \in\{1,2,3\}$, $N$ is the number of grid–points in the $j$–direction, and we use 3 points in the ghost zones for each direction.

### Primitive variables recovering

The computation of fluxes at each time during the evolution depends on values of the primitive variables $\boldsymbol{U}$, although we evolve the conserved ones $\boldsymbol{F}^{0}$. As recurrent in many conservative approaches, one of the most delicate point is the inversion of Equation (16), a problem that presents no analytic solution. Thus one has to apply a numerical method (usually a Newton-Raphson scheme).

### Atmosphere

As any GRMHD grid-based code, Spritz cannot handle zero values for the rest-mass density and a minimum value $\rho_{atm}$ needs to be set. If at time $t$ the rest-mass density $\rho$ computed in our conservative-to-primitive routine is such that $\rho<\rho_{atm}$, then its value is set to $\rho_{atm}$, the pressure and specific internal energy are recomputed using a polytropic EOS, and the fluid's three–velocity is set to zero.

### Equation of State

The Spritz code can implement both analytic and tabulated EOS. This is done via the [[EOS_Omni Thorn]] provided by the Einstein Toolkit which supports analytic EOS, such as "ideal fluid" and "piecewise polytropic" ones, and "tabulated" EOS.