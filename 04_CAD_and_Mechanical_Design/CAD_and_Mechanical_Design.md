# Chapter 4 — CAD and Mechanical Design

## 4.1 Purpose of This Chapter

The purpose of this chapter is to convert the preliminary engineering requirements from the previous chapters into a physical aircraft design.

The earlier chapters established:

* Aircraft configuration.
* Preliminary aircraft mass.
* Wing area.
* Wing span.
* Mean aerodynamic chord.
* Tail sizing.
* VTOL thrust requirements.
* Forward-flight propulsion requirements.
* Preliminary battery and propulsion requirements.

Chapter 4 converts these requirements into:

* Aircraft geometry.
* Fuselage geometry.
* Wing geometry.
* Tail geometry.
* VTOL motor locations.
* Rear pusher installation.
* Motor mounts.
* Battery compartment.
* Avionics compartment.
* Structural interfaces.
* Component clearances.
* Assembly architecture.
* Manufacturing considerations.

The CAD model should therefore not be treated only as a visual model.

It is an engineering representation of the aircraft.

---

# 4.2 From Engineering Requirements to CAD

The overall design process can be represented as:

```text
Mission Requirements
        ↓
Concept Selection
        ↓
Preliminary Sizing
        ↓
Aerodynamic Analysis
        ↓
Propulsion Requirements
        ↓
Mechanical Architecture
        ↓
CAD Model
        ↓
Structural Analysis
        ↓
Manufacturing
        ↓
Assembly
        ↓
Testing
        ↓
Validation
```

This means that CAD dimensions should have a reason behind them.

For example:

```text
Wing area
    ↓
Wing span and chord
    ↓
Fuselage integration
    ↓
Motor locations
    ↓
Structural attachment
    ↓
Battery location
    ↓
CG location
```

A good CAD model therefore represents engineering decisions rather than arbitrary geometry.

---

# 4.3 Aircraft Configuration

The aircraft is a fixed-wing hybrid VTOL configuration.

The main propulsion arrangement consists of:

* Four dedicated VTOL lift motors.
* One independent rear-mounted pusher motor.
* One fixed main wing.
* Horizontal tail.
* Vertical tail.
* Fuselage.
* Battery and avionics compartments.

The four VTOL motors provide vertical thrust.

The rear pusher motor provides forward thrust during forward flight.

The main wing provides aerodynamic lift during forward flight.

A simplified arrangement is:

```text
                    MAIN WING
          ─────────────────────────────
             ↑                    ↑
          VTOL MOTOR           VTOL MOTOR
             │                    │
             │                    │
             ↓                    ↓
          VTOL PROP             VTOL PROP


                ┌───────────┐
                │ FUSELAGE  │
                └───────────┘

                      ─────────►
                    REAR PUSHER
                      MOTOR
```

The exact motor locations will be determined through CAD, structural, aerodynamic, and CG analysis.

---

# 4.4 CAD Design Objectives

The CAD model should satisfy several objectives simultaneously.

### Aerodynamic objectives

* Maintain the required wing geometry.
* Minimize unnecessary frontal area.
* Provide smooth external geometry where practical.
* Maintain appropriate propeller clearance.
* Provide suitable tail geometry.

### Mechanical objectives

* Support motor loads.
* Support wing loads.
* Provide rigid component attachment.
* Protect sensitive electronics.
* Provide battery retention.
* Allow assembly and disassembly.

### Structural objectives

* Transfer aerodynamic loads.
* Transfer motor thrust loads.
* Resist landing loads.
* Minimize unnecessary mass.
* Provide adequate stiffness.

### Manufacturing objectives

* Use realistic materials.
* Consider available manufacturing processes.
* Minimize unnecessarily complex parts.
* Provide appropriate fastener access.
* Allow replacement of damaged components.

---

# 4.5 Reference Coordinate System

A consistent aircraft coordinate system should be established before detailed CAD work.

A common convention is:

```text
                  +X
                   →
        Forward flight direction

                   ↑ +Z
                   │
                   │
                   │
                   ●────────────→ +X
                  /
                 /
               +Y
```

The exact sign convention should be documented and then used consistently across:

* CAD.
* Flight dynamics.
* Simulation.
* Control.
* Sensor coordinate frames.
* Structural analysis.

For example:

* \(+X\): forward.
* \(+Y\): lateral direction.
* \(+Z\): upward.

The final coordinate convention must remain consistent throughout the project.

---

# 4.6 Aircraft Reference Point

A reference point should be defined for measuring component locations.

A practical choice is the aircraft nose or another clearly defined datum.

For each component:

$$
x_i,\ y_i,\ z_i
$$

can be recorded.

This allows component locations to be related to:

* CG.
* Aerodynamic center.
* Motor thrust lines.
* Structural attachment points.

---

# 4.7 Main Wing Geometry

