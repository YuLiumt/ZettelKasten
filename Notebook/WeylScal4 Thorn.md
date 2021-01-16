# WeylScal4 Thorn

One way to extract gravitational waves is through the calculation of one of the Weyl scalars

$$
\psi_{4} \equiv-C_{\alpha \beta \gamma \delta} n^{\alpha} \bar{m}^{\beta} n^{\gamma} \bar{m}^{\delta}
$$
where $\{l, n, m, \bar{m}\}$ is a null tetrad and $C_{\alpha \beta \gamma \delta}$ is the Weyl tensor.

In a 3+1 evolution this is usually calculated by defining an orthonormal 3-basis, $(\hat{r}, \hat{\theta}, \hat{\phi})$.

Using the normal to the spatial slice, $\hat{t}$, it is possible to construct a null tetrad

$$
l=\frac{1}{\sqrt{2}}(\hat{t}-\hat{r}), \quad n=\frac{1}{\sqrt{2}}(\hat{t}+\hat{r}), \quad m=\frac{1}{\sqrt{2}}(\hat{\theta}-i \hat{\phi})
$$

Using the decomposition of the Weyl tensor into it's electric and magnetic parts

$$
C_{i j} \equiv E_{i j}-i B_{i j}=R_{i j}-K K_{i j}+K_{i}{ }^{k} K_{k j}-\mathrm{i} \epsilon_{i}{ }^{k l} \nabla_{l} K_{j k}
$$

we can calculate $\psi_{4}$ in terms of all spatial quantities

$$
\psi_{4}=C_{i j} \bar{m}^{i} \bar{m}^{j}
$$