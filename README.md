# VTOL UAV — Concept to Validation

> **Design, Analysis and Validation of a Small Electric VTOL UAV**

This project focuses on the **complete engineering development of an electric VTOL UAV**, starting from mission requirements and conceptual configuration selection and progressing through preliminary sizing, aerodynamic design, propulsion, structural analysis, CAD development, simulation and validation.

The design methodology is inspired by established VTOL aircraft conceptual-design approaches, while the **aircraft configuration, dimensions, calculations, CAD and final design are developed independently for this project**.

---

## 🚀 Project Objective

The objective is to develop a complete VTOL UAV through a structured engineering workflow:

**Requirements → Concept → Sizing → Aerodynamics → Propulsion → Structure → CAD → Simulation → Validation**

The project will also investigate how major design parameters such as aircraft mass, wing loading, cruise speed, VTOL thrust requirement and battery capacity influence overall aircraft performance.

---

# 📌 Project Status

| Area                       | Status         |
| -------------------------- | -------------- |
| Project concept            | 🔄 In Progress |
| Mission definition         | ⬜ Planned      |
| Configuration selection    | ⬜ Planned      |
| Preliminary sizing         | ⬜ Planned      |
| Weight estimation          | ⬜ Planned      |
| Wing sizing                | ⬜ Planned      |
| Airfoil selection          | ⬜ Planned      |
| Aerodynamic analysis       | ⬜ Planned      |
| Tail design                | ⬜ Planned      |
| VTOL propulsion sizing     | ⬜ Planned      |
| Cruise propulsion sizing   | ⬜ Planned      |
| Battery sizing             | ⬜ Planned      |
| Structural calculations    | ⬜ Planned      |
| V-n diagram                | ⬜ Planned      |
| Wing/spar design           | ⬜ Planned      |
| SolidWorks CAD             | ⬜ Planned      |
| XFLR5 analysis             | ⬜ Planned      |
| ANSYS structural analysis  | ⬜ Planned      |
| Flight dynamics model      | ⬜ Planned      |
| MATLAB/Simulink simulation | ⬜ Planned      |
| Performance validation     | ⬜ Planned      |
| Sensitivity analysis       | ⬜ Planned      |
| Final aircraft design      | ⬜ Planned      |
| Research paper             | ⬜ Planned      |

---

# ✈️ Planned Aircraft Concept

The aircraft will be developed as an **electric VTOL UAV capable of vertical takeoff/landing and efficient forward flight**.

The exact configuration will be finalized after comparing possible VTOL architectures.

### Initial design philosophy

* Electric propulsion
* Vertical takeoff and landing
* Fixed-wing forward flight
* Separate analysis of VTOL and cruise propulsion requirements
* Lightweight structural design
* Modular avionics architecture
* CAD-based engineering development
* Simulation-based validation

### Concept Selection

Configurations to be evaluated:

* ⬜ Multirotor-assisted fixed wing
* ⬜ Tilt-rotor
* ⬜ Tail-sitter
* ⬜ Other suitable VTOL architectures

The final configuration will be selected using a **weighted engineering decision matrix** considering:

* Efficiency
* Mechanical complexity
* Control complexity
* Manufacturing
* Reliability
* Weight
* Aerodynamic performance
* Transition characteristics

---

# 01 — Mission & Requirements

### Tasks

* ⬜ Define mission
* ⬜ Define payload
* ⬜ Define target MTOW
* ⬜ Define cruise speed
* ⬜ Define maximum speed
* ⬜ Define stall speed
* ⬜ Define endurance
* ⬜ Define range
* ⬜ Define VTOL hover duration
* ⬜ Define climb rate
* ⬜ Define operating altitude
* ⬜ Define environmental assumptions

### Deliverables

* `mission_requirements.md`
* Mission profile
* Requirements table
* Design constraints

---

# 02 — Conceptual Design

### Tasks

* ⬜ Study VTOL configurations
* ⬜ Generate concept sketches
* ⬜ Compare configurations
* ⬜ Select final architecture
* ⬜ Define propulsion architecture
* ⬜ Define preliminary aircraft layout

### Deliverables

* Configuration comparison
* Decision matrix
* Concept sketches
* Selected configuration

---

# 03 — Preliminary Sizing

This section establishes the fundamental aircraft dimensions and performance requirements.

### Weight Estimation

* ⬜ Estimate structural weight
* ⬜ Estimate propulsion weight
* ⬜ Estimate battery weight
* ⬜ Estimate avionics weight
* ⬜ Estimate payload weight
* ⬜ Calculate MTOW
* ⬜ Perform weight iteration

