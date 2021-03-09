## Carpet

[Carpet](https://www.carpetcode.org) is the [[Adaptive mesh refinement]] driver mainly developed by [[Erik Schnetter]].



![[Pasted image 20201211233920.png]]

An adaptive mesh refinement (AMR) approach based on the Carpet mesh-refinement driver is used to both increase resolution and extend the spatial domain, placing the outer boundary as close as possible to the wave zone.

Carpet can run on several processors in parallel using MPI for communication. Each grid can be broken down into several components, and every component has a home processor. Carpet also contains operators to move certain regions to a different processor, or to synchronise all components of a grid.

In order to allow multiple processors to run efficiently in parallel, the grid is broken down into several rectangular components, and each processor is assigned one of these components.

The components will usually overlap by a few grid points, so as to allow the processors to e.g. calculate spatial derivatives (which require neighboring grid points) without having to communicate for every grid point. From time to time it is then necessary to synchronise the overlapping region, which is the only time at which communication happens.


- Carpet offers [[Parallel Calculations#Hybrid OpenMP MPI]]


## Bounding box 

A bounding box (bbox) describes the location and shape of a rectangular region, a bounding box set (bboxset) describes a set of non-overlapping bounding boxes.

Since a bboxset is used to describe the grid points that make up a particular refinement level, its points lie on a uniform grid. Each grid point can be described by its location, which can be expressed as $x_{0}^{i}+n^{i} \cdot \Delta x^{i}$ where $x_{0}^{i}$ and $\Delta x^{i}$ describe origin and spacing of the grid, and $n^{i}$ is a vector with integer elements. (The abstract index $i$ denotes that these are vectors, where $i \in[1 \ldots D]$ in $D$ dimensions.)