Chapter 1 established the preliminary wing parameters:

$$
S\approx0.428\ m^2
$$

$$
AR=7
$$

and:

$$
b\approx1.73\ m
$$

The preliminary mean chord for the rectangular-wing assumption was:

$$
c\approx0.247\ m
$$

These dimensions form the starting point for the CAD model.

The actual CAD geometry may later change after:

* Airfoil selection.
* Structural analysis.
* Propulsion integration.
* Manufacturing constraints.
* Experimental testing.

Therefore, these dimensions should be treated as preliminary design inputs rather than permanently fixed values.

---

# 4.8 Airfoil Integration

The selected airfoil from Chapter 2 must be transferred into the CAD model accurately.

The airfoil coordinate file normally contains points defining the upper and lower surfaces.

A simplified workflow is:

```text
Airfoil Database
       ↓
Coordinate File
       ↓
Coordinate Verification
       ↓
Scaling
       ↓
CAD Sketch
       ↓
Airfoil Profile
       ↓
Wing Surface
```

The chord length should be scaled according to the selected wing geometry.

If the normalized airfoil coordinates use:

$$
x/c
$$

and:

$$
y/c
$$

then:

$$
x=x_{normalized}c
$$

and:

$$
y=y_{normalized}c
$$

where \(c\) is the actual chord.

---

# 4.9 Wing Planform

The wing planform defines the top-view geometry of the wing.

Important parameters include:

* Span.
* Root chord.
* Tip chord.
* Sweep.
* Taper ratio.
* Dihedral.
* Twist.
* Wing thickness.
* Wing mounting location.

The taper ratio is:

$$
\lambda=\frac{c_{tip}}{c_{root}}
$$

where:

* \(c_{tip}\) = tip chord.
* \(c_{root}\) = root chord.

For a rectangular wing:

$$
\lambda=1
$$

The final planform should be selected based on aerodynamic, structural, and manufacturing requirements.

---

# 4.10 Wing Dihedral

Dihedral is the upward angle of the wing relative to the lateral plane.

A simplified representation is:

```text
              \       /
               \_____/
```

Dihedral can influence:

* Lateral stability.
* Roll response.
* Structural arrangement.
* VTOL motor installation.
* Ground clearance.

The final dihedral angle should be selected based on the aircraft's stability and mechanical requirements.

---

# 4.11 Wing Sweep

Wing sweep is the angle between the wing reference line and a line perpendicular to the aircraft centerline.

For this preliminary UAV design, large sweep is not necessarily required because the aircraft operates at relatively low Mach number.

However, sweep may still be used for:

* CG management.
* Structural integration.
* Component placement.
* Aerodynamic considerations.

Any sweep should be documented as a deliberate design decision.

---

# 4.12 Fuselage Design

The fuselage must accommodate:

* Battery.
* Flight controller.
* Power distribution.
* Receiver.
* GPS.
* Telemetry.
* Companion computer if required.
* Sensors.
* Payload.
* Wiring.
* Structural interfaces.

The fuselage should therefore be designed around the internal component architecture rather than only external appearance.

A useful design process is:

```text
Component List
      ↓
Component Dimensions
      ↓
Packaging Layout
      ↓
CG Analysis
      ↓
Fuselage Envelope
      ↓
Structural Shell
```

---

# 4.13 Internal Component Packaging

Before finalizing the fuselage, create a component layout.

For example:

```text
        FRONT
          ↓

┌─────────────────────────────┐
│       Sensor / Payload      │
├─────────────────────────────┤
│           Battery           │
├─────────────────────────────┤
│     Flight Controller       │
├─────────────────────────────┤
│ Power Distribution / ESCs    │
└─────────────────────────────┘

          REAR
           ↓
       Pusher Motor
```

This is only a conceptual arrangement.

The actual positions should be determined after considering:

* CG.
* Cooling.
* Wiring.
* Accessibility.
* Structural loads.
* Electromagnetic interference.
* Sensor fields of view.

---

# 4.14 Battery Placement

Battery position has a significant effect on CG.

The battery is often one of the heaviest individual components.

Therefore, its location should be adjustable during early testing.

A useful design feature is:

* Battery tray.
* Retention strap.
* Multiple mounting positions.
* Positive mechanical retention.
* Easy access.

The battery should not be allowed to move during flight.

---

# 4.15 Center of Gravity in CAD

The CAD model can be used to estimate the center of gravity if component masses and material properties are correctly defined.

For discrete components:

$$
x_{CG}
=
\frac{\sum m_ix_i}{\sum m_i}
$$

Similarly:

$$
y_{CG}
=
\frac{\sum m_iy_i}{\sum m_i}
$$

and:

$$
z_{CG}
=
\frac{\sum m_iz_i}{\sum m_i}
$$

The complete aircraft CG is therefore:

$$
\vec r_{CG}
=
\frac{\sum m_i\vec r_i}{\sum m_i}
$$

This is particularly useful because the CG is not determined by the fuselage geometry alone.

---

# 4.16 CG and Aerodynamic Reference

The preliminary design targeted approximately:

$$
25\%-30\%
$$

of mean aerodynamic chord as an initial CG reference.

This should not be treated as a universal requirement.

The final CG location depends on:

* Aircraft stability.
* Tail volume.
* Wing position.
* Aerodynamic center.
* Flight dynamics.
* Payload.
* Battery position.

The CAD model should therefore allow CG to be checked against the aerodynamic reference location.

---

# 4.17 VTOL Motor Placement

The four VTOL motors must be positioned carefully.

The arrangement should provide:

* Appropriate thrust distribution.
* Roll control authority.
* Pitch control authority.
* Yaw control authority where applicable.
* Structural support.
* Propeller clearance.
* Ground clearance.

A conceptual top view is:

```text
              FRONT
                ↑

          ○             ○
       VTOL Motor    VTOL Motor


              FUSELAGE


          ○             ○
       VTOL Motor    VTOL Motor

                ↓
               REAR
```

The exact positions should be determined through:

* Moment-arm analysis.
* CG location.
* Wing geometry.
* Structural requirements.
* Propeller clearance.

---

# 4.18 VTOL Motor Moment Arms

The effectiveness of a motor for attitude control depends partly on its distance from the aircraft CG.

The moment generated by a force is:

$$
M=F\times r
$$

where:

* \(M\) = moment.
* \(F\) = force.
* \(r\) = perpendicular distance from the reference point.

Therefore, moving a VTOL motor farther from the CG can increase the available control moment for the same thrust.

However, larger moment arms may increase:

* Structural loads.
* Overall dimensions.
* Weight.
* Drag.
* Wing bending requirements.

Therefore, motor placement is an optimization problem.

---

# 4.19 Propeller Clearance

Propeller clearance is a critical CAD requirement.

The propeller must have adequate clearance from:

* Wing.
* Fuselage.
* Tail.
* Ground.
* Other propellers.
* Structural members.
* Wiring.
* Payload.

The CAD model should include the complete propeller envelope.

A useful approach is to model the propeller as a simplified disk during early design.

```text
        ┌───────────┐
        │ PROPELLER │
        │   DISK    │
        └───────────┘
              ↓
        Clearance zone
```

This allows interference to be identified before physical construction.

---

# 4.20 Rear Pusher Integration

The forward-flight propulsion system is mounted at the rear of the fuselage.

The pusher motor mount must provide:

* Motor alignment.
* Structural stiffness.
* Propeller clearance.
* Load transfer.
* Vibration resistance.
* Cooling.
* Maintenance access.

The thrust axis should be clearly defined in CAD.

Ideally:

$$
\vec T_{pusher}
$$

should be aligned with the intended aircraft forward direction.

Any intentional thrust-axis offset should be documented because it creates additional moments.

---

# 4.21 Pusher Motor Mount Loads

The pusher motor creates several loads:

### Thrust load

$$
F_T=T
$$

### Torque reaction

The motor applies an equal and opposite reaction torque to the mount.

### Vibratory loading

The rotating propeller and motor can introduce vibration.

### Gyroscopic effects

A rotating propeller can generate gyroscopic moments during angular motion.

The mount must therefore be sufficiently stiff and securely attached.

---

# 4.22 Motor Mount Design

A motor mount can be designed using:

* Carbon-fiber plates.
* Aluminium.
* Plywood.
* Composite material.
* 3D-printed engineering polymer.
* Machined components.

Material selection depends on:

* Load.
* Mass.
* Manufacturing method.
* Temperature.
* Vibration.
* Cost.

The first CAD version should prioritize geometry and load paths.

Detailed material optimization can follow structural analysis.

---

# 4.23 Structural Load Paths

A good mechanical design should provide clear load paths.

For example:

```text
VTOL Motor
    ↓
Motor Mount
    ↓
Boom / Wing Structure
    ↓
Wing Spar
    ↓
Fuselage
```

For the pusher:

```text
Pusher Motor
    ↓
Motor Mount
    ↓
Fuselage / Rear Structure
    ↓
Main Airframe
```

For the wing:

```text
Aerodynamic Load
       ↓
Wing Skin
       ↓
Ribs
       ↓
Spar
       ↓
Wing Root
       ↓
Fuselage
```

The structural-analysis chapter will later evaluate these load paths quantitatively.

---

# 4.24 Wing Spar

The main wing spar is one of the most important structural components.

It carries a significant portion of the wing bending load.

A simplified beam representation is:

```text
Wing Tip                       Wing Tip
   │                              │
   │                              │
   └────────── SPAR ──────────────┘
                │
             Wing Root
                │
             Fuselage
```

