---
layout: post
title: Physics Hacks - The Principle of Virtual Work
excerpt: When we are introduced to mechanics in school, there is a standard drill for solving mechanics problems ...
mathjax: true
tags:
  - Physics
  - PhysicsHacks
  - Mechanics
---
When we are introduced to mechanics in school, there is a standard drill for solving mechanics problems:
- Draw free body diagrams
- Identify all the forces acting on the system
- Take components of these forces in x and y directions (as mostly the problems are 2D)
- Calculate the net force in each direction
- Write equations using the Newton’s Laws
- Write additional equations for constraints
- Solve the system of equations

This is perfectly fine as long as the systems that we are analyzing are simple. However, it becomes a nightmare when a system has multiple internal constraint forces, constantly changing external forces (both in direction and magnitude), etc. Too many variables, and as many equations to solve. 

We can avoid this complexity by using a simple physics hack - **virtual work**. This hack eliminates many forces (thus many variables and equations) from the analysis. Instead of writing force equations in every dimension, we analyze the system using work and energy concepts.

Let's explore the virtual work approach.

Imagine a simple pendulum swinging along its path. Now, freeze the motion at some instant. At this instant, imagine displacing the bob slightly ($δr$). One important thing to ensure is that virtual displacement (an imaginary shift) shouldn't change any of the physical constraints. In this case, the distance of the bob from the pivot point should stay the same as the string is assumed to be inextensible. So the virtual displacement ($δr$) we imagined must be perpendicular to the string. In reality, there is no physical displacement at this instant, it is just a mathematical construct.

The work done by a force ($F_i$) during this *virtual displacement* is called **virtual work** ($δW_i$). 
$$\delta W_i = \mathbf{F}_{i} \cdot \delta \mathbf{r}_{i}$$

For a system in **static equilibrium**, as we can imagine, the total virtual work done by all forces must be zero.
$$\delta W = \sum_i \mathbf{F}_{i} \cdot \delta \mathbf{r}_{i} = 0$$

In any mechanical system, we can categorize forces into two types:
*   **Applied Forces:** Gravity, external pushing/pulling, etc. ($\mathbf{F}_{app}$).
*   **Constraint Forces:** Tension in strings, normal forces from smooth surfaces, hinges ($\mathbf{F}_c$).

So we can write the total virtual work on the system as the sum of the work done by both types of forces across all particles $i$:

$$\delta W = \sum_i (\mathbf{F}_{app, i} \cdot \delta \mathbf{r}_i) + \sum_i (\mathbf{F}_{c, i} \cdot \delta \mathbf{r}_i) = 0$$

Turning back to our example, the tension in the string is a constraint force. The tension doesn't do any virtual work as the virtual displacement ($δr$) is perpendicular to the tension (we chose it to be so). Here, we are assuming that all the constraint forces are *ideal*. 

More generally, ideal constraint forces do not contribute to the total virtual work. Sometimes this is because each constraint force is perpendicular to the corresponding virtual displacement (as in the pendulum), while in some systems the virtual work of the constraint forces cancels out when the contributions from all parts of the system are added.

One might say, this is fine when the system is at a static equilibrium. But what about when it's dynamic? In fact, the simple pendulum we considered is not exactly in static equilibrium - the pendulum is moving. This is where the [D'Alembert's principle](https://en.wikipedia.org/wiki/D%27Alembert%27s_principle) comes into picture. This principle extends the principle of virtual work to dynamic systems by introducing an inertial force.

For dynamic systems, the total virtual work of the applied forces together with these inertial forces is then zero:
$$ \delta W = \sum_i \left( \mathbf{F}_{app, i} - \left( m_i \ddot{\mathbf{r}}_i + \dot{m}_i \dot{\mathbf{r}_i} \right) \right) \cdot \delta \mathbf{r}_i + \sum_i (\mathbf{F}_{c, i} \cdot \delta \mathbf{r}_i) = 0 $$

Assuming we eliminate the contribution of work done by Constrained Forces, and assuming a system where mass does not change with time, it becomes:
$$ \delta W = \sum_i \left( \mathbf{F}_{app, i} - m_i \ddot{\mathbf{r}_i} \right) \cdot \delta \mathbf{r}_i = 0 $$

The beauty of this trick lies in the fact that we can eliminate many variables and equations while analyzing the complex and dynamic systems. No internal forces, no balancing vectors, no massive systems of equations. By simply describing the geometry and taking simple derivatives, Virtual Work bypasses the constraints entirely and delivers the solution in easy steps.

This might look like a simple trick, but it has much wider applications. The analysis of a system using the Lagrangian and the idea of *action* are both connected to this concept. And these ideas explain why nature chooses the paths it takes.

---
