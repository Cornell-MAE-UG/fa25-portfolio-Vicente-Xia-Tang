---
layout: project
title: Flexible Beam Design and Deflection Analysis
description: Beam bending analysis, stiffness design, and mass-efficient cross-section selection.
technologies: [Beam Theory, Mechanics of Materials, CAD, Structural Analysis]
image: /assets/images/step2-mech.png
---

## Problem Definition

In Step 2, the rigid bar from Step 1 is replaced with a **flexible beam** that bends under load. The mechanism geometry, support locations, and actuator placement remain the same, but the bar can no longer be treated as rigid.

The objective is to:

1. Compute the **maximum deflection** of the beam under transverse loads  
2. Design the beam cross-section such that the **vertical tip deflection is less than 2% of its length**  
3. Produce a **mass-efficient** beam that fits the originally selected mechanism  
4. Present a revised CAD-style drawing of the final beam design

## Assumptions for Beam Analysis

To perform a clean and conservative deflection analysis, I used these engineering assumptions:

- The bar behaves as a **cantilever beam**:
  - Fixed at the bottom pin (P1)  
  - Free at the tip, where the load acts
- Beam length:  
  \[
  L = 0.50\ \text{m}
  \]
- The load acting transversely on the beam is dominated by the lifted weight:
  \[
  P \approx W = 17.9\ \text{kN}
  \]
- Actuator transverse contributions are small compared to W and conservatively absorbed into \(P\)
- Material: **structural steel**:
  \[
  E = 200\ \text{GPa}
  \]
- Small-deflection Euler–Bernoulli beam theory
- Maximum allowed deflection:
  \[
  \delta_{\max} \le 0.02L = 0.01\ \text{m}
  \]

## Maximum Deflection Analysis

For a cantilever beam with a point load at the tip:

\[
\delta_{\max} = \frac{P L^3}{3EI}
\]

Solving for the required second moment of area:

\[
I_{\text{req}} = \frac{P L^3}{3 E \delta_{\max}}
\]

Substituting values:

- \(P = 17.9 \times 10^3\ \text{N}\)
- \(L = 0.50\ \text{m}\)
- \(E = 200 \times 10^9\ \text{Pa}\)
- \(\delta_{\max} = 0.01\ \text{m}\)

\[
I_{\text{req}} \approx 3.7 \times 10^{-7}\ \text{m}^4
\]

This is the minimum stiffness required for the beam to satisfy the deflection constraint.

## Beam Cross-Section Selection

I compared solid and hollow rectangular sections for stiffness and mass efficiency.

### Solid Rectangular Beam 

A moderately sized solid bar (e.g., 40 mm × 60 mm) can meet the stiffness requirement but results in:

- \(I \approx 7.2 \times 10^{-7}\ \text{m}^4\)  
- Mass ≈ **9.4 kg** for a 0.5 m bar  

This is **not mass efficient**, and material usage is excessive.

### Hollow Rectangular Tube

I selected a **40 mm × 80 mm × 3 mm steel rectangular tube**:

- Outer dimensions: 40 mm (width) × 80 mm (height)  
- Wall thickness: 3 mm  
- Computes to:

\[
I \approx 5.6 \times 10^{-7}\ \text{m}^4 > I_{\text{req}}
\]

This gives a predicted deflection:

\[
\delta_{\max} \approx 6.7\ \text{mm}
\]

Which is:

- **Below 10 mm** (2% of L)  
- Only **1.3% of the beam length**  

The tube's cross-sectional area:

\[
A \approx 6.84 \times 10^{-4}\ \text{m}^2
\]

Mass per meter:

\[
m' \approx 5.4\ \text{kg/m}
\]

Mass for a 0.5 m beam:

\[
m \approx 2.7\ \text{kg}
\]

This beam is **more than 3× lighter** than a solid section that meets the same stiffness requirement.

## Final Beam Design Drawing

The SVG below represents the final flexible-beam design used in Step 2.  
It reflects the same mechanism geometry as Step 1 but includes:

- The chosen **rectangular hollow cross-section**  
- Clearly marked beam dimensions  
- Updated annotations describing material and stiffness

```html
<img src="image: /assets/images/step1-mech.png" alt="Final Step 2 Beam Design" />
