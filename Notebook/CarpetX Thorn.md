## CarpetX Thorn

CarpetX is a [[Cactus]] driver based on [[AMReX]], a software framework for block-structured AMR (adaptive mesh refinement). CarpetX is intended for the [[Einstein Toolkit]].

- Each time step goes into its own file. Files are never re-opened.
- Norms (reductions): all in one file
- TSV (Tab-Separated Values, ASCII): one file per group
	- Now easily readable by Excel, gnuplot, Julia, Mathematica, Python
- Silo (HDF5): Standard VisIt format

## Tutorial

- https://lsu.zoom.us/rec/share/YcrCqkVkEZ5BjqZrXQa-vt7EOGyXFL8rD26-GASPOEhSYvscG3AAEIShRuIM9FD4.p2KUW93Ytojr6L8V