# 1.1 Differential Equation Models
- Two ways to compute the rate of change of variables.
	- Mathematical way; finding the derivative
	- Second way; comes from the application itself and differs in each example.
- The differential equation is the expression of these two methods.

## Mechanics
- Newton's Second law: The force acting on a mass is equal to the rate of change of momentum w.r.t. time. $$\frac{d}{dt}mv=m \frac{dv}{dt} = ma.$$
	- $mv$ is the momentum, mass times velocity, and $a$ is the acceleration.
- The rate of change of momentum is equal to $F$, the force. $$ F=ma
$$
- Universal Law of Gravitation $$
\frac{GMm}{r^{2}}
$$
- Velocity and Acceleration of an object $$
v=\frac{dx}{dt}\quad\text{and}\quad a=\frac{dv}{dt}=\frac{d^{2}x}{dt^{2}}
$$
	- Force of a ball falling towards the earth with mass $m$:$$\begin{aligned}
-mg=ma=m \frac{dv}{dt}&=m \frac{d^{2}x}{dt^{2}} \\
\frac{d^{2}x}{dt^{2}} &= -g
\end{aligned}
$$
	- This is a differential equation of the second order, since the highest derivative is in the 2nd order.

## Population Models
- The rate at which the population changes w.r.t. time is given by $$
\frac{dP}{dt}
$$
- We can also say that the rate of change is proportional to the population. We get the equation $$
\frac{dP}{dt}=rP
$$where $r$ is the reproductive rate.
- A solution would be $P(t)=P_{0}e^{rt}$ where $P_{0}$ is the initial population.
- However, $r$ is not a constant so because food and space are limited
	- $r$ can then be modeled by $r\left( 1-\frac{P}{K} \right)$ where $K$ is also a constant
	- rewrite differential equation to $$
\frac{dP}{dt}=r\left( 1-\frac{P}{K} \right)P
$$

## 1.1 Exercises
1. $P'(t)=kP(t),$ where $P$ is the population of bacteria in the dish, $k$ is a constant, and $P'(t)$ is the rate of growth of the bacteria.
2. $P'(t)=\frac{k}{\sqrt{ P(t) }}$
3. $P'(t)=kP(t)(100-P(t))$
4. $y'(t)=ky(t)$
5. $y'(t)=-\frac{k}{y(t)}$
6. $y'(t)=k(y(t)-65)$
7. $y'(t)=k(77-y(t))$
8. $x'(t)=-kx(t)$
9. $-k(x'(t))|x'(t)| = mx''(t)$

# 1.2 The Derivative
- Derivatives are:
	- Rate of Change
	- Slope of the tangent line at a given point
	- Best linear approx of the function
	- Limit of difference quotients $$
f'(x_{0})=\lim_{ x \to x_{0} } \frac{f(x)-f(x_{0})}{x-x_{0}}
$$
	- Also a bunch of formulas and shit

## Rate of Change
- Derivatives are the instantaneous rate of change of a function.
- In physics, the derivative of a distance $x(t)$ is $v=x'=\frac{dx}{dt}$ where $v$ is the rate at which $x$ changes w.r.t. time.
	- $a=v'=\frac{dv}{dt}=\frac{d^{2}x}{dt^{2}}$ is the acceleration, which is the rate of change of the velocity.
- In economics, the rate of change of the price of a product w.r.t. the supply is given by $P' = \frac{dP}{dS}$. $P'$ is the marginal price, given that the demand of the product is constant.
- Modeling Definition of the Derivative

## Slope of the Tangent Line
- $y=f(x_{0})+f'(x_{0})(x-x_{0})$ is the equation of the tangent line of a function $f$ at the point $(x_{0},f(x_{0}))$![[Pasted image 20230513235109.png]]
- The derivative is the slope of the line, $f'(x_{0})$
- Geometric Definition of the Derivative

## Best Linear Approximation
- Let $L(x) = f(x_{0})+f'(x_{0})(x-x_{0})$ where $L$ is a linear function of $x$. By Taylor's Theorem, there is a remainder function $R(x)$ such that $$
f(x)=L(x)+R(x)\quad\text{and}\quad \lim_{ x \to x_{0} } \frac{R(x)}{x-x_{0}}=0.
$$
- $L$ is also the same line as the tangent line of the function.
- This approximation is algebraic
- Algebraic Definition of the Derivative

## The Limit of Difference Quotients
- Consider $m$, the difference quotient $$
m=\frac{f(x)-f(x_{0})}{x-x_{0}}
$$
- $m$ is the slope between two points. As $x$ approaches $x_{0}$, the line generated by $m$ approaches the tangent line.
- $f'(x_{0})=\lim_{ x \to x_{0} } \frac{f(x)-f(x_{0})}{x-x_{0}}$ is the slope of the tangent line, and the limit of the secant line $m$.
- This definition is the most common when used to define the derivative.
- Limit Quotient Definition of the Derivative.

## 1.2 Exercises


# 1.3 Integration