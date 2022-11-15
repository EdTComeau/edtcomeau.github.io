---
layout: post
title: Reading Math
comments: true
---

Math equations can be intimidating. 

$$-\dfrac{\hbar^2}{2m} \dfrac{d^2 \psi(x)}{dx^2} + V(x)\psi(x) = E\psi(x) $$

I have a math background and the above equation still makes my eyes gloss over a bit. I want to try to write a blog post on some quantum mechanics, and like all my posts I want it to be able to be read by anyone! 
The problem is that quantum mechanics cant be described in english, it needs to be described in math. 

I went through an old textbook and attempted to summarize my understnading of some of the equations I came across. This post is my attempt at a summary of the types of equations you may run into in the wild and why they are important.

# How to read Math
First off, we need to be able to recognize different types of math equations.
## Algebraic equations
These are equations we learned in algebra. They are usually organized into one of two categories:
- Linear
- Polynomial

### Linear
These equations can be put in the form:
$$ a_{1}x_{1} + ... + a_{n}x_{n} + b = 0 $$

Which doesn't look like anything I ever saw in algebra class, but lets take this for example:

$$ a_{1}x_{1} + a_{2}x_{2} + b = 0 $$

lets say
- $a_{1}$ = constant m
- $x_{2}$ = a variable other than x, lets call it Y instead
- $a_{2}$ = -1

we get:

$$ mx_{1}-Y+b=0 $$

or

$$ Y = mX+b$$

Soo $Y=mx+b$ is an example of a linear equation. There are other examples, but baically you can add as many variables as you want as long as there are no exponents like $Y=mx^2+b$ then you have a...

### Polynomial
These are simiar to linear equations, although they have variables raised to certain powers (called degrees).
- quadratic is second degree like $Y=mX^2+b$
- cubic is third degree like $Y=mX^3+b$
- quartic is 4
- quintic is 5
- sextic is 6
- septic is 7
- octic is 8

Technically a linear equation is a first order polynomial, but we often seperate these because the method of solving them is very different. 

### Solving algebraic equations
All of these equations represent a mapping between X and Y. If you give us an X-value, we can use an algabraic equation to provide a X value. 

## Differential Equations
Okay we have a handle on algebraic equations, now some calculus. I often turn to physics to intuitively understand these.

Take a car driving in a straight line
- Car A's position = A
- time = t
 
$$ A = 20t $$

At time 0, the position is 0, at time 10 the position is 200. This is a linear equation and it is already solved, every time has an associated distance. 

Now if A = Car A's distance, A' (pronounced "A prime") would be the first derivitive. A derivitive is a change in something. A change in distance is velocity, so a change in A is A', the derivitive of A is A'. This is really important. 

if R = how much rice I have in my house
R' is the derivitive of R, or a change in the amount of rice I have in my house (ie buying rice)

if W = how much water is in my bucket
W' is the derivitive of W and is the flow rate of water into my bucket

So remember our equation for the car:

$$ A = 20t $$

What if instead of telling you one car is twice as far as the other I instead told you one car is moving with a velocity of 20. This is the equation.

$$ A' = 20 $$
Calculus is all about how to "solve" these but Im not going to teach calculus here. The solution the above equation is:

$$ A = 20t + C $$ 

where
- C is a constant value, unknown

This means that $A=20t$ is ONE solution but so is $A=20t+10$. In fact there are infinite solutions! So asking you to "Solve" the derivitive has infinite solutions. What does this mean?!

Lets remove the math, I am asking you "A car is going 20mph, whats its location". Your answer should be... "It depends where the car started". The C value in $A=20t+c$ is the starting location. Almost all the time, when we "solve" a differential equation, our answer will be a set of infinite equations. 

After we solve a differential equation, we often need to "apply boundy conditions" so that we can narrow down the infinite solutions. In the car example, we have infinite solutions, but by saying, _the car starts at a speed of zero_ we are setting a boundry condition and we have one unique solution!

### Ordinary Differential equation
In the above example I am taking a derivitive with respect to time. I am looking at the distance as it changes in time. This is because there is a relationship between A and time A->t. We can have multiple variables, as long as all the variables are being derived with respect to time this is an Ordinary Differential Equation (ODE).

ODE's can be somewhat simple to "solve", but remember that your solution could be an infinite set of equations.

### Partial Differential Equation
ODEs (above) are when you take all your derivitives with respect to the same variable. Partial differential equations are basically a more complicated version of that, where you can the derivitives with respect to OTHER variables. 

To do this we can no longer use the Y' notation. We need to specify what variable we are using to derive. If we are deriving A with respect to time we would say $\dfrac{\partial A}{\partial t} $ which is pronounced "the partial derivitive of A with respect to t".

Solving these are complicated. Sometimes you get lucky and you can seperate the partial derivitives, other times you need to transform your equations into something that has already been solved. 

# Sum
It is important to note that this is the sum symbol:
$$\sum\nolimits_{n=1}^{10}n\$$

It just means to add up the sum from 1 to 10, so 1+2+3...+10.

# Integral
While it is not entirely true, it sometimes is best to think of an integral as the opposite of a derivitive. Integrals look like this:

$$\int^{L}_{0}\psi^{2}dx = 1 $$

Integrals cause ALL the problems with differential equations. Integrals dont necesarrily have one precise answer. They can be hard to solve and they introduce the infinite solutions that are present in all differential equations.

# Vector stuff
I admittedly have a blind spot here.

$$\vec{r} = L_x\hat{x} + L_y\hat{y} + L_z\hat{z}$$

- $\vec{vector}$ Vector lines means you are working with a vector
- $\hat{hat}$ A hat means you have a unit vector on your hands

I recognize I told you what these are defined as but it doesn't help understand them.

I *hate* vector math. I cannot think of a way to describe these without getting into matrices which I am purposefully avoiding. A vector is a line in a certain direction. The degree to what "direction" can often be summarized by a unit vector. 

# Anything else
If you dont recognize a character, its probably literally a greek letter. Some you may recognize like pi $\pi$. 


## Putting it all together
WOW!

Thats a lot we just covered. But you SHOULD now be able to read almost any math equation and kind of understand the goal.

# Quiz
Categorize the following equations:
$$ 2x – 3 = 0 $$
<details>
  <summary>Answer</summary>
  Linear Equation
</details>

$$ ax^2+bx+c=0 $$ 
<details>
  <summary>Answer</summary>
  quadratic polynomial
</details>

$$\dfrac{-\hbar^2}{2m} \dfrac{d^2 \psi(x)}{dx^2} = E \psi(x) $$
<details>
  <summary>Answer</summary>
  Ordinary Differential equation
</details>

$$\dfrac{\hbar^2}{2m} \left (\dfrac{\partial^2 \psi(x,y)}{\partial x^2} + \dfrac{\partial ^2 \psi(x,y)}{\partial y^2} \right) = E \psi(x,y) $$
<details>
  <summary>Answer</summary>
  partial differential equation
</details>




