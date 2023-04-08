# pyRadau5

`pyRadau5` is a Python wrapper around the well-known Fortran ODE/DAE integrator [Radau5](http://www.unige.ch/~hairer/software.html), an adaptive high-order L-stable time implicit Runge-Kutta method relying on Radau quadrature points. This method is especially suited to the integration of stiff systems and DAEs up to index 3 in the following form:

<p align="center">
$$M y' = f(t,y)$$
</p>

with a potentielly singular mass matrix $$M$$.

The original Fortran code has been instrumented to gain deeper insight into its internal behaviour (step rejection, Newton convergence...).
Optional parameters have been added to enhance the robustness of the linear system solution for high-index DAEs.