The actual spar configuration may use:

* Single spar.
* Main spar + rear spar.
* Carbon tube.
* Carbon rectangular beam.
* Composite spar.
* Other structural architecture.

The selection should be based on structural analysis.

---

# 4.25 Wing Ribs

Wing ribs maintain the airfoil shape and transfer loads between the skin and spar.

They can also provide:

* Motor attachment interfaces.
* Wiring passages.
* Structural reinforcement.
* Assembly references.

The rib spacing should be selected based on:

* Skin stiffness.
* Manufacturing method.
* Expected load.
* Material.
* Wing geometry.

---

# 4.26 Wing Skin

The wing skin contributes to:

* Aerodynamic surface quality.
* Torsional stiffness.
* Load transfer.
* Protection of internal components.

Possible construction methods include:

* Foam with composite skin.
* Balsa/plywood.
* Carbon-fiber composite.
* Fiberglass composite.
* 3D-printed sections.
* Mixed construction.

The final manufacturing method should be chosen based on the project's resources and required performance.

---

# 4.27 Tail Design

The aircraft uses:

* Horizontal stabilizer.
* Vertical stabilizer.

The preliminary tail areas from Chapter 1 were:

$$
S_{HT}\approx0.079m^2
$$

and:

$$
S_{VT}\approx0.039m^2
$$

These are starting values.

The final tail geometry should be updated after:

* Aerodynamic analysis.
* CG determination.
* Stability analysis.
* Control-surface sizing.

---

# 4.28 Horizontal Tail

The horizontal tail contributes primarily to:

* Pitch stability.
* Pitch control.
* Trim.

The horizontal tail consists of:

* Stabilizer.
* Elevator or equivalent control surface.
* Structural attachment.

Its position should provide an adequate moment arm from the aircraft CG.

The horizontal tail volume coefficient is:

$$
V_H=
\frac{S_{HT}L_{HT}}
{S_{wing}MAC}
$$

where:

* \(S_{HT}\) = horizontal tail area.
* \(L_{HT}\) = horizontal tail moment arm.
* \(S_{wing}\) = wing area.
* \(MAC\) = mean aerodynamic chord.

---

# 4.29 Vertical Tail

The vertical tail contributes primarily to:

* Directional stability.
* Yaw control.

The vertical tail volume coefficient is:

$$
V_V=
\frac{S_{VT}L_{VT}}
{S_{wing}b}
$$

where:

* \(S_{VT}\) = vertical tail area.
* \(L_{VT}\) = vertical tail moment arm.
* \(S_{wing}\) = wing area.
* \(b\) = wing span.

The final vertical-tail design will later be connected to flight-dynamics analysis.

---

# 4.30 Control Surfaces

The CAD model should include the major aerodynamic control surfaces.

Depending on the final configuration, these may include:

* Ailerons.
* Elevator.
* Rudder.

The control surfaces require:

* Hinges.
* Servo mounting.
* Control horns.
* Pushrods or linkages.
* Servo access.
* Mechanical travel clearance.

The final control-surface dimensions will be established through flight-dynamics and control analysis.

---

# 4.31 Servo Installation

Servo mounting should be included in the CAD design.

A servo installation should provide:

* Rigid mounting.
* Easy replacement.
* Proper alignment.
* Sufficient control-surface travel.
* Protection from vibration.
* Appropriate cable routing.

The CAD model should allow the servo arm and linkage to move through the complete intended range without interference.

---

# 4.32 Mechanical Fasteners

Fasteners should be selected according to the expected load and manufacturing method.

Common choices include:

* Screws.
* Bolts.
* Nuts.
* Washers.
* Threaded inserts.
* Heat-set inserts.
* Captive nuts.

Fastener selection should consider:

* Load.
* Material compatibility.
* Vibration.
* Accessibility.
* Repeated assembly.
* Weight.

Critical structural joints should not rely on weak threads in unsuitable materials.

---

# 4.33 Manufacturing Constraints

CAD should be designed with the manufacturing process in mind.

For 3D printing, consider:

* Print orientation.
* Layer direction.
* Support requirements.
* Wall thickness.
* Infill.
* Heat resistance.

For CNC machining:

* Tool access.
* Minimum feature size.
* Material removal.
* Fixturing.

For composite construction:

* Laminate orientation.
* Mould geometry.
* Bonding surfaces.
* Fibre direction.

For foam construction:

* Cutting method.
* Reinforcement.
* Adhesive compatibility.
* Surface finishing.

---

# 4.34 Design for Assembly

The aircraft should be designed so that major components can be assembled and removed.

Important questions include:

* Can the battery be removed without disassembling the wing?
* Can the motor be replaced?
* Can the ESC be accessed?
* Can the flight controller be serviced?
* Can wiring be inspected?
* Can the wing be transported?
* Can damaged components be replaced?

