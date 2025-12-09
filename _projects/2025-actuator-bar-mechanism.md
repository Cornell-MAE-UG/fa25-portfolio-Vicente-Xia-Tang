---
layout: project
title: Rigid-Bar Lifting Mechanism Design
description: Static analysis and mechanism layout for a 1-DOF lifting system within a constrained design space.
technologies: [Mechanism Design, Statics, CAD, Actuators]
image: /assets/images/step1-mech.png
---

## Problem Definition

The design task was to construct a 2D lifting mechanism that fits within a **150 cm × 50 cm** rectangular design space.  
The mechanism must include:

- A **rigid bar** of fixed length  
- **Three pin supports**, with at least two connected to ground  
- A **Tolomatic linear actuator** selected from an online catalog  
- The ability to **lift the maximum possible weight** to the **highest possible height**

For this design, I selected the **Tolomatic IMA55 (roller screw RN05, 3-stack motor)** with a **maximum thrust of ~35.8 kN**.

The objective is to treat the bar as rigid and finalize a mechanism based on static equilibrium analysis.

## Constraints & Objectives

**Geometric constraints**

- Entire mechanism must remain inside a **150 cm (width) × 50 cm (height)** workspace  
- Ground reference line is the lower boundary at *y = 0*  
- Bar length chosen as **L = 50 cm**  
- Actuator ground pin placed at **(35 cm, 0 cm)**  
- Bar base pin placed at **(0 cm, 0 cm)**  
- Bar–actuator joint located at the midpoint of the bar (**25 cm from the base**)

**Objectives**

1. Maximize the **lifted weight**  
2. Achieve the **highest vertical bar tip position**, up to the 50 cm height limit  
3. Use a **1-DOF mechanism** driven only by actuator extension  

## Degrees of Freedom

This mechanism consists of three rigid bodies:

1. The ground  
2. The rigid bar  
3. The actuator (treated as a two-force member)

Pin joints:

- **P1:** Ground ↔ Bar  
- **P2:** Ground ↔ Actuator  
- **P3:** Bar ↔ Actuator (also the load application point)

Because the actuator length is the only independent input, the system has **1 degree of freedom (DOF)**.

## Static Analysis (Rigid-Bar Assumption)

The actuator attaches to the bar at **mid-span**, so the moment arm ratio is:

\[
\frac{a}{L} = \frac{25\ \text{cm}}{50\ \text{cm}} = 0.5
\]

Taking moments about the bar pivot (P1):

\[
F_a \cdot a = W \cdot L
\]

Solving for maximum liftable weight:

\[
W_{\max} = \frac{a}{L} F_a = 0.5 \cdot 35.8\ \text{kN} \approx 17.9\ \text{kN}
\]

This corresponds to a mass of roughly **1.8 metric tons**, assuming no structural deformation.

This geometry was selected because:

- The actuator has a favorable moment arm  
- The bar can fully rotate to reach the 50 cm height limit  
- All supports remain within the design boundaries  

## Final Mechanism (Rigid)

The following CAD-style PNG shows the complete rigid-bar mechanism, including the actuator, load point, and pin locations.

```html
<img src="/assets/images/step-1mech.png" alt="Final Step 1 Mechanism" />
