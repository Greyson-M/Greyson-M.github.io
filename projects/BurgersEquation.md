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

[Burgers' equation](https://en.wikipedia.org/wiki/Burgers%27_equation) is a fundamental partial differential equation from fluid mechanics. It is used to model various physical phenomena such as gas dynamics and traffic flow. The equation is given by:

$$
\frac{\partial u}{\partial t} + u \frac{\partial u}{\partial x} = \nu \frac{\partial^2 u}{\partial x^2}
$$

The focus of this demonstration is the inviscid case, where the viscosity term $( \nu )$ is zero.

$$
\frac{\partial u}{\partial t} + u \frac{\partial u}{\partial x} = 0
$$

## Demonstration
![Burgers' Equation Solution](burg.gif)


## Numerical Solution

To solve Burgers' equation numerically, we can use methods such as finite difference, finite volume, finite element, etc.
Due to the nonlinearity of the equation, shocks will form in the solution. [Shocks](https://en.wikipedia.org/wiki/Shock_wave) are discontinuities in the solution that can be difficult to resolve numerically. 

Many typical numerical methods for solving PDEs will not preserve these shocks properly. In the demonstration above, a [finite volume method](https://en.wikipedia.org/wiki/Finite_volume_method), which uese a simple Reimann solver to compute the flux at the boundaries between spacial cells, is compared to the [Lax-Friedrichs method](https://en.wikipedia.org/wiki/Lax%E2%80%93Friedrichs_method), an upwinding finite difference method that is known for its effectivness in solving [conservation laws](https://en.wikipedia.org/wiki/Conservation_law).