A design that cannot be practically assembled or maintained is not a complete engineering design.

---

# 4.35 Modular Aircraft Design

A modular design can be useful for an experimental UAV.

Possible modules include:

```text
Main Fuselage
      │
 ┌────┼────────────┐
 │    │            │
Wing  Tail      Electronics
 │
VTOL Motors
 │
Propulsion
```

Modularity allows individual components to be changed without rebuilding the entire aircraft.

This is especially useful during development because:

* Motor configurations may change.
* Battery size may change.
* Sensors may change.
* Payload may change.
* Control electronics may change.

---

# 4.36 Electronics Packaging

The CAD design should reserve space for:

* Flight controller.
* GPS.
* Receiver.
* Power module.
* ESCs.
* Wiring.
* Sensors.
* Companion computer if required.
* Data storage.
* Communication hardware.

Electronics should have:

* Mechanical protection.
* Cooling where required.
* Vibration isolation where appropriate.
* Cable management.
* Service access.

---

# 4.37 Cooling

Heat-producing components include:

* Motors.
* ESCs.
* Voltage regulators.
* Power electronics.
* Computing hardware.

Cooling can be achieved through:

* Airflow.
* Ventilation openings.
* Heat sinks.
* Conductive mounting.
* Dedicated cooling paths.

The CAD design should avoid completely enclosing heat-producing components without considering heat rejection.

---

# 4.38 Wiring and Cable Management

Wiring should be considered during CAD rather than after construction.

The CAD model can include:

* Cable channels.
* Wire holes.
* Cable ties.
* Connector access.
* Protective sleeves.
* Separation between high-current and sensitive signal wiring.

A useful principle is:

```text
Power wiring
     ↓
Short and protected

Signal wiring
     ↓
Separated and organized
```

The exact electrical architecture will be developed further in the electronics chapter.

---

# 4.39 Sensor Mounting

Future perception and navigation systems may require sensors such as:

* Cameras.
* Distance sensors.
* LiDAR.
* Optical-flow sensors.
* GPS antennas.
* Other navigation sensors.

The CAD model should reserve mounting locations.

Sensor placement must consider:

* Field of view.
* Obstruction.
* Vibration.
* Propeller interference.
* Sunlight exposure.
* Structural mounting.
* Cable routing.

Sensor selection itself will be developed in later chapters.

---

# 4.40 Payload Integration

The aircraft should have a defined payload interface if payload capability is part of the mission.

The payload location affects:

* Mass.
* CG.
* Aerodynamic drag.
* Structural loading.
* Power consumption.

Therefore:

$$
CG=f(m_{payload},x_{payload})
$$

A payload mounting point should be structurally connected to the primary airframe.

---

# 4.41 Landing Loads

The aircraft must survive landing loads.

Landing loads may be transferred through:

* Landing gear.
* Fuselage.
* Motor booms.
* Wing structure.

The design should consider:

* Vertical impact.
* Forward motion.
* Side loads.
* Uneven landing.
* Hard landing.

The landing gear geometry should provide adequate propeller and fuselage clearance.

---

# 4.42 VTOL Landing Gear Clearance

During vertical landing, the propellers must remain clear of the ground.

Therefore, the CAD model should check:

$$
h_{propeller}>h_{ground}
$$

with an appropriate safety margin.

The landing gear should also avoid interfering with:

* Propeller rotation.
* Motor mounts.
* Payload.
* Sensors.

This should be verified in the assembled CAD model.

---

# 4.43 CAD Assembly Structure

A useful CAD assembly structure is:

```text
VTOL_UAV_Assembly
│
├── Fuselage
│   ├── Nose
│   ├── Center Body
│   └── Rear Body
│
├── Main Wing
│   ├── Left Wing
│   ├── Right Wing
│   ├── Spar
│   └── Control Surfaces
│
├── VTOL System
│   ├── Motor 1
│   ├── Motor 2
│   ├── Motor 3
│   └── Motor 4
│
├── Pusher System
│   ├── Rear Motor Mount
│   ├── Motor
│   └── Propeller
│
├── Tail
│   ├── Horizontal Stabilizer
│   ├── Elevator
│   ├── Vertical Stabilizer
│   └── Rudder
│
├── Electronics
│   ├── Battery
│   ├── Flight Controller
│   ├── ESCs
│   └── Sensors
│
└── Landing Gear
```

The actual CAD file structure may differ depending on the chosen CAD software.

---

# 4.44 CAD Naming Convention

Consistent naming becomes important as the project grows.

A possible convention is:

```text
UAV_MainAssembly
UAV_Fuselage
UAV_MainWing_Left
UAV_MainWing_Right
UAV_HorizontalTail
UAV_VerticalTail
UAV_VTOL_MotorMount_FL
UAV_VTOL_MotorMount_FR
UAV_VTOL_MotorMount_RL
UAV_VTOL_MotorMount_RR
UAV_PusherMotorMount
UAV_BatteryTray
UAV_ElectronicsTray
```

The naming system should remain consistent throughout CAD, simulation, drawings, and manufacturing files.

---

# 4.45 Design Revision Control

CAD designs change frequently.

A useful revision system is:

```text
REV A
Initial concept

REV B
Updated wing geometry

REV C
Updated motor mounts

REV D
Updated battery position

REV E
Structural modifications

REV F
Manufacturing-ready design
```

Each major revision should have a reason.

For example:

| Revision | Change              | Reason                 |
| -------- | ------------------- | ---------------------- |
| A        | Initial CAD         | Concept                |
| B        | Wing updated        | Aerodynamic analysis   |
| C        | Motor mount updated | Propulsion integration |
| D        | Battery moved       | CG adjustment          |
| E        | Spar reinforced     | Structural analysis    |
| F        | Finalized geometry  | Manufacturing          |

This creates engineering traceability.

---

# 4.46 CAD Verification Checklist

Before manufacturing, check:

### Geometry

* [ ] Wing dimensions verified.
* [ ] Airfoil imported correctly.
* [ ] Tail dimensions verified.
* [ ] Fuselage dimensions verified.
* [ ] Motor locations verified.
* [ ] Propeller clearance verified.

### Mass properties

* [ ] Material densities assigned.
* [ ] Component masses included.
* [ ] CG calculated.
* [ ] CG location compared with design target.

### Propulsion

* [ ] Four VTOL motors included.
* [ ] Rear pusher motor included.
* [ ] Motor mounts checked.
* [ ] Propeller envelopes checked.
* [ ] Ground clearance checked.

### Structure

* [ ] Wing spar included.
* [ ] Motor loads have load paths.
* [ ] Tail attachment checked.
* [ ] Landing loads considered.
* [ ] Fasteners defined.

### Manufacturing

* [ ] Parts can be manufactured.
* [ ] Parts can be assembled.
* [ ] Fasteners are accessible.
* [ ] Components can be replaced.
* [ ] Wiring can be routed.

---

# 4.47 CAD-to-Analysis Workflow

The CAD model should feed later engineering analyses.

```text
CAD Geometry
      ↓
Mass Properties
      ↓
CG
      ↓
Structural Model
      ↓
Finite Element Analysis
      ↓
Stress / Deformation
      ↓
Design Modification
      ↓
Updated CAD
```

Similarly:

```text
CAD Geometry
      ↓
Aerodynamic Geometry
      ↓
Aerodynamic Analysis
      ↓
Aerodynamic Loads
      ↓
Structural Analysis
```

And:

```text
CAD Geometry
      ↓
Component Locations
      ↓
CG / Moment Arms
      ↓
Flight Dynamics
      ↓
Control System
```

Thus CAD becomes an important central model of the aircraft.

---

# 4.48 Digital Mock-Up

Before manufacturing, the complete aircraft should be assembled virtually.

The digital mock-up should include:

* Wing.
* Fuselage.
* Tail.
* VTOL motors.
* Pusher motor.
* Propellers.
* Battery.
* Electronics.
* Payload.
* Landing gear.

The purpose is to identify problems before physical fabrication.

Examples include:

* Component collisions.
* Insufficient clearance.
* Incorrect CG.
* Inaccessible fasteners.
* Wiring conflicts.
* Motor interference.
* Sensor obstruction.

---

# 4.49 Interference Checking

CAD interference checking should be performed for:

* Moving control surfaces.
* Propeller envelopes.
* Motor mounts.
* Landing gear.
* Battery removal.
* Electronics installation.
* Wing assembly.

For moving components, check the entire motion range rather than only the neutral position.

For example:

```text
Elevator
   ↓
Neutral
   ↓
Maximum Up
   ↓
Maximum Down
```

The control surface should not collide with nearby structures at any intended position.

---

# 4.50 Weight Estimation From CAD

The CAD model can provide an improved estimate of aircraft mass.

The preliminary mass budget from Chapter 1 was:

| Component                 | Preliminary Mass |
| ------------------------- | ---------------: |
| Structure, wing and booms |          1.50 kg |
| Battery                   |          1.40 kg |
| Propulsion/hardware       |          0.85 kg |
| Avionics/electronics      |          0.30 kg |
| Payload                   |          0.90 kg |
| **Total**                 |      **4.95 kg** |

As the CAD model becomes more detailed, these estimates should be replaced by actual component masses.

The design should be continuously checked against the MTOW assumption.

---

# 4.51 Mass Budget Updating

The mass budget should evolve as the project develops.

For example:

```text
Preliminary Estimate
        ↓
CAD Estimate
        ↓
Purchased Component Mass
        ↓
Manufactured Part Mass
        ↓
Assembled Aircraft Mass
        ↓
Measured Flight Mass
```

The final measured mass should be compared with the original design assumption.

This comparison is valuable because increased mass affects:

* Stall speed.
* VTOL thrust requirement.
* Cruise lift coefficient.
* Cruise drag.
* Battery endurance.
* Structural loading.

---

# 4.52 Sensitivity of Design to Mass

If aircraft mass increases:

$$
W=mg
$$

therefore weight increases.

The VTOL thrust requirement becomes:

$$
T_{VTOL}=kW
$$

Therefore, a heavier aircraft requires more VTOL thrust.

The stall speed also changes:

$$
V_{stall}
=
\sqrt{
\frac{2W}
{\rho S C_{Lmax}}
}
$$

Therefore:

$$
W\uparrow
\Rightarrow
V_{stall}\uparrow
$$

if all other variables remain unchanged.

This demonstrates why CAD mass control is important.

---

# 4.53 Mechanical Design Decision Log

Important CAD decisions should be recorded.

A useful format is:

| ID      | Decision               | Reason           | Evidence               | Status      |
| ------- | ---------------------- | ---------------- | ---------------------- | ----------- |
| CAD-001 | Wing mounting position | CG and structure | CAD analysis           | Preliminary |
| CAD-002 | Battery location       | CG adjustment    | Mass properties        | Preliminary |
| CAD-003 | Motor mount geometry   | Thrust load      | Propulsion requirement | Preliminary |
| CAD-004 | Spar configuration     | Wing loads       | Structural analysis    | TBD         |
| CAD-005 | Pusher mount           | Rear propulsion  | Configuration          | Selected    |

This creates traceability between engineering analysis and CAD.

---

# 4.54 What Should Go Into the Results File?

The separate file:

```text
04_CAD_and_Mechanical_Design/
└── Results.md
```

should contain the actual CAD results.

For example:

```markdown
# CAD and Mechanical Design — Results

## 1. Final CAD Configuration

Document the final aircraft geometry.

## 2. Aircraft Dimensions

| Parameter | Preliminary | Final |
|---|---:|---:|
| Wing area | 0.428 m² | TBD |
| Span | 1.73 m | TBD |
| Mean chord | 0.247 m | TBD |
| Overall length | TBD | TBD |
| MTOW | 5 kg | TBD |

## 3. Mass Properties

| Component | Mass |
|---|---:|
| Structure | TBD |
| Battery | TBD |
| Propulsion | TBD |
| Electronics | TBD |
| Payload | TBD |
| Total | TBD |

## 4. CG Location

- X CG: TBD
- Y CG: TBD
- Z CG: TBD

## 5. Motor Locations

Document the final VTOL and pusher motor coordinates.

## 6. Structural Configuration

Document:
- Spar
- Ribs
- Motor mounts
- Fuselage structure
- Tail mounts

## 7. Interference Checks

Record the results of:
- Propeller clearance
- Control-surface movement
- Battery removal
- Electronics installation

## 8. CAD Images

Add screenshots/renders of:
- Complete aircraft
- Wing
- Fuselage
- Motor mounts
- Internal layout

## 9. Design Changes

Document major CAD revisions.

## 10. Observations

Record what was discovered during CAD development.

## 11. Design Decision

Document the final mechanical configuration.

## 12. Limitations

Record assumptions and unresolved issues.
```

---

# 4.55 Recommended CAD Evidence

The GitHub repository should eventually contain evidence such as:

```text
CAD/
├── Assembly/
├── Parts/
├── Drawings/
├── STEP/
├── STL/
└── Screenshots/
```

The exact structure can be created later when the CAD files are ready.

Useful evidence includes:

* Isometric view.
* Top view.
* Side view.
* Front view.
* Internal component layout.
* CG visualization.
* Motor mounting detail.
* Wing structure.
* Propeller clearance.
* Exploded assembly.
* Manufacturing drawings.

---

# 4.56 Engineering Evidence Rather Than Only Renders

A professional engineering project should not contain only attractive CAD renders.

The important evidence is:

```text
Requirement
    ↓
Dimension
    ↓
CAD Feature
    ↓
Analysis
    ↓
Modification
    ↓
Final Geometry
```

For example:

> The battery was moved because the original CAD mass properties placed the CG outside the preliminary target range.

That is more valuable engineering evidence than simply showing a rendered aircraft.

---

# 4.57 Connection to Structural Analysis

The CAD geometry developed in this chapter becomes the input for structural analysis.

The next structural workflow is:

```text
CAD
 ↓
Material Properties
 ↓
Loads
 ↓
Boundary Conditions
 ↓
Mesh
 ↓
FEA
 ↓
Stress
 ↓
Deformation
 ↓
Factor of Safety
 ↓
Design Revision
```

