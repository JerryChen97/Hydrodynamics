# Hydrodynamics
This is a repo for the homework3 of Computational Physics: solving the Burger equation

## Introduction
In this homework we aim to solve the nonlinear partial differential equation

<p align="center"><img src="/tex/46bf5813783a9a47d2407d2830c7ea63.svg?invert_in_darkmode&sanitize=true" align=middle width=255.951102pt height=49.315569599999996pt/></p>

This is also well-known as the inviscid Burgers equation. 

## Theoretical Analysis
By characteristic method, we can get the characteristic equation
<p align="center"><img src="/tex/0820f3991312f4b9b65074ac6a532ab4.svg?invert_in_darkmode&sanitize=true" align=middle width=198.5654022pt height=39.452455349999994pt/></p>
and then we know that 
<p align="center"><img src="/tex/b3d14a1cb1a3b018721408a6bc193082.svg?invert_in_darkmode&sanitize=true" align=middle width=581.9330863499999pt height=33.81208709999999pt/></p>

This implies that along the characteristic curve <img src="/tex/f92a2fed82f1dacdec6e4d5a05fbbf97.svg?invert_in_darkmode&sanitize=true" align=middle width=28.11651809999999pt height=24.65753399999998pt/>, <img src="/tex/ea7f6e7c713ea13afc88230bcadc76b9.svg?invert_in_darkmode&sanitize=true" align=middle width=63.554204999999996pt height=24.65753399999998pt/> is constant,
<p align="center"><img src="/tex/5483cc80b3ba126b544ddec48d808783.svg?invert_in_darkmode&sanitize=true" align=middle width=224.58916589999998pt height=16.438356pt/></p>
along with the solution to the characteristic equation
<p align="center"><img src="/tex/069262788f1ca30ac67b23bd89b517f3.svg?invert_in_darkmode&sanitize=true" align=middle width=169.30707915pt height=16.438356pt/></p>
offering us an implicit solution to the inviscid Burgers equation
<p align="center"><img src="/tex/eb178b18aa3683bf75d5f1cd027e0aff.svg?invert_in_darkmode&sanitize=true" align=middle width=151.25197725pt height=16.438356pt/></p>

Even though usually due to the complexity of <img src="/tex/10898c33912164da6714fe6146100886.svg?invert_in_darkmode&sanitize=true" align=middle width=15.96281939999999pt height=14.15524440000002pt/>, we will not be able to solve the explicit solution, we can still manipulate <img src="/tex/e714a3139958da04b41e3e607a544455.svg?invert_in_darkmode&sanitize=true" align=middle width=15.94753544999999pt height=14.15524440000002pt/> to give a parametric curve as the solution.

However, such a solution cannot guarantee itself to be a function, which is necessary to be the real solution.
After a certain point <img src="/tex/f72fc41d42dcd7a00b572b76be6d4d81.svg?invert_in_darkmode&sanitize=true" align=middle width=16.42873814999999pt height=20.221802699999984pt/>, this characteristic solution will not hold anymore, along with the formation of shock.

## Numerical Calculation
In this homework we calculated the convergence order of the numerical method offered by William at different resolutions:
- Before the formation of shock, we compare the numerical results with the theoretical implicit solution. The original code of Will is edited by me to be able to offer an exact solution inside the class.
- After the formation of shock, we compare the numerical results with each other to approximate the convergence order, i.e.
<p align="center"><img src="/tex/cf4ccdf1db76e29d14aeb7bcd42ba4e6.svg?invert_in_darkmode&sanitize=true" align=middle width=115.84265384999999pt height=38.96533905pt/></p>
where <img src="/tex/2ad9d098b937e46f9f58968551adac57.svg?invert_in_darkmode&sanitize=true" align=middle width=9.47111549999999pt height=22.831056599999986pt/> is the lattice space.

## Findings
Not everywhere (w.r.t. <img src="/tex/332cc365a4987aacce0ead01b8bdcc0b.svg?invert_in_darkmode&sanitize=true" align=middle width=9.39498779999999pt height=14.15524440000002pt/>) our minmod method will reach the order of 2.
This is because only at the shock region, where the numerical method shows obvious errors, the difference of errors among different resolutions can be presented well.
![alt text](allerrors.png "Title")
![alt text](pointwise.png "Title")

