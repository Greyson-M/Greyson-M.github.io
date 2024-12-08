<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.13.18/dist/katex.min.css">
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.13.18/dist/katex.min.js"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.13.18/dist/contrib/auto-render.min.js"></script>
<script>
    document.addEventListener("DOMContentLoaded", function() {
        renderMathInElement(document.body);
    });
</script>


# Numerical Solution to Inviscid Burgers' Equation

Burgers' equation is a fundamental partial differential equation from fluid mechanics. It is used to model various physical phenomena such as gas dynamics and traffic flow. The equation is given by:

$$
\frac{\partial u}{\partial t} + u \frac{\partial u}{\partial x} = \nu \frac{\partial^2 u}{\partial x^2}
$$

The focus of this demonstration is the inviscid case, where the viscosity term $( \nu )$ is zero.

$$
\frac{\partial u}{\partial t} + u \frac{\partial u}{\partial x} = 0
$$

where:
- $( u )$ is the velocity field,
- $( t )$ is time,
- $( x )$ is the spatial coordinate,

## Demonstration
![Burgers' Equation Solution](burg.gif)


## Numerical Solution

To solve Burgers' equation numerically, we can use methods such as finite difference, finite element, or spectral methods. 
Due to the nonlinearity of the equation, it is possible for shocks to form in the solution. Shocks are discontinuities in the solution that can be difficult to resolve numerically. 

Because of this, many typical numerical methods for solving PDEs will not preserve these shocks properly. In the demonstration above, a finite volume method, which uese a simple Reimann solver to compute the flux at the boundaries between spacial steps, is compared to the Lax-Friedrichs method, a finite difference method that is known for its effectivness in solving conservation laws.

## Analytical Solution
A rough outline of the analytical solution to Burgers' equation with the initial values shown in the demonstration can be found here: [Burgers' Equation Analytical Solution](weaksolution.pdf)

**The Cauchy-Schwarz Inequality**
$$\left( \sum_{k=1}^n a_k b_k \right)^2 \leq \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right)$$