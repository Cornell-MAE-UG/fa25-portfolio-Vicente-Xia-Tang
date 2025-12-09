---
layout: project
title: Flexible Beam Design and Deflection Analysis
description: Beam bending analysis to enforce stiffness constraints and select a mass-efficient beam cross-section.
technologies: [Beam Theory, Structural Analysis, CAD, Materials]
image: /assets/images/step2-mech.png
---

## Problem Definition

In Step 2, the rigid bar used in Step 1 is treated as a **flexible beam** subject to bending.  
The goals are to:

1. Compute the **maximum deflection** under transverse loading  
2. Ensure the beam’s vertical tip deflection is **below 2% of its length**  
3. Select a **mass-efficient beam cross-section** meeting stiffness requirements  
4. Present a finalized beam design drawing

The mechanism geometry and actuator locations remain identical to Step 1.

## Assumptions

- Beam length:  
  \[
  L = 0.50\ \text{m}
  \]
- Cantilever configuration: fixed at P1, free at the tip  
- Dominant load is the lifted weight:  
  \[
  P \approx W = 17.9\text{ kN}
  \]
- Material: **Steel**, with  
  \[
  E = 200\ \text{GPa}
  \]
- Maximum allowable deflection:  
  \[
  \delta_{\max} \le 0.01\ \text{m} = 2\%L
  \]
- Euler–Bernoulli beam theory

## Deflection Analysis

For a cantilever with a point load at the free end:

\[
\delta_{\max} = \frac{P L^3}{3 E I}
\]

Solve for required stiffness:

\[
I_{\text{req}} = \frac{P L^3}{3 E \delta_{\max}}
\]

Substituting:

- \(P = 17.9\times10^3\ \text{N}\)
- \(L = 0.50\ \text{m}\)
- \(E = 200\times10^9\ \text{Pa}\)
- \(\delta_{\max} = 0.01\ \text{m}\)

\[
I_{\text{req}} \approx 3.7\times10^{-7}\ \text{m}^4
\]

Any beam design must satisfy **I ≥ I_req**.

## Beam Cross-Section Comparison

### Option 1 — Solid Rectangular Bar  
Meets stiffness but is **heavy** (≈9.4 kg for L = 0.5 m).

### Option 2 — Hollow Rectangular Tube (Selected)

Chosen cross-section:

- **40 mm × 80 mm × 3 mm**
- Steel rectangular tube

Computed stiffness:

\[
I \approx 5.6\times10^{-7}\ \text{m}^4
\]

Deflection prediction:

\[
\delta \approx 6.7\ \text{mm} < 10\ \text{mm}
\]

Beam mass:

\[
m \approx 2.7\ \text{kg}
\]

This is a **3× improvement in mass efficiency** relative to the solid bar.

## Final Step 2 Beam Design

The following diagram shows the mechanism with the flexible beam and selected hollow cross-section:

```html
<img src="/assets/images/step2-mech.png" alt="Final Step 2 Beam Design" />