## GR - Covariant derivative

The covariant derivative of an arbitrary tensor $\mathbf{T}$ is also a tensor and it measures the change of $\mathbf{T}$ with respect to parallel transport. For example, a mixed rank-2 tensor with components $T^{a}_{\;b}$, the covariant derivative is a tensor of rank 3 and its components are

$$
\nabla_{c} T_{\;b}^{a}=\partial_{c} T_{\;b}^{a}+{ }^{(4)} \Gamma_{\;d c}^{a} T_{\; b}^{d}-{ }^{(4)} \Gamma_{\; b c}^{d} T_{\; d}^{a}
$$
where the quantities ${ }^{(4)}\Gamma^{a}_{\;b c}$ are connection coefficients associated with the spacetime metric $g_{a b}$. The connection coefficients measure the change in the basis vectors and 1-forms with respect to parallel transport. In a coordinate basis they are related to partial derivatives of the metric by

$$
{ }^{(4)} \Gamma_{\; b c}^{a}=g^{a d} { }^{(4)} \Gamma_{d b c}=\frac{1}{2} g^{a d}\left(\partial_{c} g_{d b}+\partial_{b} g_{d c}-\partial_{d} g_{b c}\right)
$$
In a local Lorentz frame, the Christoffel symbols vanish. The covariant derivative of a scalar function $f$ is the gradient one-form; in components, $\nabla_{a} f=\partial_{a} f$. The corresponding vector $\nabla^{a} f$ is normal to the hypersurface $f = \text{constant}$.


> Consider now the derivative of a vector with respect to a given coordinate:
This equation shows that the derivative of a vector is more that just the derivative of its components. One must also take into account the change in the basis vectors.
> 
>The connection coefficients are not tensor. This is found, e.g., from the fact that they vanish in a local Lorentz frame at which $g_{a b} = \eta_{a b}$ where $\eta_{a b}$ denotes the flat, Minkowski metric.


$$
\nabla_{\mu} V^{\mu}=\frac{1}{\sqrt{|g|}} \partial_{\mu}\left(\sqrt{|g|} V^{\mu}\right)
$$
$$
\nabla_{\mu} V^{\mu}=\partial_{\mu} V^{\mu}+\Gamma_{\mu \lambda}^{\mu} V^{\lambda}
$$
$$
\Gamma_{\mu \lambda}^{\mu}=\frac{1}{\sqrt{|g|}} \partial_{\mu} \sqrt{|g|}
$$