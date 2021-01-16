## Driver

In [[Cactus]], infrastructure capabilities such as memory management, parallelization, time evolution, mesh refinement, and I/O are delegated to a set of special driver components.

The Einstein Toolkit offers two drivers:

- [[PUGH Thorn]] - A uniform grid with Cartesian topology
- [[Carpet Thorn]] - Adaptive mesh refinement

Incorrect memory allocation and the use of uninitialized variables can easily lead to bugs in codes which are hard to detect. Various Cactus thorns provide tools which help locate such errors, for example by initializing variables to have a value of NaN and then checking for these values during the simulation.

