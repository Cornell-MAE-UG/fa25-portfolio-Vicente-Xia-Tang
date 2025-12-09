---
layout: project
title: Bar Lifting Mechanism Design
description: Static equilibrium–based mechanism design for lifting within a constrained 150 cm × 50 cm workspace.
technologies: [Mechanism Design, Statics, CAD, Actuators]
image: /assets/images/step1-mech.png
---

## Problem Definition

The objective for Step 1 is to design a 2D lifting mechanism inside a **150 cm × 50 cm** design space using:

- A rigid bar of fixed length
- Three pin supports, two of which must be grounded
- A linear actuator chosen from the Tolomatic online catalog (using only maximum force values)
- Rigid supports and rigid actuator assumptions

The goal is to lift the **maximum possible weight** to the **highest reachable height** within the vertical constraint.

For this design, I selected the **Tolomatic IMA55 (roller screw RN05, 3-stack motor)**, which provides a **maximum thrust of about 35.8 kN**.

## Constraints & Objectives

**Geometric constraints**

- Workspace: 150 cm (width) × 50 cm (height)
- Bar length: **L = 50 cm**
- Ground pins:
  - P1 = (0 cm, 0 cm)
  - P2 = (35 cm, 0 cm)
- Actuator–bar joint: P3 at the midpoint of the bar (25 cm from P1)

**Objectives**

1. Maximize lifted load capacity  
2. Reach the maximum feasible vertical elevation of the bar tip  
3. Maintain a **single degree of freedom** driven by actuator extension  

## Degrees of Freedom

The system consists of:

- The ground
- One rigid bar
- One two-force actuator

Pin joints:

- P1: ground ↔ bar  
- P2: ground ↔ actuator  
- P3: bar ↔ actuator  

Because the actuator length is the only independent input, the mechanism has **1 DOF**.

## Static Analysis (Rigid-Bar Assumption)

The actuator applies force at mid-span of the bar.

Ratio of the lever arms:

- \( a = 25\ \text{cm} \) (distance from P1 to P3)  
- \( L = 50\ \text{cm} \) (distance from P1 to bar tip)  
- So: **a / L = 25 / 50 = 0.5**

Taking moments about the pivot P1:

- Actuator moment: \( F_a \times a \)  
- Load moment: \( W \times L \)

Static equilibrium gives:

- \( F_a \times a = W \times L \)

So the maximum supported load is

- \( W_{\max} = (a / L) \times F_a = 0.5 \times 35.8\ \text{kN} \)
- **\( W_{\max} \approx 17.9\ \text{kN} \)**

This corresponds to lifting approximately **1.8 metric tons**, assuming the bar is perfectly rigid.

## Final Mechanism Design

Below is the final schematic used for Step 1:
<img src="/assets/images/step1-mech.png" alt="Final Step 1 Mechanism" />

Now,let's consider when the bar **ISN'T** rigid:

## Problem Definition

In Step 2, the rigid bar from Step 1 is treated as a **flexible beam** that bends under load.  
The goals are to:

1. Compute the maximum deflection under transverse loading  
2. Ensure the beam’s vertical tip deflection is **below 2% of its length**  
3. Select a **mass-efficient beam cross-section** that meets this stiffness requirement  
4. Present a finalized beam design drawing

The mechanism geometry (pin locations and actuator position) is kept the same as in Step 1.

## Assumptions

- Beam length: **L = 0.50 m**
- Cantilever configuration: fixed at P1, free at the tip  
- Dominant transverse load is the lifted weight: **P ≈ W = 17.9 kN**  
- Material: **steel**, with elastic modulus **E = 200 GPa**  
- Maximum allowable deflection at the tip: **δ_max ≤ 0.01 m (2% of L)**  
- Small-deflection Euler–Bernoulli beam theory

## Deflection Analysis

For a cantilever beam with a point load P at the free end, the maximum tip deflection is

- **δ_max = (P · L³) / (3 · E · I)**

where:

- \( P \) = transverse load  
- \( L \) = beam length  
- \( E \) = Young’s modulus  
- \( I \) = second moment of area about the bending axis  

Solving for the required second moment of area:

- **I_req = (P · L³) / (3 · E · δ_max)**

Using:

- \( P = 17.9 \times 10^3\ \text{N} \)  
- \( L = 0.50\ \text{m} \)  
- \( E = 200 \times 10^9\ \text{Pa} \)  
- \( \delta_{\max} = 0.01\ \text{m} \)

gives:

- **I_req ≈ 3.7 × 10⁻⁷ m⁴**

Any beam design must have **I ≥ I_req**.

## Beam Cross-Section Comparison

### Option 1 – Solid Rectangular Bar (Not Selected)

A solid bar sized to satisfy \( I \ge I_{\text{req}} \) can meet the stiffness requirement but is heavy  
(roughly **9.4 kg** for a 0.5 m bar in a reasonable size range).

### Option 2 – Hollow Rectangular Tube (Selected)

Final choice:

- Outer dimensions: **40 mm × 80 mm**  
- Wall thickness: **3 mm**  
- Material: **steel**

This produces:

- Second moment of area: **I ≈ 5.6 × 10⁻⁷ m⁴** (greater than I_req)  
- Predicted tip deflection:

  - **δ ≈ 6.7 mm**, which is less than **10 mm** (2% of L)

- Cross-sectional area: about **6.84 × 10⁻⁴ m²**  
- Mass per meter: ≈ **5.4 kg/m**  
- Mass of the 0.5 m beam: ≈ **2.7 kg**

So the hollow tube is more than **three times lighter** than a solid bar that meets the same stiffness requirement.

## Final Step 2 Beam Design

The figure below shows the final mechanism with the flexible beam and selected rectangular tube cross-section.

<img src="/assets/images/step2-mech.png" alt="Final Step 2 Beam Design" />