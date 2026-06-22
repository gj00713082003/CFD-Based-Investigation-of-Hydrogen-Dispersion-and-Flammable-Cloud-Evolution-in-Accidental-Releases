# CFD-Based-Investigation-of-Hydrogen-Dispersion-and-Flammable-Cloud-Evolution-in-Accidental-Releases

## Overview

Hydrogen is widely recognized as a promising clean energy carrier for future energy systems. However, its low ignition energy, high diffusivity, and broad flammability range introduce significant safety concerns during storage, transportation, and utilization. Understanding the dispersion behavior of leaked hydrogen is therefore essential for the safe deployment of hydrogen technologies.

This project presents a Computational Fluid Dynamics (CFD) investigation of hydrogen (H₂) leakage and dispersion in enclosed environments using ANSYS Fluent. The study focuses on predicting hydrogen concentration distribution, buoyancy-driven plume behavior, flammable cloud formation (4–78% H₂ by volume), and associated safety hazards under various leak and ventilation scenarios. Simulations employ species transport and turbulence modeling to quantify flammable cloud volume, concentration evolution, and risk zones, providing insights for hydrogen safety assessment, ventilation design, and leak mitigation in future hydrogen energy systems.

---

## Research Objectives

### Primary Objectives

* Simulate hydrogen leakage in an enclosed room.
* Investigate buoyancy-driven hydrogen dispersion.
* Predict hydrogen concentration distribution throughout the domain.
* Determine flammable cloud formation and growth.
* Quantify the volume occupied by hydrogen within the flammable range.
* Assess potential safety hazards associated with hydrogen accumulation.

### Secondary Objectives

* Evaluate transient evolution of hydrogen concentration.
* Identify regions with elevated ignition risk.
* Analyze the influence of room ventilation on dispersion behavior.
* Develop a CFD workflow for hydrogen safety assessment.

---

## Physical Problem Description

Hydrogen is continuously released into an enclosed room through a circular leak source. Due to its low density, hydrogen rises rapidly and accumulates near the ceiling. The resulting concentration field is monitored to determine the extent and evolution of the flammable cloud.

### Room Dimensions

| Parameter | Value |
| --------- | ----- |
| Length    | 3 m   |
| Width     | 2.5 m |
| Height    | 3 m   |

### Leak Characteristics

| Parameter               | Value           |
| ----------------------- | --------------- |
| Leak Diameter           | 55 mm           |
| Hydrogen Mass Flow Rate | 1.5 × 10⁻⁵ kg/s |
| Release Type            | Continuous      |
| Release Composition     | 100% Hydrogen   |

### Ventilation

* Open door acting as pressure outlet
* Natural ventilation conditions

---

## Numerical Methodology

The simulation workflow consists of:

1. Geometry generation
2. Mesh generation
3. Boundary condition definition
4. Solver configuration
5. Steady-state simulation
6. Transient simulation
7. Post-processing
8. Flammable cloud assessment
9. Safety evaluation

---

## Governing Equations

The simulations solve the following transport equations:

### Continuity Equation

Mass conservation for the hydrogen-air mixture.

### Momentum Equation

Navier-Stokes equations governing fluid motion.

### Species Transport Equation

Transport of hydrogen within ambient air through convection and diffusion.

### Turbulence Model

RNG k-ε turbulence model.

### Buoyancy Effects

Gravity-induced density differences are considered to capture hydrogen plume rise and ceiling accumulation.

---

## CFD Model Setup

### Solver

* Pressure-Based Solver
* Species Transport Model
* Gravity Enabled

### Turbulence

* RNG k-ε Model
* Enhanced Wall Treatment

### Pressure-Velocity Coupling

#### Steady-State

* SIMPLE Scheme

#### Transient

* PISO Scheme

### Spatial Discretization

* Pressure: Second Order
* Momentum: Second Order Upwind
* Turbulent Kinetic Energy: Second Order Upwind
* Turbulent Dissipation Rate: Second Order Upwind
* Species: Second Order Upwind

---

## Boundary Conditions

### Hydrogen Inlet

