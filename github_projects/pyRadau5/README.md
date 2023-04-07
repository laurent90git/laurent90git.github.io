# pyRadau5

`pyRadau5` is a Python wrapper around the well-known Fortran ODE/DAE integrator [Radau5](http://www.unige.ch/~hairer/software.html), an adaptive high-order L-stable time implicit Runge-Kutta method, especially suited to the integration of stiff systems and DAEs.

The original Fortran code has been instrumented to gain deeper insight into its internal behaviour (step rejection, Newton convergence...).
Optional parameters have been added to enhance the robustness of the linear system solution for high-index DAEs.


source: `{{ page.path }}`
