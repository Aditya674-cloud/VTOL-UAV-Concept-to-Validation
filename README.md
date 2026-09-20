# VTOL UAV — Concept to Validation

## An Open Engineering Workflow for Hybrid VTOL Aircraft, Autonomous Flight and Collision Avoidance

This repository documents the development of a small electric hybrid VTOL UAV from the initial mission definition and engineering calculations through mechanical design, aerodynamics, propulsion, structural analysis, flight dynamics, control, perception, collision avoidance, simulation and validation.

The project is being developed as a multidisciplinary engineering study connecting:

**Mechanical Engineering → Mechatronics → Control Systems → Robotics → Autonomous Systems → Physical AI**

The objective is not only to create a UAV CAD model, but to document **how the aircraft dimensions, systems and algorithms are derived and how they are progressively validated.**

---

# 1. Project Overview

Hybrid VTOL aircraft combine the vertical take-off and landing capability of multirotor aircraft with the forward-flight capability of fixed-wing aircraft.

This project investigates a **dual-system hybrid VTOL configuration** consisting of:

* dedicated vertical-lift propulsion;
* a fixed-wing aerodynamic system;
* separate forward-flight propulsion;
* onboard avionics;
* obstacle sensing;
* autonomous collision detection and avoidance.

The project follows the aircraft from the initial design requirements through preliminary sizing, CAD, analysis, simulation and eventual validation.

---

# 2. Project Goal

The long-term goal is to develop and document an engineering workflow for an autonomous hybrid VTOL UAV capable of:

* vertical take-off;
* vertical climb;
* transition to forward flight;
* fixed-wing cruise;
* obstacle detection;
* obstacle tracking;
* collision prediction;
* collision avoidance;
* trajectory or path replanning;
* return to the intended mission;
* transition back to VTOL flight;
* vertical landing.

The project is intentionally multidisciplinary.

The mechanical design provides the physical platform.

The electronics provide sensing and actuation.

The control system provides stable flight.

The robotics and software systems provide perception, planning and autonomous behaviour.

---

# 3. Why This Repository Exists

Many UAV resources available online focus on individual areas such as:

* quadcopters;
* fixed-wing aircraft;
* autopilot configuration;
* flight controllers;
* computer vision;
* robotics;
* simulation;
* or individual aerodynamic tools.

These resources are useful, but the complete engineering path from **aircraft requirements → dimensions → CAD → analysis → autonomous system** is often distributed across many different sources.

This repository attempts to connect those areas into one traceable workflow.

The intention is to make the project useful not only as a record of one aircraft, but also as a reference for students and engineers trying to understand how a hybrid VTOL UAV can be developed from first principles.

---

# 4. Engineering Philosophy

The project follows the principle:

```text
Requirement
    ↓
Assumption
    ↓
Engineering Method
    ↓
Calculation / Simulation
    ↓
Result
    ↓
Design Decision
    ↓
Validation
```

The aircraft is not designed by choosing arbitrary dimensions first.

Instead, dimensions are progressively derived from:

* mission requirements;
* mass;
* aerodynamic requirements;
* propulsion requirements;
* structural requirements;
* component packaging;
* stability;
* control;
* and validation.

The design is therefore iterative.

```text
Requirements
      ↓
Preliminary Sizing
      ↓
First Geometry
      ↓
CAD
      ↓
Analysis
      ↓
Updated Geometry
      ↓
Simulation
      ↓
Validation
      ↓
Design Revision
```

A design revision may change previously calculated dimensions.

This is expected in aircraft development.

---

# 5. System Development Roadmap

```text
                     MISSION
                        ↓
                  REQUIREMENTS
                        ↓
                 CONFIGURATION
                        ↓
               PRELIMINARY SIZING
                        ↓
                  AERODYNAMICS
                        ↓
                   PROPULSION
                        ↓
              MECHANICAL / CAD
                        ↓
                STRUCTURAL FEA
                        ↓
               MASS PROPERTIES
                        ↓
                FLIGHT DYNAMICS
                        ↓
                     CONTROL
                        ↓
                  ELECTRONICS
                        ↓
                   PERCEPTION
                        ↓
              COLLISION PREDICTION
                        ↓
                AVOIDANCE LOGIC
                        ↓
                   SIMULATION
                        ↓
                   PROTOTYPE
                        ↓
                  VALIDATION
```

---

# 6. Repository Structure

