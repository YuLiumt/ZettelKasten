## GR - Lie derivative

Consider a (non-zero) vector field $X^{a}$ in a manifold $M$. We can find the integral curves $x^{a}(\lambda)$ of $X^{a}$ by integrating the ordinary differential equations

$$
\frac{d x^{a}}{d \lambda}=X^{a}(\mathbf{x}(\lambda)).
$$
Here $\lambda$ is some affine parameter, and we use bold-face notation $\mathbf{x}$ instead of index notation $x^{a}$ for the coordinate location in the argument to make the expressions more transparent. For a
sufficiently well-behaved vector field $X^{a}$ a solution is guaranteed, at least locally, by the existence and uniqueness theorem for ordinary differential equations. This procedure is completely equivalent
to finding the paths of fluid particles, given their fluid velocity. 

We would now like to define a derivative of a tensor field, say $T^{a}_{\; b}$, using $X^{a}$. This involves comparing the tensor field at two different points along $X^{a}$, say $P$ and $Q$, and taking the limit as $Q$ tends to $P$. This is where we encounter a conceptual problem: what do we mean by comparing two tensors at two different locations in the manifold $M$?

We could, of course, simply compare components of the tensor field $T^{a}_{\; b}$ at $P$, $T^{a}_{\; b}(P)$ and at $Q$, $T^{a}_{\; b}(Q)$. This leads to the definition of the partial derivative. \gray{Note, however, the partial derivative of a tensor is not a tensor.}

In order to differentiate a tensor in a tensorial manner, we therefore have to evaluate the two tensors at the same point. To do so, we have to drag one tensor to the other point before we can compare the two tensors. For example, we can drag $T^{a}_{\; b}(P)$ along $X^{a}$ to the point $Q$. At $Q$, we can then compare the dragged tensor, which we will denote with primes, $T^{a^{\prime}}_{\; b^{\prime}}$, with the tensor already present at $Q$, $T^{a}_{\; b}(Q)$.

![[Pasted image 20201214182403.png]]

However, this recipe still leaves open how we drag $T^{a}_{\; b}$ along $X^{a}$. One approach would be to parallel-transport the tensor $T^{a}_{\; b}$ from $P$ to $Q$. This idea leads to the definition of the covariant derivative. In some sense an even
more straight-forward approach is to view the dragging as a simple coordinate transformation from $P$ to $Q$. This, in fact, defines the Lie derivative. Unlike the covariant derivative, the Lie derivative does not require an affine connection, and hence requires less structure.

Consider now the infinitesimal coordinate transformation

\begin{equation}
    \label{eq:00215.1}
    x^{a^{\prime}}=x^{a}+\delta \lambda X^{a}(\mathbf{x})
\end{equation}
which maps the point $P$, with coordinates $x^{a}$, into the point $Q$, with coordinates $x^{a^{\prime}}$.

Assuming a coordinate basis we can differentiate \eqref{eq:00215.1} to find

$$
\frac{\partial x^{a^{\prime}}}{\partial x^{b}}=\tensor{\delta}{^{a}_{b}}+\delta \lambda \partial_{b} X^{a},
$$
and, to first order in $\delta \lambda$,

\begin{equation}
    \label{eq:00215.3}
    \frac{\partial x^{a}}{\partial x^{b^{\prime}}}=\tensor{\delta}{^{a}_{b}}-\delta \lambda \partial_{b} X^{a}.
\end{equation}

We now start at point $P$, where the components of the tensor field $\tensor{T}{^{a}_{b}}$ are $\tensor{T}{^{a}_{b}}(\mathbf{x})$. We map this tensor into the primed tensor $\tensor{T}{^{a^{\prime}}_{b^{\prime}}}\left(\mathbf{x}^{\prime}\right)$ at $Q$ with the help of the coordinate transformation \eqref{eq:00215.1}

\begin{equation}
    \label{eq:00215.4}
    \begin{aligned} 
        \tensor{T}{^{a^{\prime}}_{b^{\prime}}}\left(\mathbf{x}^{\prime}\right) &=\frac{\partial x^{a^{\prime}}}{\partial x^{c}} \frac{\partial x^{d}}{\partial x^{b^{\prime}}} \tensor{T}{^{c}_{d}}(\mathbf{x}) \\ &=\left(\tensor{\delta}{^{a}_{c}}+\delta \lambda \partial_{c} X^{a}\right)\left(\tensor{\delta}{^{d}_{b}}-\delta \lambda \partial_{b} X^{d}\right) \tensor{T}{^{c}_{d}}(\mathbf{x}) \\ &=\tensor{T}{^{a}_{b}}(\mathbf{x})+\delta \lambda\left(\partial_{c} X^{a} \tensor{T}{^{c}_{b}}(\mathbf{x})-\partial_{b} X^{c} \tensor{T}{^{a}_{c}}(\mathbf{x})\right)+\mathcal{O}\left(\delta \lambda^{2}\right).
    \end{aligned}
