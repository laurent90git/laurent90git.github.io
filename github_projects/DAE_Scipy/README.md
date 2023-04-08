# [DAE-Scipy](https://github.com/laurent90git/DAE-Scipy)

This Python package is an extension of the native Python ODE solver Radau from the Scipy library.

It enables the introduction of use of a constant mass matrix $$M$$
to solve differential-algebraic equations up to index 3 :

<p align="center">
$$My' = f(t,y)$$
</p>

Extensions to variable mass matrices and equations of the form $$d_t g(y) = f(t,y)$$ are in the works !