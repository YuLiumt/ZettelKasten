## Performance and Optimization Abstractions for Large Scale Heterogeneous Systems in the Cactus/Chemora Framework

- **Author**: [[Erik Schnetter]]
- **Summary**:
	- 
- **Link**: 
- [ADS](https://ui.adsabs.harvard.edu/abs/2013arXiv1308.1343S/abstract) Schnetter E. Performance and Optimization Abstractions for Large Scale Heterogeneous Systems in the Cactus/Chemora Framework. arXiv:1308.1343.

___

## Highlight

- LoopControl
	- Here we present LoopControl, an iterator mechanism to efficiently loop over multi-dimensional arrays for stencil-based loop kernels. LoopControl parallelizes iterations across multiple threads, across multiple SMT threads, performs loop tiling to improve cache efficiency, and honours SIMD vector sizes to ensure an efficient SIMD vectorization is possible.
	- LoopControl monitors the performance of its loops, and dynamically adjusts its parameters to improve performance.
	- LoopControl uses a random-restart hill-climbing algorithm for this dynamic optimization.
	- LoopControl employs hwloc to query the system hardware, and also queries MPI and OpenMP about process/thread setups. hwloc also reports thread-to-core and thread-to-cache bindings that are relevant for performance. All information is gathered automatically, requiring no user setup to achieve good performance.
	- LoopControl assumes that each loop iteration is independent of the others, and can thus be executed in parallel or in an arbitrary order.
	- Since LoopControl cannot influence how arrays are allocated, the programmer needs to specify the array alignment, if any.
- The multi-threading is based on OpenMP threads, but employs a dynamic region selection and load distribution mechanism to handle kernels with non-uniform cost per iteration.