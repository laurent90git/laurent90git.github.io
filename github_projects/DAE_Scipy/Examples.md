# Examples

Please come back later, this is still in the works :)

Here are a few example results obtained with this code. The initial example also serves as a short introduction to differential-algebraic equations.

## 1. Index-3 DAE: Pendulum

The movement of pendulum with an infinitely stiff rod can be modelled in cartesian coordinates as a set of index-3 DAEs.
Applying Newton's law in the $$(x,y)$$ reference frame, $$x$$ being the horizontal axis, and $$y$$ the vertical axis (positive upwards), we obtain:

$$
\begin{align}
 d_t x &= v_x \tag{1.1}\label{eq1}\\
 d_t y &= v_y \tag{1.2}\label{eq2}\\
 d_t v_x &= - \tfrac{T}{m} sin(\theta) \tag{1.3}\label{eq3}\\
 d_t v_y &=  \tfrac{T}{m} cos(\theta) - g \tag{1.4}\label{eq4}\\
 x^2 + y^2 &= r_0^2 \tag{1.5}\label{eq5}
\end{align}
$$
 
with $$m$$ the mass attached at the end of the rod, $$L$$ the length of this (massless) rod, and $$T$$ the force it exerts on the mass.

Equation \eqref{eq5} ensures that the rod-length remains constant.
By using $$sin(\theta) = x/\sqrt{x^2+y^2}$$
and $$cos(\theta) = - y / \sqrt{x^2+y^2}$$,
we may introduce $$\lambda=T/\sqrt{x^2+y^2}$$ and rewrite Equations \eqref{eq3} and \eqref{eq4} as:

$$
\begin{align}
 d_t v_x &= - \lambda x/m \tag{1.6}\label{eq6}\\
 d_t v_y &= - \lambda y/m - g \tag{1.7}\label{eq7}
\end{align}
$$

Here, $$\lambda$$ plays the role of a Lagrange multiplier, which adjusts istelf in time so that equation \eqref{eq5} is not violated,
i.e. the solution remains on the manifold $$x^2 +y^2 - r0^2 = 0$$.
  
The issue is that the time derivative of $$T$$ does not appear, hence a trivial application of classical ODE integrators is not possible.
Equation \eqref{eq5} is algebraic, and is also referred to as a constraint. The variable $lambda$ is termed *algebraic* variable, while the other variables are termed *differential*.
The system is therefore said to be a set of  *differential-algebraic equations* (DAEs).
A key attribute os such a system is its *index*, which is the number of times one or multiple equations from the original system must be derived in order to obtain an explicit expression for the time derivatives of the algebraic variables.

We can show that the system (\ref{eq1}-\ref{eq5}}) is of index 3.
Let us differentiate the constraint \eqref{eq5} to time. If we do it once, we obtain:

    x*vx + y*vy = 0                    (6)

  Physically, this means that the velocity vector of the pendulum mass is
  always perpendicular to the rod. The system (1,2,3a,3b,6) is a DAE of index 1.
  If we differentiate it once more with respect to time, we obtain:

    lbda*(x^2 + y^2)  + m*(vx^2 + vy^2) - m*g*y = 0     (7)

## 2. Large-Scale index-3 DAE: pendulum chain

Using the index-3 formulation of the rod constraint, it is easy to describe the movement of a chain of sequentially-linked pendulums, since no specific change of reference needs to be performed from one pendulum to the next.
Here is an example showing the free fall of chain, whose tip surprisingly falls faster than a free-falling mass. More information on this phenoeman can be found [here](https://www.researchgate.net/publication/29639055_The_motion_of_a_freely_falling_chain_tip).
<iframe width="320" height="560" src="https://www.youtube.com/embed/VESQ7IXPlQw" title="Free falling chain simulation" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

## 3. Stiff ODEs

The DAE-adapted code remains compatible with purely differential equations. Radau5 is often recognised as the archetype of the stiff integrator.
Being L-stable, possessing both a high order and high stage order with stiff accuracy, it handles stiff and very stiff equations naturally. Its embedded error estimate can also be corrected for stiffness, ensuring the time step is not limited by stiffness.

The well-known Robertson ODE is one such model. It models a small network of reactions with vastly different time scales. Its ODE formulation is:
TODO

An equivalent index-1 formulation is:
TODO