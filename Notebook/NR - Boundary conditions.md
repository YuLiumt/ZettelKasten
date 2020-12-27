## NR - Boundary conditions

With the exception in which a compactified domain is used, spatial infinity is not included in the computational domain. Thus, the domain has to be cut at some finite distance from the interesting region and boundary conditions have to be imposed.


The most used boundary conditions are the outgoing radiation boundary conditions by Alcubierre et al.

$$
f=f_{0}+u \frac{r-v t}{r}+\frac{h(t)}{r^{n}}
$$
where $f$ is the quantity in question, $f_{0}$ is the asymptotic value of $f$ and $v$ is the wave speed (the speed of light in our case).

The power of $r^{n}$ is unknown and has to be assumed. Empirically, a value of $n = 3$ has shown to have a good effect for this boundary condition, but this might also depend on the quantity in question.

Another type of frequently applied boundary conditions are the so called Robin boundary conditions. This is a physically motivated boundary condition. It assumes a certain fall-off of the variables at large radii:

$$
f=f_{0}+\frac{k}{r^{n}}
$$
with a constant $k$. It is related to the radiation boundary condition, but without information about the time evolution.