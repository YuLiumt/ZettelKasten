# Carpet Thorn

[Carpet](www.carpetcode.org) is a mesh-refinement driver mainly developed by [[Erik Schnetter]].

[[Adaptive mesh refinement]]

![[Pasted image 20201211233920.png]]

An adaptive mesh refinement (AMR) approach based on the Carpet mesh-refinement driver is used to both increase resolution and extend the spatial domain, placing the outer boundary as close as possible to the wave zone.

Carpet can run on several processors in parallel using MPI for communication. Each grid can be broken down into several components, and every component has a home processor. Carpet also contains operators to move certain regions to a different processor, or to synchronise all components of a grid.

In order to allow multiple processors to run efficiently in parallel, the grid is broken down into several rectangular components, and each processor is assigned one of these components.

The components will usually overlap by a few grid points, so as to allow the processors to e.g. calculate spatial derivatives (which require neighboring grid points) without having to communicate for every grid point. From time to time it is then necessary to synchronise the overlapping region, which is the only time at which communication happens.