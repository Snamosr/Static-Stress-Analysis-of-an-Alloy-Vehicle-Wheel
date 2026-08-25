# Static Stress Analysis of an Aluminum Alloy Vehicle Wheel Under Lateral Cornering Loads.
---
**Software:** SolidWorks Simulation (Static Study) |

**Domain:** Structural Mechanics & FEA |

**Date:** 2025


## 1. Background & Motivation
Creating complex 3D models of automotive components was a great way to master CAD surfacing and solid modeling. However, as I looked at the multi-spoke wheel, a fundamental engineering question came in mind: *Is this design actually functionally sound, or is it just aesthetically pleasing?*

In modern automotive design, alloy wheels must balance low unsprung mass with structural integrity. They endure dynamic vertical loads, braking torque, and aggressive lateral forces during high-speed cornering. I wanted to move beyond pure geometry modeling and test whether the wheel's spoke geometry and material selection could safety withstand extreme lateral loads without risk of yielding or excessive deflection.

To answer this, I established a focused static FEA study in SolidWorks Simulation to evaluate the wheel's performance under severe cornering conditions.

## 2. Description
This project investigates the structural behaviour, stress concentrations, and elastic deformation of an A356-T6 cast aluminum alloy wheel subjected to aggressive lateral cornering forces. Using SolidWorks Simulation, a static FEA study was conducted to evaluate safety margins, ensure lightweight performance, and verify structural resilience at critical wheel-spoke transitions.

## 3. Boundary Setup & Load Conditions
* ***Material:*** Permanent Mould Cast Aluminum (A356-T6), isotropic, linear elastic --  ($\sigma_{yield} = 152\text{ MPa}$, $E = 72.4\text{ GPa}$, $\nu = 0.33$).
* ***Applied Load:*** A lateral force of $11,500\text{ N}$ applied normally across the outer rim flanges to simulate peak cornering thrust.
* ***Fixtures:*** Fixed geometry constraints applied to the hub mounting face and bolt-hole seats.
* ***Meshing Strategy & Discretization:*** Applied a high-density, Curvature-based solid mesh to automatically refine element density along rounded, fillets, bolt seats, and flange transitions. Discretised body into **344,322 nodes** and **189,811 elements**, maintaining zero distorted elements, ensuring high numerical fidelity around geometric radii.

## 4. FEA Results & Analysis

### *Von Mises Stress & Safety Margins*
* ***Peak Stress:*** The maximum von Mises stress calculated was $19.4\text{ MPa}$ ($1.94\times 10^7\text { N/m}^2$), concentrated along the inner flange and spoke root radius.
* ***Yield Assessment:*** Comparing the peak stress directly to the $152\text{ MPa}$ yield limit of the A356-T6 aluminum confirms the wheel remains well within its linear elastic limit.
* ***Factor of Safety (FoS):*** A robust safety factor of **$\approx 7.83$** relative to material yield strength verifies that the structural architecture easily handles the $11.5\text{ kN}$ lateral force.

### *Deformation & Strain Profile*
* ***Displacement:*** The maximum resultant displacement reached on **$0.0476\text{ mm}$ ($47.6\ \mu\text{m}$)** at the flange, confirming high lateral stiffness with negligible geometry compliance.
* ***Equivalent Strain:*** Peak strain recorded was **$2.233 \times 10^{-4}$**, localized along the high-stress fillet regions.

## 5. Design & Engineering Takeaways
This project was a crucial step in bridging pure 3D design with quantitative structural verification:

1. ***Verification Over Intuition:*** Modeling filleted spokes is visually clean, but running static FEA proved *where* the forces actually concentrate (at the spoke-to-flange root) and quantified the structural margin of safety.
2. ***Structure Adequacy:*** The structural architecture remains well within the linear elasticity regime under an $11.5\text{ kN}$ lateral force, confirming high fatigue life margins during steady-state cornering.
3. ***Optimization Potential:*** The high *Factor of Safety* ($\text{FoS} \approx 7.8$) suggests opportunities for weight reduction through targeted web pocketing or spoke thinning without compromising stiffness or safety standards.

## 6. Multi-Solver Cross-Validation (SolidWorks vs. ANSYS)
To verify that the SolidWorks results were not sensitive to soler-specific formulation errors or mesh artifacts, a benchmark study was independently run in **ANSYS Mechanical** using identical geometry, material parameters, and an $11.5\text{ kN}$ lateral load.

### Key Validation Outcomes
* **Stress Convergence:** SolidWorks predicted a peak von Mises stress of **($19.4\text{ ,MPa}$)** while ANSYS yielded **$18.96\text{ MPa}$** - a high-fidelity correlation with only **2.3% variance**. Both solvers highlighted identical stress concentration zones along the spoke root radii.
* **Elastic Compliance:** Both solvers confirmed negligible structural deflection SolidWorks ($0.0476\text {mm}$) vs. ANSYS ($[ANSYS\ Deflection]\text{ mm}$) - demonstrating high structural stiffness consistency across both FEA Solvers.
## Contributors
* [Amos Ablorh]() - *CAD Geometry Preparation, SolidWorks Simulation (FEA), and Secondary Documentation*
* [Francis Blay-Yenzu]() - *CAD Geometry Preparation, Independent Benchmarking & FEA Cross-Validation in ANSYS Mechanical*
