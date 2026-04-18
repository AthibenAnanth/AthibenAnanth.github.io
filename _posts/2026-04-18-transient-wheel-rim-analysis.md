---
layout: post
title: "Transient Structural Analysis: 680mm Performance Rim"
date: 2026-04-18
permalink: /wheel-analysis/
description: "A self-directed study on high-speed rotation cycles (0-1500-800 RPM) to validate structural integrity and fatigue life."
image: assets/images/wheel_stress.jpg
---

### The Motivation
This project was born out of a personal curiosity about material limits during dynamic load changes. While my university coursework focuses on static equilibrium, I wanted to simulate the real-world "ramp-up" and "ramp-down" phases of a wheel's rotation to observe how inertial effects influence the stress-time history of Aluminum 6061-T6.

### The Physics of the Cycle
The simulation covers a 2.0s transient window. The centrifugal stress $\sigma$ is governed by the angular velocity $\omega$:

$$\sigma \approx \rho \cdot r^2 \cdot \omega^2$$

To ensure accuracy in a transient environment, the solver integrates the fundamental equation of motion:

$$[M]\{\ddot{u}\} + [C]\{\dot{u}\} + [K]\{u\} = \{F(t)\}$$

### Methodology & Mesh Validation
* **Mesh Quality:** Using the **Mesh Metric** tool, I verified that the average **Skewness** was **0.22**, with zero elements exceeding the 0.9 failure threshold. This ensures the gradients at the fillets are numerically stable.
* **Stress Probing:** Rather than just looking at global maximums, I placed a **Stress Probe** at the high-stress spoke-root interface to capture the exact stress-time history throughout the 1500 RPM cycle.

### Key Data & Results

| Parameter | Result | Engineering Note |
| :--- | :--- | :--- |
| **Peak Von-Mises Stress** | 55.37 MPa | Occurred at the 1.0s peak velocity. |
| **Total Deformation** | 15.8 $\mu$m | Global radial expansion of the rim bed. |
| **Fatigue Life (Cycles)** | $> 1 \times 10^8$ | Estimated using the Ansys Fatigue Tool (S-N Curve). |
| **Safety Factor (Yield)** | 8.18 | Based on $S_y = 276 \text{ MPa}$ for Al 6061-T6. |

### Conclusion: Data Interpretation
The **Total Deformation** of 15.8 $\mu$m is negligible, confirming the rim retains its geometric intent under centrifugal load. However, the **Stress Probe** data reveals that the stress follows the $\omega^2$ curve almost perfectly, with no significant lagging from damping ($[C]$). 

With a fatigue life exceeding $10^8$ cycles at 55 MPa, the component is effectively in the "infinite life" regime for this load case. This suggests that the current design is **conservative**; we could reduce the spoke thickness by 20% to lower unsprung mass while still maintaining a safe margin for lateral cornering impacts.

### Personal Reflection: What I Learnt
Building this project outside of my EIM class taught me three critical things:
1. **The Solver is a Tool:** I initially had a mesh that was too coarse, leading to "stress singularities." Learning to use Mesh Metrics like Skewness taught me to question the computer's output.
2. **Time-Stepping Matters:** In my first run, I used too few sub-steps, and the results didn't capture the peak stress correctly. I learnt that transient analysis requires a balance between computational cost and temporal resolution.
3. **The Engineering Mindset:** Designing for "static" strength isn't enough for high-performance automotive parts. Moving from yield analysis to **Fatigue Life** estimation changed how I look at material selection.

---
*Note: This simulation is a personal project focusing on FEA workflows.*
