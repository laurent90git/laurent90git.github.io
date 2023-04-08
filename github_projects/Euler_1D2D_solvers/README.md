# Finite-volume Euler solvers

## [CFD Euler 1D]()

This is a pure Python CFD solver for the simulation of a one-dimensional compressible flow of a single perfect gas.
It is a useful platform to learn about finte-volume schemes and test various approaches.
Implemented are the simple first-order Godunov scheme, and the second-order MUSCL-Hancock scheme with limiters.
Time integration is mostly implicit with CFL-based time step.

Here is the space-time diagram of the Schlieren field ($$log10(||\mathrm{grad}(\rho)||)$$) which visualises the various waves (shocks, contact discontinuity and rarefactions) which appear during the simulation of a simple shock tube.

## [CFD Euler 2D]()

This is a modification of the previous code for the simulation of two-dimensional flows. Note that performance becomes relatively poor due to the pure Python interface, however it is still an interesting learning platform.

Here is an animation of a Rayleigh instability when a flow is submitted to a gravity field:

*(Note that we can spot pressure waves moving up and down, which surely accelerate the destabilisation, these waves are due to a small error in the initial field)*