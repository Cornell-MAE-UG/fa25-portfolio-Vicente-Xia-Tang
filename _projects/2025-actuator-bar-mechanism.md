---
layout: project
title: Rigid-Bar Lifting Mechanism Design
description: Static equilibrium–based mechanism design for lifting within a constrained 150 cm × 50 cm workspace.
technologies: [Mechanism Design, Statics, CAD, Actuators]
image: /assets/images/step1-mech.png
---

## Problem Definition

The objective for Step 1 is to design a 2D lifting mechanism inside a **150 cm × 50 cm** design space using:

- A **rigid bar** of fixed length
- **Three pin supports**, two of which must be grounded
- A **linear actuator** chosen from the Tolomatic online catalog (using only maximum force values)
- Rigid supports and rigid actuator assumptions

The goal is to **lift the maximum possible weight** to the **highest reachable height** within the vertical constraint.

For this design, I selected the **Tolomatic IMA55 (roller screw RN05, 3-stack motor)**, which provides a **maximum thrust of ~35.8 kN**.

---

## Constraints & Objectives

**Geometric Constraints**

- Workspace: 150 cm (width) × 50 cm (height)
- Bar length chosen as **L = 50 cm**
- Ground pins placed at:
  - P1 = (0 cm, 0 cm)
  - P2 = (35 cm, 0 cm)
- Actuator-to-bar joint (P3) positioned at the **midpoint** of the bar (25 cm from P1)

**Objectives**

1. Maximize the lifted load capacity  
2. Achieve the maximum vertical elevation of the bar tip  
3. Maintain a **single-degree-of-freedom** mechanism driven by actuator extension  

---

## Degrees of Freedom

The system consists of:

- A rigid body (bar)
- A two-force actuator
- Ground

Three pin joints:

- **P1:** Ground ↔ Bar  
- **P2:** Ground ↔ Actuator  
- **P3:** Bar ↔ Actuator  

Since the actuator length is the only independent variable, the mechanism has **1 DOF**.

---

## Static Analysis (Rigid-Bar Assumption)

The actuator applies force at mid-span:

\[
\frac{a}{L} = \frac{25\ \text{cm}}{50\ \text{cm}} = 0.5
\]

Taking moments about the pivot P1:

\[
F_a \cdot a = W \cdot L
\]

Solving for the maximum supported load:

\[
W_{\max} = \frac{a}{L} F_a = 0.5 \cdot 35.8\text{ kN}
\]

\[
W_{\max} \approx 17.9\ \text{kN}
\]

This corresponds to lifting approximately **1.8 metric tons**, assuming the bar is perfectly rigid.

---

## Final Mechanism Design

Below is the final CAD-style schematic used for Step 1:

```html
<img src="/assets/images/step1-mech.png" alt="Final Step 1 Mechanism" />
