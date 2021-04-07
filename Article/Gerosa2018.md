## Black-hole kicks from numerical-relativity surrogate models

- **Author**: Gerosa D, Hébert F, [[Leo C. Stein]].
- **Summary**:
	- Uses a numerical relativity surrogate model to obtain the gravitational waveform given a set of binary parameters, then from this waveform we directly integrate the gravitational-wave linear momentum flux.
	- In contrast with the available fitting formulae, our procedure provides not only the final kick speed $v_{k}$, but also the entire velocity accumulation profile $\mathbf{v}(t)$.
	- Our extraction procedure is made publicly available as a module for the Python programming language named surrkick.
- **Link**: [[BBH - Final black hole]], [[surrkick]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2018PhRvD..97j4049G) Gerosa D, Hébert F, Stein L C. Black-hole kicks from numerical-relativity surrogate models. PRD, 2018, 97(10): 104049.

___

## Highlight

- Binary black holes radiate linear momentum in gravitational waves as they merge. Recoils imparted to the black-hole remnant can reach thousands of $km/s$, thus ejecting black holes from their host galaxies.
	- The key property to generate a GW recoil (or "kick") is asymmetry. It is straightforward to show that symmetry prevents linear momentum dissipation during inspiral and merger of equal-mass, nonspinning BHs. Conversely, a generic BH binary radiates GWs anisotropically: linear momentum is preferentially emitted in some direction, and the binary consequently recoils.
		- Non-spinning BH binaries do not receive any recoil for both $q = 1$ (because of symmetry) and $q = 0$ (which corresponds to the test-particle limit). Recoils are present in between these two limits.
	- Most of the linear momentum is emitted during the last few orbits and merger, which corresponds to the highly dynamical, fully non-linear regime that can only be captured with NR simulations.
- As the system recoils, a Doppler shift of the emitted GWs can provide a possible direct observational signature of BH kicks within the reach of future space- and ground-based GW observatories.
- Linear momentum dissipation, however, is encoded in both differences between the dominant $l=2, m=\pm 2$ modes and higher harmonics $(l>2)$. This approach, therefore, requires an inspiral-merger-ringdown approximant able to model both higher harmonics (crucial to linear momentum flux) and misaligned spins (which are known to generate the largest kicks).
- In this paper we use the NR waveform surrogate model NRSur7dq2 to generate our waveforms. 
	- NRSur7dq2 is the very first model able to cover the 7-dimensional parameter space describing generic precessing systems. NRSur7dq2 is trained on 886 NR waveforms generated with the Spectral Einstein Code (SpEC).
	- Waveforms generated with NRSur7dq2 span the time range $-4500 M \leq t \leq 100 M$, where $t=0$ is defined as the time that maximizes the total waveform amplitude $\mathcal{A}^{2}(t)=\sum_{l, m}\left|h^{l m}(t)\right|^{2}$. The initial time $t=-4500 M$ corresponds to about 20 orbits before merger and the final value $t=100 M$ allow for a full dissipation of the signal.
	- More specifically, NRSur7dq2 provides the distance-independent dimensionless strain, extrapolated to $\mathcal{I}^{+}$, i.e. $\lim _{r \rightarrow \infty} r h / M$ where $r$ is the distance from the binary's center of mass and $M$ is the total mass of the binary at the beginning of the evolution.
- The kick profile $\mathbf{v}(t)$ for a series of BH mergers with $q=0.5, \ldots, 1$.
	![[Pasted image 20210330135842.png]]
	- Interestingly, the projection of the recoil profile along the final kick direction $\mathbf{v}(t) \cdot \hat{\mathbf{v}}_{\mathbf{k}}$ is not monotonic after merger: the binary suddenly decelerates at about $t \sim 15 M$, after which the imparted velocity settles down to the asymptotic value $v_{k}$. This effect has been dubbed antikick, and turns out to be a rather generic feature of BH mergers.
- The impact of aligned spins on the radiated energy and linear momentum profile
	![[Pasted image 20210330140725.png]]
	![[Pasted image 20210330140813.png]]
- We now estimate the accuracy of our extraction procedure by directly comparing our results to numerical relativity simulations from the SpEC code.
	![[Pasted image 20210330145412.png]]
	- This is not the most ideal comparison: each of these numerical simulation occupies a special point in the binary parameter space of the surrogate model.
		- The surrogate waveforms do not reproduce the NR waveforms exactly.
		- NRSur7dq2 was designed to maximize the overlap between the interpolated and the NR strain $h$, not to accurately model BH kicks.
	


## Radiated energy and momenta

The energy flux emitted in GWs is provided in terms of the first time derivative of the complex strain $\dot{h}$ and reads:

$$
\frac{d E}{d t}=\lim _{r \rightarrow \infty} \frac{r^{2}}{16 \pi} \sum_{l, m}\left|\dot{h}^{l, m}\right|^{2} \tag{1}
$$

When integrating to obtain $E(t)$ we set the integration constant $E_{0}$ to account for the binding energy dissipated in GWs at times $t<-4500 M$, before the start of our waveforms, thus enforcing $\lim _{t \rightarrow-\infty} E(t)=0$. A straightforward Newtonian (0PN) calculation yields

$$
\frac{E_{0}}{M}=\left(\frac{5}{1024} \frac{q^{3}}{(1+q)^{6}} \dot{E}_{0}\right)^{1 / 5} \tag{2}
$$

where $\dot{E}_{0}$ is estimated from Eq. (1) by averaging over the first $100 M$ in time.

