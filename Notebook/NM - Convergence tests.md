## NM - Convergence tests

The errors which arise due to the discretisation of the physical problem, e.g. by approximating derivatives by finite differences, depends on the resolution chosen. This gives the possibility to check for errors in a simulation by comparing the data to simulations of the same problem, but different resolution.

It is important to compare the order of the obtained convergence to the expected order of the methods used. This is easy in the case of a known, analytical solution, because then it is easy to check if the error made by discretising the problem converges to the known solution by the expected order.

However, for most problems an analytical solution is not known. In this case it is possible to check for the convergence order to some solution by comparing simulations with three different resolutions. The obtained order of convergence $o$ can be calculated by the following expression, using one of the involved quantities $q$ taken from simulations with low, middle and high resolution, differing in a factor of two:

$$
2^{o}=\frac{q_{\text {low }}-q_{\text {middle }}}{q_{\text {middle }}-q_{\text {high }}}
$$