The structural analysis should therefore use the actual mechanical architecture rather than an unrelated simplified geometry whenever practical.

---

# 4.58 Connection to Flight Dynamics

The CAD model also provides geometric information for flight dynamics.

Important parameters include:

* Mass.
* CG.
* Moment of inertia.
* Wing geometry.
* Tail geometry.
* Motor locations.
* Thrust moment arms.

These influence the equations of motion.

For example, the rotational equation around an axis can be represented generally as:

$$
I\dot{\omega}=M
$$

where:

* \(I\) = moment of inertia.
* \(\dot{\omega}\) = angular acceleration.
* \(M\) = applied moment.

Therefore, accurate mass distribution from CAD becomes important later.

---

# 4.59 Connection to Control

The control system will require knowledge of:

* Motor locations.
* Thrust directions.
* Control-surface geometry.
* Servo locations.
* Moment arms.
* Aircraft mass.
* Moments of inertia.

For example, the VTOL motors generate forces that can produce moments about the CG:

$$
\vec M=\vec r\times\vec F
$$

where:

* \(\vec r\) = position vector from CG to motor.
* \(\vec F\) = thrust force.

Therefore, motor placement in CAD directly affects control authority.

---

# 4.60 CAD Development Philosophy

The CAD model should evolve with the engineering process.

It should not be treated as a one-time activity.

A practical cycle is:

```text
Design
 ↓
Analyze
 ↓
Identify Problem
 ↓
Modify CAD
 ↓
Re-analyze
 ↓
Manufacture
 ↓
Test
 ↓
Update CAD
```

This is normal engineering development.

The final CAD model should represent the configuration that was actually built and tested.

---

# 4.61 Final CAD Checklist

Before considering the mechanical design ready for fabrication:

### Aircraft

* [ ] Configuration confirmed.
* [ ] Wing geometry confirmed.
* [ ] Tail geometry confirmed.
* [ ] Fuselage geometry confirmed.

### Propulsion

* [ ] Four VTOL motor locations confirmed.
* [ ] Rear pusher location confirmed.
* [ ] Propeller clearance checked.
* [ ] Motor mounts designed.

### Mass

* [ ] Component masses entered.
* [ ] Total mass estimated.
* [ ] CG calculated.
* [ ] CG target checked.

### Structure

* [ ] Wing spar designed.
* [ ] Motor load paths defined.
* [ ] Tail attachment defined.
* [ ] Landing loads considered.

### Electronics

* [ ] Battery location defined.
* [ ] ESC locations defined.
* [ ] Flight controller location defined.
* [ ] Wiring paths defined.
* [ ] Sensor locations reserved.

### Manufacturing

* [ ] Manufacturing process selected.
* [ ] Parts manufacturable.
* [ ] Fasteners accessible.
* [ ] Assembly sequence defined.
* [ ] Replacement/maintenance considered.

---

# 4.62 Summary

Chapter 4 converts the theoretical and analytical work from the previous chapters into a physical aircraft design.

The major CAD and mechanical design elements are:

* Fixed-wing geometry.
* Fuselage.
* Four VTOL motor mounts.
* Rear pusher motor mount.
* Wing structure.
* Tail structure.
* Landing gear.
* Battery compartment.
* Electronics compartment.
* Sensor mounting.
* Payload mounting.
* Wiring paths.
* Manufacturing interfaces.

The CAD model should maintain traceability to the engineering requirements established in the earlier chapters.

The overall relationship is:

$$
\boxed{
Requirements
\rightarrow
Sizing
\rightarrow
Aerodynamics
\rightarrow
Propulsion
\rightarrow
CAD
\rightarrow
Structural\ Analysis
\rightarrow
Testing
}
$$

The CAD model is therefore not simply a drawing of the aircraft.

It is the physical representation of the engineering decisions made throughout the project.

---

# 4.63 Key Engineering Lessons

1. **CAD should be driven by engineering requirements rather than appearance.**
2. **Component placement affects mass distribution and CG.**
3. **Motor placement affects structural loads and control authority.**
4. **Propeller clearance must be checked before fabrication.**
5. **Battery placement should allow CG adjustment.**
6. **Load paths should be identified before detailed structural analysis.**
7. **Manufacturing constraints should be considered during CAD development.**
8. **The complete aircraft should be checked as a digital assembly.**
9. **Mass properties from CAD should be compared with actual component masses.**
10. **CAD revisions should be documented rather than overwritten without explanation.**
11. **The final CAD model should match the physical aircraft that is eventually built.**
12. **CAD provides important geometry and mass information for structural analysis, flight dynamics, and control.**

The next chapter will use the mechanical geometry developed here to investigate whether the aircraft structure can safely withstand aerodynamic, propulsion, and landing loads.
