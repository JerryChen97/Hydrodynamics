# Hydrodynamics
This is a repo for the homework3 of Computational Physics: solving the Burger equation

## Introduction
In this homework we aim to solve the nonlinear partial differential equation

$$
\left\{\begin{aligned}
u_{t}+u u_{x} &=0, & & x \in \mathbb{R}, & t>0 \\
u(x, 0) &=u_{0}(x), & & x \in \mathbb{R}
\end{aligned}\right.
$$

This is also well-known as the inviscid Burgers equation. 

## Theoretical Analysis
By characteristic method, we can get the characteristic equation
$$
\left\{\begin{array}{c}
x^{\prime}(t)=u(x(t), t), \quad t>0 \\
x(0)=x_{0}
\end{array}\right.
$$
and then we know that 
$$
\frac{d}{d t}[u(x(t), t)]=u_{t}(x(t), t)+x^{\prime}(t) u_{x}(x(t), t)=u_{t}(x(t), t)+u(x(t), t) u_{x}(x(t), t)=0
$$

This implies that along the characteristic curve $x(t)$, $u(x(t), t)$ is constant,
$$
u(x(t), t)=u(x(0), 0)=u_{0}\left(x_{0}\right)
$$
along with the solution to the characteristic equation
$$
x=x_{0}+u_{0}\left(x_{0}\right) t, t>0
$$
offering us an implicit solution to the inviscid Burgers equation
$$
u(x, t)=u_{0}\left(x_{0}(x, t)\right)
$$

Even though usually due to the complexity of $u_0$, we will not be able to solve the explicit solution, we can still manipulate $x_0$ to give a parametric curve as the solution.

However, such a solution cannot guarantee itself to be a function, which is necessary to be the real solution.
After a certain point $t_B$, this characteristic solution will not hold anymore, along with the formation of shock.

## Numerical Calculation
In this homework we calculated the convergence order of the numerical method offered by William at different resolutions:
- Before the formation of shock, we compare the numerical results with the theoretical implicit solution. The original code of Will is edited by me to be able to offer an exact solution inside the class.
- After the formation of shock, we compare the numerical results with each other to approximate the convergence order, i.e.
$$ \log_2 \frac{u_h - u_{h/2}}{u_{h/2} - u_{h/4}} $$
where $h$ is the lattice space.

## Findings
Not everywhere (w.r.t. $x$) our minmod method will reach the order of 2.
This is because only at the shock region, where the numerical method shows obvious errors, the difference of errors among different resolutions can be presented well.
![alt text](allerrors.png "Title")
![alt text](pointwise.png "Title")

## Acknowledgement
Thanks to Cristian for elaborate discussion with me regarding all respects of this homework.
