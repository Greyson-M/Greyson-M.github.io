<script type="text/x-mathjax-config">
  MathJax.Hub.Config({
    tex2jax: {
      inlineMath: [ ['$','$'], ["\\(","\\)"] ],
      processEscapes: true
    }
  });
</script>
    
<script type="text/javascript"
        src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
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

To solve Burgers' equation numerically, we can use methods such as finite difference, finite volume, finite element, etc.
Due to the nonlinearity of the equation, it is possible for shocks to form in the solution. Shocks are discontinuities in the solution that can be difficult to resolve numerically. 

Because of this potential solutions containing shocks, many typical numerical methods for solving PDEs will not preserve these shocks properly. In the demonstration above, a finite volume method, which uese a simple Reimann solver to compute the flux at the boundaries between spacial steps, is compared to the Lax-Friedrichs method, an upwinding finite difference method that is known for its effectivness in solving conservation laws.

## Analytical Solution
A rough outline of an analytical solution to the Cauchy problem presented in the demonstration can be found here: [Burgers' Equation Analytical Solution](weaksolution.pdf). (Note: this is not a rigorous proof, more of an outline of the analytical methods used, pulled from my personal notes on the subject.)