## Lorene - Vector

Lorene can handle a vector field $V$ expressed in either of two types of components (i.e. using two orthonormal triads, of type [[Lorene - Base_val]].

- the Cartesian triad $\left(e_{x}, e_{y}, e_{z}\right)=\left(\frac{\partial}{\partial x}, \frac{\partial}{\partial y}, \frac{\partial}{\partial z}\right)$
- the spherical triad $\left(e_{r}, e_{\theta}, e_{\varphi}\right)=\left(\frac{\partial}{\partial r}, \frac{1}{r} \frac{\partial}{\partial \theta}, \frac{1}{r \sin \theta} \frac{\partial}{\partial \varphi}\right)$

```C++
// Vector field defined by its cartesian components
Vector v_cart(map, CON, map.get_bvect_cart()) ;
// Change to spherical triad
v_cart.change_triad(map.get_bvect_spher()) ;
```

The covariance type of the indices is indicated by an integer which takes two values, defined in file `tensor.h`:
- COV: covariant index
- CON: contravariant index