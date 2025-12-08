---
layout: project
title: RC Car System Modeling
description: RC Car ODE and State-space Analysis
technologies: [Control Systems Modeling]
image: /assets/images/stuntcar.jpg
---


# ODEs, State-Space, and TFs 

![RC Car Motor Dynamics Free Body Diagram]({{ "/assets/images/systemsfbd.png" | relative_url }}){: style="width: 550px"}


- Develops a physics-based model for a small RC car by combining **vehicle longitudinal dynamics** with **DC motor electrical dynamics**.

- Starts from Newton’s 2nd law:
  - With drag, grade, and rolling resistance neglected on flat ground,

    $$
    M_{eq}\,\dot{v} = F_t
    $$

  - Equivalent mass:

    $$
    M_{eq} = \frac{J_w + mr^2 + i_g^2 J_e}{r^2}
    $$


- Uses the **no-slip condition** (\(\omega = v/r\)) and wheel torque balance to relate motor torque to traction force at the tires.
- Models the DC motor with:
  - Electrical: \(L\frac{di}{dt} + Ri = V - K_e\omega\)
  - Torque: \(T_e = K_t i\)
  - Mechanical rotation with inertia and damping.
- Chooses states and input:
  - \(x_1 = i\) (motor current)
  - \(x_2 = v\) (vehicle speed)
  - \(u = V\) (applied motor voltage)
- Builds the **state-space model**:
  - \(\dot{x}_1 = \frac{u}{L} - \frac{R}{L}x_1 - \frac{K_e}{Lr}x_2\)
  - \(\dot{x}_2 = \frac{i_g K_t}{M_{eq} r} x_1\)
- Uses Laplace transforms to derive a **transfer function** from input voltage to vehicle speed by combining the electrical and mechanical subsystems and applying a published approximation.

---

[Open full PDF: *RC Car ODE and State-space Analysis*]({{ "/assets/RC Car ODE and State-space Analysis.pdf" | relative_url }})