### Wing Sizing

Calculate:

$$
\frac{W}{S}
$$

$$
S
$$

$$
AR
$$

$$
b
$$

$$
MAC
$$

$$
c
$$

### Performance Constraints

* ⬜ Stall-speed constraint
* ⬜ Cruise-speed constraint
* ⬜ Climb constraint
* ⬜ VTOL constraint
* ⬜ Power loading
* ⬜ Wing loading
* ⬜ Sizing matrix

### Deliverables

* Preliminary sizing calculations
* Weight breakdown
* Wing dimensions
* Performance constraint plots
* Initial aircraft dimensions

---

# 04 — Aerodynamic Design

## Airfoil

* ⬜ Calculate Reynolds number
* ⬜ Identify candidate airfoils
* ⬜ Compare aerodynamic characteristics
* ⬜ Select wing airfoil
* ⬜ Select tail airfoil

## Wing

Calculate/design:

* ⬜ Wing area
* ⬜ Wingspan
* ⬜ Aspect ratio
* ⬜ Mean aerodynamic chord
* ⬜ Taper ratio
* ⬜ Sweep
* ⬜ Dihedral
* ⬜ Twist, if required

## Tail

* ⬜ Select tail configuration
* ⬜ Horizontal tail sizing
* ⬜ Vertical tail sizing
* ⬜ Tail arm
* ⬜ Tail volume coefficients
* ⬜ Control-surface sizing

## Aerodynamic Validation

Using XFLR5 or equivalent:

* ⬜ Lift coefficient
* ⬜ Drag coefficient
* ⬜ Lift-to-drag ratio
* ⬜ Stall behavior
* ⬜ Lift curve
* ⬜ Drag polar
* ⬜ Stability characteristics

---

# 05 — Structural Design

### Loads

* ⬜ Determine design load factors
* ⬜ Develop V-n diagram
* ⬜ Calculate maneuver loads
* ⬜ Calculate gust loads
* ⬜ Identify critical load case

### Wing Structure

* ⬜ Select structural architecture
* ⬜ Select spar configuration
* ⬜ Select structural materials
* ⬜ Calculate bending moment
* ⬜ Calculate shear force
* ⬜ Calculate bending stress
* ⬜ Calculate deflection
* ⬜ Calculate factor of safety

### FEA

Using ANSYS:

* ⬜ Geometry preparation
* ⬜ Material definition
* ⬜ Boundary conditions
* ⬜ Mesh generation
* ⬜ Static structural analysis
* ⬜ Stress result
* ⬜ Deformation result
* ⬜ Factor of safety
* ⬜ Mesh convergence study

---

# 06 — Propulsion System

## VTOL Propulsion

Calculate:

$$
T_{total} \geq kW
$$

$$
T_{motor}=\frac{T_{total}}{N}
$$

* ⬜ Number of VTOL motors
* ⬜ Required thrust
* ⬜ Motor selection
* ⬜ Propeller selection
* ⬜ ESC selection
* ⬜ Hover power
* ⬜ Climb power
* ⬜ Thrust margin

## Cruise Propulsion

Calculate:

$$
D=\frac{1}{2}\rho V^2SC_D
$$

$$
P=DV
$$

* ⬜ Cruise thrust
* ⬜ Cruise power
* ⬜ Cruise motor selection
* ⬜ Propeller selection
* ⬜ ESC selection
* ⬜ Propulsive efficiency

---

# 07 — Battery & Electrical System

### Battery

* ⬜ Mission energy calculation
* ⬜ VTOL energy
* ⬜ Cruise energy
* ⬜ Climb energy
* ⬜ Landing energy
* ⬜ Battery capacity
* ⬜ Battery voltage
* ⬜ Maximum current
* ⬜ Battery mass
* ⬜ Energy reserve

### Electrical Architecture

* ⬜ Battery
* ⬜ Power distribution
* ⬜ ESCs
* ⬜ Motors
* ⬜ Flight controller
* ⬜ Sensors
* ⬜ Telemetry
* ⬜ Power monitoring

---

# 08 — CAD Development

## SolidWorks

The final aircraft will be developed as a complete assembly.

### Components

* ⬜ Fuselage
* ⬜ Main wing
* ⬜ Wing spars
* ⬜ VTOL motor mounts
* ⬜ VTOL motors
* ⬜ Cruise motor mount
* ⬜ Tail
* ⬜ Control surfaces
* ⬜ Battery compartment
* ⬜ Avionics compartment
* ⬜ Payload compartment