One can then define the time-dependent (Bondi) mass of the binary,

$$
M(t)=M-E(t)+E_{0} \tag{3}
$$

The emitted linear momentum is also fully specified by $\dot{h}$ and crucially includes mixing between modes with different $l$ and $m$:

$$
\begin{aligned}
\frac{d P_{x}}{d t}=& \lim _{r \rightarrow \infty} \frac{r^{2}}{8 \pi} \operatorname{Re}\left[\sum_{l, m} \dot{h}^{l, m}\left(a_{l, m} \dot{\bar{h}}^{l, m+1}\right.\right.\\
&\left.\left.+b_{l,-m} \dot{\bar{h}}^{l-1, m+1}-b_{l+1, m+1} \dot{\bar{h}}^{l+1, m+1}\right)\right]
\end{aligned} \tag{4}
$$

$$
\begin{aligned}
\frac{d P_{y}}{d t}=& \lim _{r \rightarrow \infty} \frac{r^{2}}{8 \pi} \operatorname{Im}\left[\sum_{l, m} \dot{h}^{l, m}\left(a_{l, m} \dot{\bar{h}}^{l, m+1}\right.\right.\\
&\left.\left.+b_{l,-m} \dot{\bar{h}}^{l-1, m+1}-b_{l+1, m+1} \dot{\bar{h}}^{l+1, m+1}\right)\right]
\end{aligned} \tag{5}
$$

$$
\begin{aligned}
\frac{d P_{z}}{d t}=& \lim _{r \rightarrow \infty} \frac{r^{2}}{16 \pi} \sum_{l, m} \dot{h}^{l, m}\left(c_{l, m} \dot{\bar{h}}^{l, m}\right.\\
&\left.+d_{l, m} \dot{\bar{h}}^{l-1, m}+d_{l+1, m} \dot{\bar{h}}^{l+1, m}\right)
\end{aligned} \tag{6}
$$

where the upper bar denotes complex conjugation and

$$
\begin{array}{l}
a_{l, m}=\frac{\sqrt{(l-m)(l+m+1)}}{l(l+1)} \\
b_{l, m}=\frac{1}{2 l} \sqrt{\frac{(l-2)(l+2)(l+m)(l+m-1)}{(2 l-1)(2 l+1)}} \\
c_{l, m}=\frac{2 m}{l(l+1)} \\
d_{l, m}=\frac{1}{l} \sqrt{\frac{(l-2)(l+2)(l-m)(l+m)}{(2 l-1)(2 l+1)}}
\end{array} \tag{7}
$$

The integration constant for the $d \mathbf{P} / d t$ integration is chosen so that the average of $\mathbf{P}$ over the first $1000 M$ in time, where linear momentum emission is expected to be negligible, is zero. By conservation of linear momentum, the time profile of the kick imparted to the system is

$$
\mathbf{v}(t)=-\frac{P_{x}(t) \hat{\mathbf{x}}+P_{y}(t) \hat{\mathbf{y}}+P_{z}(t) \hat{\mathbf{z}}}{M(t)} \tag{8}
$$

and the final velocity of the post-merger remnant BH is

$$
\mathbf{v}_{\mathbf{k}}=\lim _{t \rightarrow \infty} \mathbf{v}(t) \tag{9}
$$

One can further integrate $\mathbf{v}(t)$ in time to obtain the trajectory $\mathbf{x}(t)=\int \mathbf{v}(t) d t$. Although the binary trajectory is a coordinate-dependent notion, the time integral of the linear momentum dissipated in GWs can be interpreted as the motion of the spacetime's center of mass seen by an observer at $\mathcal{I}^{+}$.

The angular momentum carried by GWs involves both $h$ and $\dot{h}$

$$
\begin{aligned}
\frac{d J_{x}}{d t}=& \lim _{r \rightarrow \infty} \frac{r^{2}}{32 \pi} \operatorname{Im}\left[\sum_{l, m} h^{l, m}\left(f_{l, m} \dot{\bar{h}}^{l, m+1}\right.\right.\\
&\left.\left.+f_{l,-m} \dot{\bar{h}}^{l, m-1}\right)\right]
\end{aligned} \tag{10}
$$

$$
\begin{aligned}
\frac{d J_{y}}{d t}=&-\lim _{r \rightarrow \infty} \frac{r^{2}}{32 \pi} \operatorname{Re}\left[\sum_{l, m} h^{l, m}\left(f_{l, m} \dot{\bar{h}}^{l, m+1}\right.\right.\\
&\left.\left.-f_{l,-m} \dot{\bar{h}}^{l, m-1}\right)\right]
\end{aligned} \tag{11}
$$

$$
\frac{d J_{z}}{d t}=\lim _{r \rightarrow \infty} \frac{r^{2}}{16 \pi} \operatorname{Im}\left[\sum_{l, m} m h^{l, m} \dot{\bar{h}}^{l, m}\right] \tag{12}
$$

where

$$
f_{l, m}=\sqrt{l(l+1)-m(m+1)} \tag{13}
$$

When integrating $d \mathbf{J} / d t$, we do not adjust the integration constant to account for the angular momentum radiated before the beginning of our waveforms.

We perform all differentiations and integrations required to extract these radiated quantities analytically on the spline interpolants provided by NRSur7dq2, over the range $-4500 M \leq t \leq 100 M$. The $t \rightarrow \infty$ limits are approximated with values at $t=100 M$.