## Metric

Components of the flat metric in an orthonormal cartesian frame

```C++
Sym_tensor g_uu(map, CON, map.get_bvect_cart()) ;
// write of a particular element (index i,j)
g_uu.set(1,1) = 1 ;
g_uu.set(2,2) = 1 ;
g_uu.set(3,3) = 1 ;
g_uu.set(1,2).annule_hard() ; // Sets it to zero in a hard way.
g_uu.set(1,3).annule_hard() ;
g_uu.set(2,3).annule_hard() ;
g_uu.std_spectral_base() ;
// 3-metric
Metric gam(g_uu) ;
```

## Tensor Calculus

- Tensorial product
```C++
Tensor_sym tens3 = tens1 * tens2 ; 
```
- Contraction
```C++
// Contraction on two indices of a single tensor (trace).
Scalar scal = contract(tens, 0, 1) ; // 0 = first index, 1 = second index, and so on...
// Contracting two tensors :
Tensor tens3 = contract(tens1, 1, tens2, 0) ;
```
- Raising an index with the metric `gam`
```C++
Tensor tens = tens.up(1, gam) ;
```
- The covariant derivative of $V$ with respect to the metric `gam`
```C++
Tensor tens = v.derive_cov(gam) ;
```
- The Ricci tensor associated with the metric `gam`
```C++
Sym_tensor ricci = gam.ricci() ;
```
- Lie derivative with respect to $V$
```C++
Sym_tensor tens = tens.derive_lie(v) ; 
```
- and so on.