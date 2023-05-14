# 2.1 Differential Equations and Solutions
## Ordinary Differential Equations
- An **Ordinary Differential Equation (ODE)** is an equation with a single variable with one or more of its derivatives.
	- $\frac{dy}{dt}=y-t$ is an ODE where $y=y(t)$ is the unknown and $t$ is independent.
- Equations are called **first order** because the highest order derivative of the unknown function is only the first level.
	- $y''=y^2$ is an example of a **second order** differential equation.
- Equations are called **ordinary** because there are only functions of a single variable. **Partial Differential Equations (PDE)** deal with functions of with multiple independent variables.
	- For example, the differential equation with function $w$ of independent variables $t$ and $x$ is $$
\frac{ \partial^{2}w }{ \partial t^{2} } =c^{2}\frac{ \partial^{2}w }{ \partial x^{2} }
$$ a PDE.

## Normal Form
- A first-order differential equation with the form $$
y'=f(t,y)
$$is said to be in **normal form**.
- An equation of order *n* with the form $$
y^{(n)}=f(t,y,y',\dots, y^{(n-1)})
	$$is said to be in **normal form.**
- Any first order equation can be put into the form $\phi(t,y,y')=0$, where $\phi$ is a function of 3 variables.

- The differential equation $t+4yy'=0$ in normal form is $$
y'=-\frac{t}{4y}
$$where $-\frac{t}{4y}=f(t,y)$.

## Solutions to a First-Order ODE
- The **solution** to a first-order ODE $\phi(t,y,y')=0$ is the differentiable function $y(t)$ such that $\phi(t,y(t),y'(t))=0$ for all $t$ in the interval where $y(t)$ is defined.

- Show that $y(t)=Ce^{-t^{2}}$ is a solution of the first-order equation $$
y'=-2ty
$$ where $C$ is an arbitrary real number. By plugging $y(t)$ into $y'$ we obtain $y'(t)=-2tCe^{-t^{2}}$. By plugging in $y(t)$ into $-2ty$ we obtain $-2ty(t)=-2tCe^{-t^{2}}.$ Both sides are equal so the equation is satisfied. Both $y(t)$ and $y'(t)$ are defined on the interval $(-\infty,\infty)$. Therefore, for each real number $C$, $y(t)=Ce^{-t^{2}}$ is a solution on the interval $(-\infty,\infty)$.
- This is the general solution.

## Initial Value Problems