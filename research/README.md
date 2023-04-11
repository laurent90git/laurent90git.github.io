---
sort: 2
---
# Research

My current research interests lie in the development of simulation tools and numerical methods for the study of reactive fluid flows, and also the development of high-order adaptive coupling of specialised solvers to enable accurate and efficient unsteady multiphysics simulations (e.g. conjugate heat transfer).

My Google Scholar page is [here](https://scholar.google.fr/citations?user=K0jov1cAAAAJ).

## Summary of my PhD work

For my PhD thesis, I worked during 3 years on the subject
<p align="center">
**"Multiphysics modelling and simulation of the ignition transient in solid rocket motor"** .
</p>
This work was conducted by Prof. Marc Massot from CMAP, Ecole Polytechnique, and Joël Dupays, research enginneer at ONERA, the French Aerospace Lab.
The final manuscript is available [here](https://www.theses.fr/2022IPPAX004), and you can watch the replay of the defense [here](https://www.youtube.com/watch?v=sHh0csPVN0M).

This work brought a few contributions, e.g. :
- clarification of the mathematical nature of the model describing the burning of a solid propellant (differential-algebraic system of index 1)
- choice of well-suited numerical methods for the simulation of the previous model (high-order adaptive ESDIRK methods)
- implementation of the numerical strategy in the `Vulc1D` Fortran code
- integration of the previous code as a dynamic boundary condition in the CFD toolchain CEDRE from ONERA.
- assessment through simulations of the modelling assumptions
- exploration of adaptive high-order code coupling techniques to enhance the accuracy and efficiency of simulations involving multiple solvers.


## Reasearch work at ONERA

Following my PhD defense in early 2022, I have become a research engineer at ONERA in Palaiseau, France.
My main subjects are:
- modelling and simulation of rocket propulsion and aerodynamics
- development of the adaptive code-coupling library `Rhapsopy`, which will be presented at the Coupled2023 conference, demosntrating a strategy to enable high-order adaptive coupling of multiple specialised solvers, with the added ability of performing an iterative implicit coupling, greatly improving the accuracy and stability of coupled computations.
