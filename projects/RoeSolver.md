# Finite Volume: Euler Equations

Euler equations are a set of hyperbolic partial differential equations that describe the motion of an inviscid fluid. The compressible equations are given by:
$$
\begin{align*}
\rho_t + (\rho u)_x  = 0 \\
(\rho u)_t + \left( \rho u^2 + p \right)_x = 0 \\
E_t + \left( (E + p)u \right)_x = 0
\end{align*}
$$
Where:
- $\rho$ is the density of the fluid
- $u$ is the velocity of the fluid
- $p$ is the pressure of the fluid
- $E$ is the total energy of the fluid
- $P$ is the pressure of the fluid, related to the density and internal energy by  an equation of state. For example, for polytropic gases, the equation of state is given by:
$$
P = (\gamma - 1) (E - \frac{1}{2} \rho u^2)
$$

- $\gamma$ is the ratio of specific heats, which is a constant for a given gas. For air, $\gamma \approx 1.4$.

## Numerical Solution
I use a Godunov-type finite volume method to solve the Euler equations. The method is based on the idea of partitioning the domain into a grid of cells and solving the equations in each cell. The fluxes at the boundaries of the cells are computed using a Riemann solver. The Riemann problem is an initial value problem that consists of two constant states separated by a discontinuity. The solution to the Riemann problem gives the fluxes at the boundaries of the cells. 

For the Riemann solver I used the method of Roe. The Roe solver is a Godunov-type Riemann solver that is based on the idea of linearizing the equations around the average state of the two constant states. 

![Shock Tube](shock_tube.gif)
The initial condition is a shock tube problem, where the initial condition is given by:
$$
\begin{align*}
\rho(x,0) = \begin{cases} 1 & x < 0 \\ 0.125 & x > 0 \end{cases} \\
u(x,0) = \begin{cases} 0 & x < 0 \\ 0 & x > 0 \end{cases} \\
p(x,0) = \begin{cases} 1 & x < 0 \\ 0.1 & x > 0 \end{cases}
\end{align*}
$$

The Exact solution of the Riemann problem for Euler equations is known, so that can be used to test the accuracy of the method. Comparison is given below. The exact solution is given by the dashed line, and the numerical solution is given by the solid line. 
![Comparison of Exact and Numerical Solution](shock_compare.gif)