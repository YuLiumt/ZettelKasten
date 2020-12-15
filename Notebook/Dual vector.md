## Dual vector

Now introduce a set of basis 1-forms $\tilde{\omega}^{a}$ dual to the basis vectors $\mathbf{e}_{a}$. An arbitrary 1-form $\tilde{\mathbf{B}}$ can be expanded in its covariant components according to

$$
\tilde{\mathbf{B}}=B_{a} \tilde{\omega}^{a}.
$$
The scalar product of two 1-forms $\tilde{\mathbf{A}}$ and $\tilde{\mathbf{B}}$ is

$$
\tilde{\mathbf{A}} \cdot \tilde{\mathbf{B}}=\left(A_{a} \tilde{\omega}^{a}\right) \cdot\left(B_{b} \tilde{\omega}^{b}\right)=g^{a b} A_{a} B_{b}.
$$
where $g^{a b}$ is the inverse of $g_{a b}$. A basis of 1-forms dual to the basis $\mathbf{e}_{a}$ always satisfies

$$
\tilde{\omega}^{a} \cdot \mathbf{e}_{b}=\delta^{a}_{\;b}.
$$
Accordingly, the scalar product of a vector with a 1-form does not involve the metric, but only a summation over an index:

$$
\mathbf{A} \cdot \tilde{\mathbf{B}}=\left(A^{a} \mathbf{e}_{a}\right) \cdot\left(B_{b} \tilde{\omega}^{b}\right)=A^{a} \delta_{a}^{\;b} B_{b}=A^{a} B_{a}.
$$

The vector $\mathbf{A}$ carries the same information as the corresponding 1-form $\tilde{\mathbf{A}}$, and we often will not make a distinction between them. Their components are related by

$$
A_{a}=g_{a b} A^{b},
$$
or
$$
A^{a}=g^{a b} A_{b}.
$$
A coordinate basis of 1-forms may be written $\tilde{\omega}^{a}=\widetilde{\mathbf{d} x}^{a}$; geometrically, the basis form $\widetilde{\mathbf{d} x}^{a}$ may be thought of as piercing surfaces of constant coordinate $x^{a}$.

A particular useful one-form is $\widetilde{\mathbf{d} f}$, the gradient of an arbitrary scalar function $f$. In a coordinate basis, it may be expanded according to $\widetilde{\mathbf{d} f}=\partial_{a} f \widetilde{\mathbf{d} x}^{a}$, whereby its components are ordinary partial derivatives. The scalar product between an arbitrary vector $\mathbf{v}$ and the one-form $\widetilde{\mathbf{d} f}$ gives the directional derivative of $f$ along $\mathbf{v}$

$$
\mathbf{v} \cdot \widetilde{\mathbf{d} f}=\left(v^{a} \mathbf{e}_{a}\right) \cdot\left(\partial_{b} f \widetilde{\mathbf{d} x}^{b}\right)=v^{a} \partial_{a} f.
$$