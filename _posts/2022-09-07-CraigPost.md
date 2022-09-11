---
layout: post
title: Atoms
---

The goal of this post is to take someone from no understanding of quantum chemistry to kind of understanding the structure of an atom.

# The atom model is more complex than you probably think

Imagine an atom...

Did you think of something like this:
![Atom](\images\Parts-of-an-Atom-Diagram.jpg)

Thats probably how you were taught, but the reality is the atom is so much cooler! 
We will have to dive into a lot of physics/chemistry to unveil its secrets.

# 1 The wave equation

We will be investigating the nature of electrons, but first you must understand the wavelike nature of an electron. 

If we shoot electrons through a piece of paper with two slits like this:
![DoubleSlit](\images\Double-slit.svg.png)

The piece of paper behind looks like this:
![DoubleSlitResult](\images\250px-Young's_slits.jpg)

If electrons were particles, they wouldn't look like this. There would be two clumps. The pattern you see here is the results of wave-like interference. Because of this experiment (and many others) we can assume small particles also act like waves.

What do I mean by waves?
![wave](\images\1DWave.gif)

I mean a wave equation, the particle doesn't actually LOOK like a wave. This is a generalized wave equation:

$$ \dfrac{\partial^2 u(x,t)}{\partial x^2} = \dfrac{1}{v^2} \dfrac{\partial^2 u(x,t)}{\partial t^2} $$

with u is the amplitude of the wave at position x and time t, and v is the velocity of the wave. This is a linear partial differential equation, and generally when we "solve" these we will be trying to define the u(x,t).

For example:
One end of a string is held still: $ u(0,t)=0 $
The other end of the string (length L) is held still: $ u(L,t)=0 $

There are still infinite solutions to the linear partial differential equation, but we can narrow it down a lot better now. 

![solutions](\images\Standing_waves_on_a_string.gif)
Here are six solutions. Later we will touch upon how to solve these. 
Notice that every solution has one more node than its successor. 

# 2 Lets quickly derive the schrodenger equation

Remember the equation for a wave:

$$ \dfrac{\partial^2 u(x,t)}{\partial x^2} = \dfrac{1}{v^2} \dfrac{\partial^2 u(x,t)}{\partial t^2} $$

Let's swap out the velocity of a wave for the light speed constant and the nasty doubel derivitive with the Laplacian 

$$ \nabla^2 \Psi(x,y,z,t) -\dfrac{1}{c^2}\dfrac{\partial ^2 \Psi(x,y,z,t) }{\partial t^2}=0 $$

This is all okay to do because Maxwells Equation's (Equations that define how energy works) allow us to simulate a particle with a 3-D wave. 
This is the first hand-wavy part of this description. You may need to trust me that particles can be described as waves here. 

So this has four dimensions, x,y,z,t (time). It helps to think of it in one dimension, lets say x...
$ \Psi(x)=f\left(\dfrac {2\pi x}{ \lambda}\right) $





SO maybe you have heard that an electron is a particle and a wave? So contemporary phyiscs assumes things are particles, if we want to get into the very small (quantum) world we must look at the wave-like nature of a particle. 