```text
VTOL-UAV-Concept-to-Validation/

├── README.md
│
├── 00_Requirements/
│   └── 0. Requirements and Mission.md
│
├── 01_Concept_and_Sizing/
│   └── 1. Concept and Preliminary Sizing.md
│
├── 02_Aerodynamics/
│   └── 2. Aerodynamic Design.md
│
├── 03_Propulsion_and_Energy/
│   └── 3. Propulsion and Energy System.md
│
├── 04_CAD_and_Mechanical_Design/
│   └── 4. CAD and Mechanical Design.md
│
├── 05_Structural_Analysis/
│   └── 5. Structural Analysis.md
│
├── 06_Flight_Dynamics/
│   └── 6. Flight Dynamics and Mathematical Model.md
│
├── 07_Control/
│   └── 7. Flight Control System.md
│
├── 08_Electronics/
│   └── 8. Electronics and Avionics.md
│
├── 09_Anti_Collision/
│   └── 9. Anti-Collision System.md
│
├── 10_Perception_and_AI/
│   └── 10. Perception and AI.md
│
├── 11_Simulation/
│   └── 11. Simulation and Digital Twin.md
│
├── 12_Validation/
│   └── 12. Experimental Validation.md
│
├── 13_Research/
│   └── 13. Literature Review and References.md
│
└── 14_Results/
    └── 14. Results and Design Iterations.md
```

Some chapters will remain under development until the corresponding engineering work is completed.

The repository structure is therefore a roadmap rather than a claim that every stage has already been completed.

---

# 7. Development Stages

## Stage 0 — Requirements and Mission

Define:

* mission;
* aircraft purpose;
* operating environment;
* initial performance requirements;
* payload;
* initial MTOW;
* speed requirements;
* endurance;
* VTOL requirements;
* collision-avoidance requirements;
* system architecture.

**Status:** Started

---

## Stage 1 — Concept and Preliminary Sizing

Determine:

* aircraft configuration;
* initial mass budget;
* wing area;
* wing loading;
* aspect ratio;
* span;
* chord;
* taper;
* tail sizing;
* preliminary fuselage envelope;
* VTOL thrust;
* forward-flight propulsion;
* preliminary battery requirement;
* centre of gravity.

**Status:** In progress

---

## Stage 2 — Aerodynamic Design

Investigate:

* Reynolds number;
* airfoil selection;
* airfoil coordinates;
* XFLR5/XFOIL analysis;
* lift coefficient;
* drag coefficient;
* pitching moment;
* lift-to-drag ratio;
* wing performance;
* lift distribution;
* induced drag;
* stability;
* control surfaces.

**Status:** Started

---

## Stage 3 — Propulsion and Energy

Determine:

* VTOL motor requirements;
* propeller requirements;
* forward-flight motor;
* forward-flight propeller;
* ESCs;
* battery;
* current;
* power;
* energy;
* endurance;
* thermal requirements.

**Status:** Planned

---

## Stage 4 — CAD and Mechanical Design

Develop the SolidWorks model from the preliminary design point.

The CAD model will include:

* wing;
* fuselage;
* tail;
* VTOL arms/booms;
* motor mounts;
* propeller clearances;
* battery compartment;
* avionics compartment;
* payload bay;
* structural components;
* assembly.

The CAD model will also be used to determine:

* mass properties;
* centre of gravity;
* component packaging;
* interference;
* mechanical interfaces.

**Status:** Not started

---

## Stage 5 — Structural Analysis

Investigate:

* flight loads;
* VTOL loads;
* wing bending;
* spar loads;
* structural stress;
* deformation;
* factor of safety;
* motor/boom loads;
* landing loads.

Where appropriate, finite element analysis will be performed using ANSYS.

**Status:** Planned

---

## Stage 6 — Flight Dynamics

Develop mathematical models for:

* longitudinal motion;
* lateral-directional motion;
* VTOL operation;
* forward flight;
* transition;
* actuator behaviour;
* stability;
* trim.

The objective is to create a mathematical representation suitable for simulation and controller development.

**Status:** Planned

---

## Stage 7 — Flight Control

Investigate:

* attitude control;
* altitude control;
* position control;
* VTOL control;
* fixed-wing control;
* transition control;
* trajectory tracking;
* disturbance rejection.

Possible control methods will be evaluated based on the requirements of the aircraft model.

**Status:** Planned

---

## Stage 8 — Electronics and Avionics

Define:

* flight controller;
* IMU;
* GPS;
* barometer;
* magnetometer;
* ESCs;
* telemetry;
* power distribution;
* communication;
* obstacle sensors;
* companion computer where required.

**Status:** Planned

---

## Stage 9 — Anti-Collision System

Develop an integrated collision-avoidance architecture.

The functional chain is:

```text
Sensor
  ↓
Sensor Processing
  ↓
Obstacle Detection
  ↓
Object Tracking
  ↓
Relative-State Estimation
  ↓
Collision Prediction
  ↓
Avoidance Decision
  ↓
Trajectory Update
  ↓
Flight Controller
  ↓
Aircraft
```

Potential technologies include:

