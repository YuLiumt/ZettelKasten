## Adaptive mesh refinement

AMR implies that resolution in the simulation domain is dynamically adapted to the current state of the simulation, i.e., regions that require a higher resolution are covered with blocks with a finer grid (typically by a factor of two); these are called refined levels. At regular intervals, the resolution requirements in the simulation are re-evaluated, and the grid hierarchy is updated; this step is called regridding.

## Berger-Oliger algorithm

