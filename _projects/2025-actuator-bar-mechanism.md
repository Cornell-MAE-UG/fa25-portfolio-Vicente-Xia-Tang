---
layout: project
title: Lifting Mechanism Design
description: A complete lifting mechanism design beginning with rigid-body statics and concluding with flexible-beam structural optimization.
technologies: [Mechanism Design, Statics, Structural Analysis, Beam Theory, Materials, CAD]
image: /assets/images/step1-mech.png
---

# Overview

This project develops a 2D lifting mechanism that must operate within a **150 cm × 50 cm** design envelope.  
The mechanism uses:

- One bar (initially treated as rigid)
- Three pin joints, two attached to ground
- A Tolomatic linear actuator (IMA55 series)
- Rigid joints and ideal actuator behavior  

The design progresses in two stages:

1. **Rigid-body static analysis** to determine optimal geometry and theoretical lifting capacity.  
2. **Flexible-beam analysis** to account for deformation, compute stiffness requirements, and select an efficient structural cross-section.

Both steps are integrated into one continuous mechanism design.

---

# Step 1 — Rigid-Bar Mechanism Design

## Problem Definition

The objective is to lift the **maximum possible weight** to the **greatest achievable height** within a 50 cm vertical constraint. The mechanism geometry is defined as follows:

- Bar length: **50 cm**  
- Ground pin locations:
  - **P1 = (0 cm, 0 cm)**
  - **P2 = (35 cm, 0 cm)**
- Actuator–bar joint:
  - **P3 = midpoint of the bar (25 cm from P1)**  
- Selected actuator: **Tolomatic IMA55**, maximum thrust approx. **35.8 kN**

This configuration provides high leverage and allows the bar tip to sweep the full height limit.

---

## Degrees of Freedom

The system contains three rigid bodies:

- Ground  
- A rigid bar  
- A two-force actuator  

Pin joints:

- P1: bar ↔ ground  
- P2: actuator ↔ ground  
- P3: actuator ↔ bar  

Since the actuator length is the only independently controlled variable, the mechanism has **1 degree of freedom**.

---

## Static Analysis (Rigid-Bar Assumption)

Key distances:

- Distance from P1 to actuator joint (P3): **a = 25 cm**  
- Distance from P1 to bar tip: **L = 50 cm**

Ratio:

- a / L = 25 / 50 = **0.5**

Moments about the pivot P1:

- Actuator moment = (actuator force) × a  
- Load moment = (lifted weight) × L  

Equilibrium requires:

- actuator force × a = W × L  

Solving for the maximum load:

- W_max = (a / L) × actuator force  
- W_max = 0.5 × 35.8 kN  
- **W_max ≈ 17.9 kN**

This corresponds to lifting roughly **1.8 metric tons** under ideal rigid-bar behavior.

---

## Final Rigid Mechanism (Step 1)

![Rigid-Bar Mechanism](/assets/images/step1-mech.png)

This establishes the geometry used in Step 2.

---

# Step 2 — Flexible Beam Structural Analysis

The bar now behaves as a **beam that deflects under load**, requiring a structural analysis to ensure it meets a 2% deflection limit.

## Assumptions

- Beam length: **0.50 m**
- Transverse load: **≈ 17.9 kN**  
- Material: **Steel**
- Young’s modulus: **200 GPa**
- Max allowable tip deflection: **0.01 m (2% of beam length)**
- Beam acts as a cantilever: fixed at P1, free at tip
- Euler–Bernoulli small-deflection theory applies

---

## Deflection Analysis

For a cantilever with a point load at the free end:

- max deflection = (load × L³) ÷ (3 × E × I)

Rearranged for required stiffness:

- I_required = (load × L³) ÷ (3 × E × allowable deflection)

Using:

- load = 17.9 × 10³ N  
- L = 0.50 m  
- E = 200 × 10⁹ Pa  
- allowable deflection = 0.01 m  

Results in:

- **I_required ≈ 3.7 × 10⁻⁷ m⁴**

Any selected beam cross-section must exceed this value.

---

## Cross-Section Selection

### Solid Rectangular Bar (Rejected)

A solid bar can meet stiffness but becomes **too heavy** (approx. 9.4 kg for a 0.5 m length).

---

### Hollow Rectangular Tube (Selected)

Final chosen cross-section:

- Outer dimensions: **40 mm × 80 mm**
- Wall thickness: **3 mm**
- Material: steel

Properties of this tube:

- Second moment of area: **≈ 5.6 × 10⁻⁷ m⁴**  
- Predicted tip deflection: **≈ 6.7 mm** (< 10 mm limit)  
- Mass of 0.5 m beam: **≈ 2.7 kg**

This design is over **three times lighter** than a comparable solid bar while satisfying stiffness constraints.

---

## Final Flexible Beam Design (Step 2)

![Flexible Beam Mechanism](/assets/images/step2-mech.png)

---

# Integrated Summary

This project combines rigid-body mechanism design with structural beam analysis:

- Step 1 establishes an ideal mechanism capable of lifting **17.9 kN** using an IMA55 actuator and optimal geometry.
- Step 2 ensures the bar is realistically modeled as a deformable beam, selects a **40 × 80 × 3 mm steel tube**, and verifies deflection remains under **2% of beam length**.
- The final design is:
  - Structurally efficient  
  - Mass-optimized  
  - Capable of supporting the required load  
  - Consistent with practical engineering design principles  

This unified process produces a mechanically functional and physically feasible lifting mechanism.