* cameras;
* depth cameras;
* LiDAR;
* range sensors;
* optical flow;
* sensor fusion;
* computer vision.

The final architecture will be selected after studying the requirements, computational limitations, sensor characteristics and aircraft constraints.

**Status:** Planned

---

## Stage 10 — Perception and Physical AI

The project will investigate the computational side of autonomous flight.

Potential areas include:

* object detection;
* object tracking;
* depth estimation;
* sensor fusion;
* relative motion estimation;
* collision prediction;
* path planning;
* trajectory generation;
* autonomous decision making.

The intention is to connect perception and decision-making directly to the physical aircraft.

**Status:** Planned

---

## Stage 11 — Simulation and Digital Model

Simulation will progressively connect the individual subsystems.

Potential simulation environments include:

* MATLAB;
* Simulink;
* UAV-related MATLAB tools;
* robotics simulation tools;
* Python-based analysis;
* flight-controller simulation where appropriate.

The objective is to build progressively more complete models rather than immediately attempting a complete autonomous simulation.

**Status:** Planned

---

## Stage 12 — Validation

The final stage will compare engineering predictions with experimental results.

Potential validation activities include:

* motor thrust testing;
* power measurements;
* battery testing;
* structural tests;
* sensor testing;
* control-system tests;
* flight tests;
* obstacle-detection tests;
* collision-avoidance tests.

The exact validation plan will depend on the final aircraft and available hardware.

**Status:** Planned

---

# 8. Current Preliminary Design Point

The project currently uses the following preliminary values as a starting point.

| Parameter             |       Preliminary Value | Status                 |
| --------------------- | ----------------------: | ---------------------- |
| Configuration         | Dual-system hybrid VTOL | Selected               |
| Initial MTOW          |                    5 kg | Assumption             |
| Initial payload       |                  0.9 kg | Assumption             |
| Cruise speed          |                  15 m/s | Assumption             |
| Stall speed           |                  12 m/s | Assumption             |
| Number of VTOL motors |                       4 | Preliminary            |
| Forward propulsion    |                 1 motor | Preliminary            |
| Aspect ratio          |                       7 | Preliminary            |
| Wing area             |               ~0.428 m² | Calculated             |
| Wing span             |                 ~1.73 m | Calculated             |
| Mean chord            |                ~0.247 m | Calculated             |
| Airfoil               |                     TBD | Analysis required      |
| Endurance             |                     TBD | Not yet defined        |
| Range                 |                     TBD | Not yet defined        |
| Battery               |                     TBD | Not yet selected       |
| CG                    |                     TBD | CAD iteration required |

These values are **not final specifications**.

They represent the current starting point for the preliminary sizing process.

---

# 9. Design Revision Philosophy

The aircraft will be developed through design revisions.

```text
Revision 0
Initial requirements and preliminary sizing

        ↓

Revision 1
Aerodynamic refinement

        ↓

Revision 2
Propulsion and energy refinement

        ↓

Revision 3
CAD mass properties and CG

        ↓

Revision 4
Structural refinement

        ↓

Revision 5
Flight-dynamics and control model

        ↓

Revision 6
Integrated autonomous system

        ↓

Prototype Revision
Physical validation
```

A revision is introduced when a significant change affects the aircraft geometry, mass, propulsion, structure or system architecture.

---

# 10. Engineering Traceability

Every important design variable should ideally have a traceable path.

Example:

```text
Stall-speed requirement
        ↓
CLmax assumption
        ↓
Wing-area calculation
        ↓
Wing area
        ↓
Aspect ratio
        ↓
Wing span
        ↓
Chord
        ↓
Reynolds number
        ↓
Airfoil analysis
        ↓
Wing geometry
        ↓
SolidWorks
        ↓
Aerodynamic validation
```

Similarly:

```text
MTOW
  ↓
Required VTOL thrust
  ↓
Thrust per motor
  ↓
Motor + propeller
  ↓
Current
  ↓
Power
  ↓
Battery
  ↓
Battery mass
  ↓
Updated MTOW
```

This creates a feedback loop.

---

# 11. Mechanical → Robotics → Physical AI

One of the goals of this project is to demonstrate how conventional mechanical engineering can provide the physical foundation for an autonomous robotic system.

The progression is:

```text
Mechanical Engineering
        |
        +-- Aircraft configuration
        +-- Aerodynamics
        +-- CAD
        +-- Structures
        +-- Propulsion
        |
        v
Mechatronics
        |
        +-- Motors
        +-- ESCs
        +-- Sensors
        +-- Power electronics
        |
        v
Control Engineering
        |
        +-- Dynamics
        +-- State estimation
        +-- Flight control
        +-- Trajectory tracking
        |
        v
Robotics
        |
        +-- Perception
        +-- Localization
        +-- Planning
        +-- Obstacle avoidance
        |
        v
Physical AI
        |
        +-- Environment understanding
        +-- Collision prediction
        +-- Autonomous decision making
        +-- Real-world action
```

