---
layout: post
title: "Transient Structural Analysis: 680mm Performance Rim"
date: 2026-04-18
description: "A self-directed study on high-speed rotation cycles (0-1500-800 RPM) to validate structural integrity."
image: assets/images/wheel_stress.jpg
---

### The Motivation
This project was born out of a personal interest in understanding how transient loads affect automotive components. While static analysis provides a baseline, I wanted to simulate the actual "ramp-up" and "ramp-down" phases of a wheel's rotation to observe the material's response over time.

### The Physics of the Duty Cycle
The simulation targets a peak angular velocity of **1500 RPM** followed by a deceleration to **800 RPM**. The internal centrifugal stress scales quadratically with angular velocity:

$$\sigma_{centrifugal} \approx k \cdot \omega^2$$

### Methodology & Setup
* **Software:** Ansys Mechanical 2025 R2 Student
* **Material:** Aluminum 6061-T6 ($S_y = 276 \text{ MPa}$)
* **Mesh:** Tetrahedral with local refinement at the spoke-rim junctions.
* **Loading:** Rotational Velocity ramped over a 2.0s time step.

### Simulation Results
The analysis showed that the most critical stress concentrations occur at the root of the spokes.

| Parameter | Value |
| :--- | :--- |
| **Peak Equivalent (Von-Mises) Stress** | 55.37 MPa |
| **Total Directional Deformation** | 15.8 $\mu$m |
| **Calculated Safety Factor (FOS)** | 8.18 |

![Equivalent Stress Map](/assets/images/wheel_stress.jpg)

### Technical Takeaway
A Safety Factor of **8.18** suggests that while the design is exceptionally safe for pure rotation, there is significant room for **lightweighting**. I’m currently looking into how I can use **nTop** or generative design to shave mass from the spokes while maintaining the required stiffness for lateral cornering loads.

---
*Note: This is a personal research project conducted to deepen my understanding of transient FEA workflows.*
