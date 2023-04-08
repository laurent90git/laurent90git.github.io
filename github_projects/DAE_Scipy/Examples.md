# Examples

Please come back later, this is still in the works :)

Here are a few example results obtained with this code. The initial example also serves as a short introduction to differential-algebraic equations.

## 1. Index-3 DAE: Pendulum

The movement of pendulum with an infinitely stiff rod can be modelled in cartesian coordinates as a set of index-3 DAEs.
Applying Newton's law in the $$(x,y)$$ reference frame, $$x$$ being the horizontal axis, and $$y$$ the vertical axis (positive upwards), we obtain:

$$
\begin{align*}
 d_t x &= v_x \\
 d_t y &= v_y \\
 d_t v_x &= - \tfrac{T}{m} sin(\theta) \\
 d_t v_y &=  \tfrac{T}{m} cos(\theta) - g \\
 x^2 + y^2 &= r_0^2
\end{align*}
$$


\begin{align}
 x^2 + y^2 &= r_0^2 \tag{1.1}\label{eq1}
\end{align}

\begin{align}
 x^2 + y^2 &= r_0^2
\end{align}

\begin{align}
 x^2 + y^2 &= r_0^2 \tag{eq1}
\end{align}


$$
\begin{align*}
 x^2 + y^2 &= r_0^2 \tag{eq1}
\end{align*}
$$

$$
\begin{align*}
 x^2 + y^2 &= r_0^2 \tag{1}
\end{align*}
$$


calling \eqref{eq1}

\ref{eq1}

 
 
with $$m$$ the mass attached at the end of the rod, $$L$$ the length of this (massless) rod, and $$T$$ the force it exerts on the mass.

testing:


  Equation (5) ensures that the rod-length remains constant.
  By expression sin(theta) as x/sqrt(x**2+y**2) and cos(theta)=-y/sqrt(x**2+y**2),
  we may introduce lbda=T/sqrt(x**2+y**2) and rewrite Equations (4) and (5) as:

    d(vx)/dt = -lbda*x/m               (3a)
    d(vy)/dt = -lbda*y/m - g           (4a)

  The new variable "lbda" plays the role of a Lagrange multiplier, which adjusts
  istelf in time so that equation (5) is not violated, i.e. the solution remains
  on the manifold x^2 +y^2 - r0^2 = 0.

  The corresponding system (1,2,3a,4a,5) is a DAE of index 3.
  We can obtain lower-index DAE by differentiating equation (5) with respect
  to time. If we do it once, we obtain:

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