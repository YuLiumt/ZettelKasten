## The Einstein Toolkit: A Community Computational Infrastructure for Relativistic Astrophysics

- **Author**: [[Frank Löffler]], Faber J, Bentivegna E, Bode T, Diener P, [[Roland Haas]], Hinder I, Mundim B C, Ott C D, [[Erik Schnetter]], Allen G, Campanelli M, Laguna P.
- **Summary**:
	- Einstein Toolkit, a community-driven, freely accessible computational infrastructure intended for use in numerical relativity, relativistic astrophysics, and other applications.
	- The Einstein Toolkit is currently based on the Cactus Framework for high-performance computing and the Carpet adaptive mesh refinement driver.
- **Link**: [[Einstein Toolkit]], [[Cactus]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2012CQGra..29k5001L) Löffler F, Faber J, Bentivegna E, Bode T, Diener P, Haas R, Hinder I, Mundim B C, Ott C D, Schnetter E, Allen G, Campanelli M, Laguna P. The Einstein Toolkit: a community computational infrastructure for relativistic astrophysics. Classical and Quantum Gravity, 2012, 29(11): 115001.

___

## Highlight

- The mechanisms for the development and support of the Einstein Toolkit are designed to be open, transparent and community-driven.
	- Almost all discussions about the toolkit take place on an open mail list.
	- The regular weekly meetings for the Einstein Toolkit are open and the community is invited to participate.
	- Every substantial change or addition to the toolkit must be reviewed by another Einstein Toolkit maintainer, and is generally open for discussion on the users mailing list.

## Numerical Convergence

A numerical quantity $\Psi$ is said to converge with convergence order $Q$ if for a set of numerical step sizes $h_{1}, h_{2}, h_{3}$ the difference between successive resolutions scales as

$$
\frac{\Psi_{h_{1}}-\Psi_{h_{2}}}{\Psi_{h_{2}}-\Psi_{h_{3}}}=\frac{h_{1}^{Q}-h_{2}^{Q}}{h_{2}^{Q}-h_{3}^{Q}}
$$

![[Pasted image 20210401151855.png]]
- In the bottom plot the black (solid) curve shows the absolute value of the difference between the real part of the medium and low resolution waveforms while the blue (dashed) curve shows the absolute value of the difference between the high and medium resolution waveforms in a log-plot.
- The red (dotted) curve is the same as the blue (dashed) curve, except it is scaled for fourth-order convergence, demonstrating we indeed achieve this. With the resolutions used here this factor is $\left(0.016^{4}-0.024^{4}\right) /\left(0.012^{4}-0.016^{4}\right) \approx 5.94$.