---
layout: post
title: Physics Hacks - Beyond F=ma
excerpt: Imagine a cart filled with sand. It is moving on a frictionless track under the action of an external force ...
mathjax: true
tags:
  - Physics
  - PhysicsHacks
  - Mechanics
---
Imagine a cart filled with sand. It is moving on a frictionless track under the action of an external force $F_{ext}$.  We can analyze the motion using Newton's second law:
$$
F_{ext} = ma
$$

This approach works well as long as the mass of the cart-sand system remains constant.

Let's now imagine that magically sand is dropped into the moving cart vertically from above at some rate, say $\frac{dm}{dt}$. One may say, we can still use Newton's second law written in terms of momentum $(p = mv)$.

$$
F_{ext} = \frac{dp}{dt} = \frac{d(mv)}{dt} = m\frac{dv}{dt} + v\frac{dm}{dt}$$

Before we move forward, take a moment to reflect on the following scenarios:
- **Scenario 1:** A cart filled with sand moves along a frictionless track at a constant velocity (taking $F_{ext} = 0$ for simplicity). Let's assume, sand is dropped **vertically into the cart from above** at a rate $\frac{dm}{dt}$. What will happen to it's velocity as sand is added to it?

- **Scenario 2:** Now, let's imagine that instead of dropping sand into the cart, we create a hole at the bottom causing sand to **leak straight down the hole**. What will happen to cart's velocity as the amount of sand decreases?

- **Scenario 3:** Now consider a rocket traveling through space. As burned gases are ejected out at high speeds, what happens to the rocket's speed?

We will revisit these at the end of this post.

Let's start with **The Variable-Mass Trap!**

While expanding Newton's second law using the product rule looks mathematically valid, it is **physically invalid** for open systems. Such a formulation violates **[Galilean invariance](https://en.wikipedia.org/wiki/Galilean_invariance)** which states that the basic laws of physics are exactly the same for everyone in all inertial frames of reference. This is because in the above formula, it depends on the absolute velocity $v$ of the system (as $v$ changes based on the reference frame an observer chooses).

How can we address this? Using another foundational concept of physics - **The Impulse-Momentum Theorem**.

The Impulse-Momentum Theorem states that the net external impulse applied to a system over a time interval $\Delta t$ is equal to the total change in momentum of that system:

$$\int F_{ext} \, dt = \Delta p_{system}$$

By tracking a small amount of mass $dm$ entering the system (cart+sand) over time $dt$, we can account precisely for the change in momentum. Let's rewrite the governing equation for any **variable-mass system** (whether mass is increasing or decreasing):

$$
F_{ext} = m \frac{dv}{dt} - v_{rel} \frac{dm}{dt}
$$

Where:
* $F_{ext}$: Net external forces acting on the system
* $m$: Instantaneous mass of the system at that exact moment
* $\frac{dv}{dt}$: Instantaneous acceleration of the system
* $v_{rel}$: Velocity of the entering/leaving mass relative to the main system
* $\frac{dm}{dt}$: Rate of change of mass (positive for entering/accumulation, negative for leaving/leaking)

This is also known as **Meshchersky's Equation** (derived by Russian physicist [Ivan Meshchersky](https://en.wikipedia.org/wiki/Ivan_Vsevolodovich_Meshcherskiy)).

The term **$v_{rel} \frac{dm}{dt}$** is known as the **thrust**; because, as $m$ changes over time, this term can imagined as an additional external force on the system. We can rewrite the equation as:

$$
F_{ext} + F_{thrust} = m \frac{dv}{dt}
$$

Where:

$F_{thrust} = v_{rel} \frac{dm}{dt}$ and its is determined by the combination of two distinct factors - Mass Rate Change ($\frac{dm}{dt}$) and Relative Velocity Vector ($v_{rel}$).

Now, let's go back to our example and look at two scenarios.
 
**Scenario 1: Cart Collecting Sand** 
* **The Setup:** Cart is moving at a constant velocity $v$. Sand is dropped into it **vertically from above** at a rate $\frac{dm}{dt}$. (Mass Increasing, $\frac{dm}{dt} > 0$)

* **Relative Velocity:** Because the sand is dropped vertically, its initial horizontal velocity is zero ($u_{hor} = 0$). Therefore, its velocity relative to the moving cart is:

  $$
  v_{rel} = 0 - v = -v
  $$

* **Applying Meshchersky’s Formula (assuming $F_{ext} = 0$):**
 $$
 0 + (-v)\left(\frac{dm}{dt}\right) = m \frac{dv}{dt} \implies m \frac{dv}{dt} = -v \frac{dm}{dt}
 $$
 
* **Physical Result:** The cart **slows down**. It must constantly expend momentum to accelerate incoming stationary sand up to the cart's speed.

**Scenario 2: A Cart Leaking Sand** 
* **The Setup:** Cart is moving at velocity $v$ and sand leaks straight down through a hole in the bottom.

* **Relative Velocity:** When the sand drops out, at the exact instant of separation, it shares the cart's horizontal velocity ($u = v$). Thus, its horizontal velocity relative to the cart is:
  $$
	v_{rel} = v - v = 0
	$$

* **Applying Meshchersky’s Formula (assuming $F_{\text{ext}} = 0$):**
  $$
	0 + (0)\left(\frac{dm}{dt}\right) = m \frac{dv}{dt} \implies m \frac{dv}{dt} = 0
	$$

* **Physical Result:** The cart's acceleration is zero ($dv/dt = 0$). Despite losing mass, **the cart does not speed up**, because the escaping sand carries away its share of forward momentum ($v$). 

---

**Why Relative Velocity is Everything**

As shown by Meshchersky's formulation, mass change alone does not accelerate a body, **relative velocity does**:
1. **If $v_{rel} = 0$ (leaking straight down):** No reactive force. Mass loss changes nothing dynamically.
2. **If $v_{rel}$ is high and opposite (rocket exhaust):** The $v_{rel} \frac{dm}{dt}$ term becomes a massive forward **thrust**.

---
