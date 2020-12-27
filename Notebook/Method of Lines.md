## Method of Lines

The idea is to convert a system of partial differential equations (PDEs) into a system of ordinary differential equations (ODEs) by leaving the problem continuous in time first, but discretise in space.

Well known stable ODE integrators such as Runge-Kutta can be used in the time integration, so that instabilities can only arise from the spatial discretisation or the equations themselves.