### Deliverables

* `.SLDPRT`
* `.SLDASM`
* `.STEP`
* `.STL`
* Engineering drawings
* Final renders

---

# 09 — Flight Dynamics

The aircraft will eventually be represented using mathematical models.

### Planned work

* ⬜ Coordinate system definition
* ⬜ Equations of motion
* ⬜ Longitudinal dynamics
* ⬜ Lateral-directional dynamics
* ⬜ Stability derivatives
* ⬜ Trim conditions
* ⬜ Linearization
* ⬜ State-space model
* ⬜ Control response

### Simulation

* ⬜ MATLAB
* ⬜ Simulink
* ⬜ Flight dynamics simulation
* ⬜ VTOL simulation
* ⬜ Cruise simulation
* ⬜ Transition analysis

---

# 10 — Performance Analysis

The final aircraft will be evaluated for:

### Flight Performance

* ⬜ Maximum speed
* ⬜ Stall speed
* ⬜ Cruise speed
* ⬜ Climb rate
* ⬜ Endurance
* ⬜ Range
* ⬜ Hover capability
* ⬜ VTOL power requirement
* ⬜ Cruise power requirement

### Performance Plots

* ⬜ Power vs speed
* ⬜ Drag vs speed
* ⬜ Lift vs angle of attack
* ⬜ L/D vs angle of attack
* ⬜ Endurance vs payload
* ⬜ Range vs battery capacity
* ⬜ VTOL power vs mass

---

# 11 — Sensitivity Analysis

A major goal is to determine which parameters have the greatest influence on aircraft performance.

Parameters to investigate:

* ⬜ MTOW
* ⬜ Wing loading
* ⬜ Aspect ratio
* ⬜ Cruise speed
* ⬜ Battery mass
* ⬜ Battery energy density
* ⬜ VTOL thrust margin
* ⬜ Propeller efficiency
* ⬜ Aerodynamic efficiency

Example:

$$
Battery\ Mass
\rightarrow
MTOW
\rightarrow
VTOL\ Power
\rightarrow
Energy
\rightarrow
Endurance
$$

This will help identify the **design trade-offs and optimal design region** rather than producing only one final aircraft configuration.

---

# 12 — Validation

The final design will be checked using multiple methods:

```text
Analytical Calculation
        ↓
       CAD
        ↓
Aerodynamic Simulation
        ↓
Propulsion Calculation
        ↓
Structural FEA
        ↓
Flight Dynamics
        ↓
Performance Comparison
```

### Validation checklist

* ⬜ Hand calculations vs Python/MATLAB
* ⬜ Analytical aerodynamics vs XFLR5
* ⬜ Structural calculations vs ANSYS
* ⬜ Motor requirement vs selected motor
* ⬜ Battery calculation vs actual battery specification
* ⬜ Predicted performance vs simulation
* ⬜ Mesh convergence
* ⬜ Sensitivity analysis

---

# 📊 Final Design Summary

This section will be completed after the design is finalized.

| Parameter          | Final Value |
| ------------------ | ----------: |
| MTOW               |         TBD |
| Empty Weight       |         TBD |
| Payload            |         TBD |
| Wing Area          |         TBD |
| Wingspan           |         TBD |
| Aspect Ratio       |         TBD |
| Cruise Speed       |         TBD |
| Maximum Speed      |         TBD |
| Stall Speed        |         TBD |
| VTOL Motors        |         TBD |
| VTOL Thrust/Motor  |         TBD |
| Cruise Motor       |         TBD |
| Battery            |         TBD |
| Endurance          |         TBD |
| Range              |         TBD |
| Maximum Climb Rate |         TBD |

---


```text
[ ] Requirements
        ↓
[ ] Concept Selection
        ↓
[ ] Preliminary Sizing
        ↓
[ ] Aerodynamic Design
        ↓
[ ] Propulsion Design
        ↓
[ ] Battery & Avionics
        ↓
[ ] Structural Design
        ↓
[ ] SolidWorks CAD
        ↓
[ ] XFLR5
        ↓
[ ] ANSYS
        ↓
[ ] Flight Dynamics
        ↓
[ ] MATLAB / Simulink
        ↓
[ ] Performance Validation
        ↓
[ ] Sensitivity Analysis
        ↓
[ ] Final VTOL Design
        ↓
[ ] Research Paper
```

**Status:** 🔄 Project Initiated
**Design Stage:** Concept Development