The objective is not to replace mechanical engineering with software.

The objective is to connect the physical system and the computational system.

---

# 12. Tools and Technologies

The project may use the following tools depending on the analysis stage:

### CAD

* SolidWorks
* CATIA where appropriate

### Aerodynamics

* XFLR5
* XFOIL
* analytical aerodynamic calculations

### Structural Analysis

* ANSYS
* analytical structural calculations

### Modelling and Control

* MATLAB
* Simulink

### Robotics and Autonomy

* MATLAB Robotics/UAV resources
* ROS/ROS 2 where appropriate
* Python
* computer-vision libraries
* flight-controller simulation

### Documentation and Version Control

* Git
* GitHub
* Markdown

Tools are selected according to the engineering problem rather than using one software package for every task.

---

# 13. How to Read This Repository

The recommended reading order is:

```text
00 Requirements
      ↓
01 Concept and Preliminary Sizing
      ↓
02 Aerodynamics
      ↓
03 Propulsion and Energy
      ↓
04 CAD and Mechanical Design
      ↓
05 Structural Analysis
      ↓
06 Flight Dynamics
      ↓
07 Control
      ↓
08 Electronics
      ↓
09 Anti-Collision
      ↓
10 Perception and AI
      ↓
11 Simulation
      ↓
12 Validation
```

Readers interested in a particular discipline can also enter the project at the corresponding chapter.

Each chapter should explain:

1. What problem is being solved.
2. Why the problem matters.
3. What assumptions are being made.
4. What method is being used.
5. What calculations or simulations are performed.
6. What results are obtained.
7. What design decision follows.
8. How the result will eventually be validated.

---

# 14. Project Status

### Completed / Started

* Initial project concept.
* Hybrid VTOL architecture study.
* Preliminary dual-system configuration.
* Initial MTOW assumption.
* Preliminary mass breakdown.
* Initial wing sizing.
* Initial aspect-ratio selection.
* Preliminary wing dimensions.
* Initial Reynolds-number calculation.
* Preliminary VTOL thrust calculation.
* Initial forward-flight calculations.
* Initial fuselage and CG considerations.
* Beginning of aerodynamic-design documentation.

### In Progress

* Requirements definition.
* Preliminary aircraft sizing.
* Aerodynamic analysis.
* Airfoil selection.
* XFLR5 methodology.
* Design-point refinement.

### Planned

* Propulsion selection.
* Battery sizing.
* SolidWorks CAD.
* Structural analysis.
* Flight-dynamics modelling.
* Flight-control development.
* Electronics architecture.
* Anti-collision system.
* Perception.
* Autonomous planning.
* Simulation.
* Prototype.
* Experimental validation.

---

# 15. Current Next Step

The immediate objective is to establish:

## Design Revision 0

This includes:

* requirements;
* initial MTOW;
* mass budget;
* wing area;
* wing span;
* chord;
* wing planform;
* preliminary tail dimensions;
* VTOL thrust requirement;
* forward-flight propulsion requirement;
* preliminary battery requirement;
* fuselage envelope;
* preliminary CG.

Once these values are established, the first meaningful SolidWorks concept model can be created.

The resulting geometry will then be analysed and iterated rather than treated as a final design.

---

# 16. Final Objective

The final objective of this repository is to demonstrate a complete engineering chain:

```text
IDEA
 ↓
REQUIREMENTS
 ↓
RESEARCH
 ↓
ENGINEERING CALCULATIONS
 ↓
PRELIMINARY DESIGN
 ↓
AERODYNAMICS
 ↓
PROPULSION
 ↓
CAD
 ↓
STRUCTURAL ANALYSIS
 ↓
FLIGHT DYNAMICS
 ↓
CONTROL
 ↓
ELECTRONICS
 ↓
PERCEPTION
 ↓
ANTI-COLLISION
 ↓
AUTONOMOUS DECISION MAKING
 ↓
SIMULATION
 ↓
PROTOTYPE
 ↓
EXPERIMENT
 ↓
VALIDATION
```

The project is being developed progressively.

Not every value is known at the beginning.

Not every calculation will remain unchanged.

The purpose of the repository is to make those engineering decisions, revisions and trade-offs visible and understandable.

---

## Status

**Project:** VTOL UAV — Concept to Validation

**Configuration:** Hybrid / Dual-System VTOL

**Primary disciplines:** Mechanical Engineering, Aerodynamics, Propulsion, Structural Analysis, Control Systems, Electronics, Robotics and Autonomous Systems

**Current stage:** Requirements + Concept + Preliminary Sizing

**Next major milestone:** Design Revision 0





