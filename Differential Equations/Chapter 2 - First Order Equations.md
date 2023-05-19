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
- We want to determine the value of constants and specify the solution completely. This is called the **particular solution**.

- Given that $y(t)=-\frac{1}{t-C}$ is a general solution of $y'=y^2$, find the particular solution satisfying $y(0)=1$.
- Because $$\begin{aligned}
1=y(0)&=\frac{-1}{0-C}=\frac{1}{C} \\ \\
C&=1
\end{aligned}
$$Substituting $C=1$ into $y(t)$, we obtain $$
y(t)=-\frac{1}{t-1}
$$ a particular solution of $y'=y^{2}$, satisfying $y(0)=1$.

- A first-order differential equation with the initial condition $$y'=f(t,y),\quad y(t_{0})=y_{0}$$is called an **initial value problem**. A solution of the IVP is a differentiable function $y(t)$ such that
	1. $y'(t)=f(t,y(t))$ for all $t$ in an interval containing $t_{0}$ where $y(t)$ is defined.
	2. $y(t_{0}) = y_{0}$

## Interval of Existence
- The **interval of existence** of a solution is the largest interval where the solution can be defined.

- The interval of existence of $y'=y^{2}$ with initial value $y(0)=1$ with the solution $y(t)=\frac{-1}{t-1}$ is undefined at $t=1$.
	- Thus, the function is not fully defined over the entire real number line. Therefore, the largest interval where the solution curve $y(t)$ is defined is the interval $(-\infty,1)$.

# 2.2 Solutions to Separable Equations

# 2.3 Models of Motion

# 2.4 Linear Equations
## First order linear equations
## Solution of the homoegenous equation
## Solution of the inhomogenous equation
## General method of solving linear equations
# 2.5 Mixing Problems

# 2.6 Exact Differential Equations

# 2.7 Existence and Uniqueness of Solutions

# 2.8 Dependence of Solutions on Initial Conditions

# 2.9 Autonomous Equations and Stability