\end{equation}
For the purpose of defining the Lie derivative this is the result of dragging $\tensor{T}{^{a}_{b}}$ along $\tensor{X}{^{a}}$ from $P$ to $Q$. The components of the unprimed tensor already present at $Q$, $\tensor{T}{^{a}_{b}}(\mathbf{x}^{\prime})$, can be related to $\tensor{T}{^{a}_{b}}(\mathbf{x})$ by Taylor expanding

\begin{equation}
    \label{eq:00215.5}
    \begin{aligned} 
        \tensor{T}{^{a}_{b}}\left(\mathbf{x}^{\prime}\right)&=\tensor{T}{^{a}_{b}}(x^{c^{\prime}})\\ &=\tensor{T}{^{a}_{b}}\left(x^{c}+\delta \lambda X^{c}\right)\\ &=\tensor{T}{^{a}_{b}}(\mathbf{x})+\delta \lambda X^{c} \partial_{c} \tensor{T}{^{a}_{b}}+\mathcal{O}\left(\delta \lambda^{2}\right)
    \end{aligned}
\end{equation}

We now denote the Lie derivative of $\tensor{T}{^{a}_{b}}$ with respect to $\tensor{X}{^{a}}$ as $\mathcal{L}_{X} \tensor{T}{^{a}_{b}}$ and define

$$
\mathcal{L}_{X} \tensor{T}{^{a}_{b}}=\lim _{\delta \lambda \rightarrow 0} \frac{\tensor{T}{^{a}_{b}}\left(x^{\prime}\right)-\tensor{T}{^{a^{\prime}}_{b^{\prime}}}\left(x^{\prime}\right)}{\delta \lambda}.
$$
Note that we evaluate both tensors at the same point, so that the Lie derivative of a tensor is again a tensor, and moreover a tensor of the same rank.

For our tensor $\tensor{T}{^{a}_{b}}$ we can insert \eqref{eq:00215.4} and \eqref{eq:00215.5} into \eqref{eq:91025.13} to find

$$
\mathcal{L}_{\mathbf{X}} \tensor{T}{^{a}_{b}}=X^{c} \partial_{c} \tensor{T}{^{a}_{b}}-\tensor{T}{^{c}_{b}} \partial_{c} X^{a}+\tensor{T}{^{a}_{c}} \partial_{b} X^{c}.
$$
The Lie derivative of a general tensor field can be found by first taking a partial derivative of the tensor and contracting it with $\tensor{X}{^{a}}$, and then adding additional terms involving derivatives of $\tensor{X}{^{a}}$ as in \eqref{eq:00215.6} for each index, with a negative sign for contravariant indices and a positive sign for covariant indices.

We can always introduce an adapted coordinate system, in which, for example, the coordinate basis vector $e_{(0)}^{a}$ is aligned with $\tensor{X}{^{a}}$, and all the other coordinates are constant along $\tensor{X}{^{a}}$. Setting $X^{a}=e_{(0)}^{a}$ then yields

$$
X^{\alpha}=\tensor{\delta}{^{\alpha}_{0}}=(1,0, \ldots, 0).
$$
We have used greek indices as opposed to the latin indices of our abstract index notation, since this relationship for components only holds in these adapted coordinates. Writing equation \eqref{eq:00215.6} in this coordinate system, we immediately find

$$
\mathcal{L}_{\mathbf{X}} \tensor{T}{^{\alpha}_{\beta}}=\frac{\partial}{\partial x^{0}} \tensor{T}{^{\alpha}_{\beta}}.
$$
In this sense the Lie derivative is a tensorial generalization of the partial derivative.

We can replace all the partial derivatives with covariant derivatives, obtaining covariant (coordinate-free) expressions for the Lie derivative.

$$
\mathcal{L}_{\mathbf{X}} \tensor{T}{^{a}_{b}}=X^{c} \nabla_{c} \tensor{T}{^{a}_{b}}-\tensor{T}{^{c}_{b}} \nabla_{c} X^{a}+\tensor{T}{^{a}_{c}} \nabla_{b} X^{c}
$$