| Parameter | Value           |
| --------- | --------------- |
| Type      | Mass Flow Inlet |
| Species   | H₂ = 1          |
| Flow Rate | 1.5 × 10⁻⁵ kg/s |

### Outlet

| Parameter      | Value           |
| -------------- | --------------- |
| Type           | Pressure Outlet |
| Gauge Pressure | 0 Pa            |

Backflow Composition:

* O₂ = 23%
* N₂ = 77%

### Walls

* No-slip condition
* Adiabatic

---

## Mesh Generation

A high-quality computational mesh is generated to accurately resolve hydrogen concentration gradients near the leak source.

### Meshing Strategy

* Unstructured mesh
* Local refinement around leakage region
* Inflation layers near walls
* Grid quality assessment

### Mesh Quality Metrics

* Maximum Skewness
* Average Orthogonal Quality
* Total Cell Count

---

## Simulation Cases

### Steady-State Analysis

Performed to determine the final equilibrium distribution of hydrogen within the room.

### Transient Analysis

Performed to investigate:

* Cloud growth
* Ceiling accumulation
* Temporal evolution of concentration
* Hazard development

Typical transient settings:

| Parameter           | Value  |
| ------------------- | ------ |
| Time Step           | 0.05 s |
| Iterations per Step | 30     |
| Number of Steps     | 500    |

---

## Post-Processing

The following quantities are extracted from ANSYS Fluent:

### Hydrogen Concentration

* Mole Fraction Contours
* Mass Fraction Contours
* Iso-surfaces

### Flow Characteristics

* Velocity Magnitude
* Streamlines
* Velocity Vectors

### Cloud Characteristics

* Cloud Height
* Cloud Width
* Maximum Extent
* Ceiling Accumulation Region

---

## Flammable Cloud Analysis

Hydrogen becomes flammable when its concentration lies within the flammability limits.

### Flammable Range

Lower Flammability Limit (LFL): 4%

Upper Flammability Limit (UFL): 78%

The flammable cloud is defined as:

4% ≤ H₂ Mole Fraction ≤ 78%

### Calculated Parameters

* Flammable Cloud Volume (m³)
* Maximum Cloud Height (m)
* Maximum Cloud Width (m)
* Cloud Growth Rate
* Time to Reach Hazardous Conditions

---

## Results

### Hydrogen Dispersion

The simulations reveal strong buoyancy-driven upward transport of hydrogen, resulting in concentration stratification and accumulation near the ceiling.

### Flammable Cloud Development

Transient simulations demonstrate the formation and growth of a flammable hydrogen cloud that expands from the release source toward the upper portions of the room.

### Safety Assessment

The concentration distribution is used to identify regions susceptible to ignition and evaluate potential hazard zones.

---

## Repository Structure

Hydrogen-Dispersion-CFD/

├── geometry/

├── mesh/

├── setup/

├── simulations/

│ ├── steady_state/

│ └── transient/

├── results/

│ ├── contours/

│ ├── streamlines/

│ ├── velocity/

│ └── flammable_cloud/

├── plots/

├── literature/

├── docs/

└── README.md

---

## Applications

* Hydrogen Storage Safety
* Fuel Cell Systems
* Hydrogen Refueling Stations
* Indoor Hydrogen Leak Assessment
* Ventilation Design
* Industrial Risk Analysis
* Hydrogen Infrastructure Development

---

## Future Work

* Large Eddy Simulation (LES)
* Explosion Consequence Analysis
* Hydrogen Sensor Placement Optimization
* Multi-Room Dispersion Studies
* Ventilation Optimization
* Machine Learning-Based Hazard Prediction
* Hydrogen Risk Quantification Framework

---

## Software Used

* ANSYS SpaceClaim
* ANSYS Meshing
* ANSYS Fluent
* CFD-Post
* Microsoft Excel
* Python (Data Analysis and Visualization)

---

## Author

Gaurav Jingar

Department of Energy Science and Engineering

Indian Institute of Technology Bombay

---

## License

This repository is intended for academic and research purposes. Please cite the repository and acknowledge the author when using the methodology or results in derivative work.
