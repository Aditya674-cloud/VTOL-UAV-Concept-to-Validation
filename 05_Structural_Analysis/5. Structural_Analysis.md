# Chapter 5 — Structural Analysis and Structural Design

## 5.1 Purpose of This Chapter

The purpose of structural analysis is to determine whether the aircraft structure can safely withstand the loads expected during operation.

The previous chapters established:

* Aircraft configuration.
* Aircraft mass.
* Wing geometry.
* Tail geometry.
* VTOL propulsion requirements.
* Rear pusher propulsion.
* Preliminary CAD geometry.

This chapter converts those requirements into structural loads and evaluates:

* Wing strength.
* Wing deflection.
* Fuselage strength.
* Motor-mount loads.
* VTOL boom loads.
* Tail loads.
* Landing loads.
* Fastener loads.
* Material selection.
* Stress.
* Strain.
* Deformation.
* Factor of safety.

The general engineering process is:

```text
Aircraft Requirements
        ↓
CAD Geometry
        ↓
Load Identification
        ↓
Load Cases
        ↓
Material Selection
        ↓
Boundary Conditions
        ↓
FEA Model
        ↓
Stress / Deformation
        ↓
Factor of Safety
        ↓
Design Modification
        ↓
Structural Validation
```

The objective is not simply to obtain a colorful finite-element-analysis plot.

The objective is to understand **how loads travel through the aircraft and whether the structure is adequate for those loads**.

---

# 5.2 Structural Design Philosophy

A UAV structure must satisfy several competing requirements.

It must be:

* Strong enough.
* Stiff enough.
* Lightweight.
* Manufacturable.
* Repairable.
* Resistant to vibration.
* Capable of carrying propulsion loads.
* Capable of carrying aerodynamic loads.

A structure that is extremely strong but unnecessarily heavy can reduce aircraft performance.

Therefore, structural design is an optimization problem.

The simplified design objective can be represented as:

$$
\text{Minimum Mass}
$$

subject to:

$$
\sigma_{max}<\sigma_{allowable}
$$

and:

$$
\delta<\delta_{allowable}
$$

and:

$$
FOS>FOS_{required}
$$

where:

* \(\sigma_{max}\) = maximum stress.
* \(\sigma_{allowable}\) = allowable material stress.
* \(\delta\) = structural deformation.
* \(FOS\) = factor of safety.

---

# 5.3 Structural Components

The major structural components of the aircraft include:

```text
VTOL UAV Structure
│
├── Fuselage
│
├── Main Wing
│   ├── Spar
│   ├── Ribs
│   └── Skin
│
├── VTOL Motor Supports
│   ├── Front-left
│   ├── Front-right
│   ├── Rear-left
│   └── Rear-right
│
├── Rear Pusher Motor Mount
│
├── Horizontal Tail
│
├── Vertical Tail
│
├── Landing Gear
│
└── Fasteners / Joints
```

Each component experiences different types of loading.

---

# 5.4 Types of Structural Loads

The aircraft can experience:

* Tension.
* Compression.
* Bending.
* Shear.
* Torsion.
* Bearing loads.
* Impact loads.
* Vibratory loads.

In real flight, several of these occur simultaneously.

For example, the wing may experience:

```text
Aerodynamic Lift
       ↓
     Bending
       +
     Shear
       +
    Torsion
```

A motor mount may experience:

```text
Motor Thrust
      ↓
   Bending
      +
    Shear
      +
   Torque
      +
  Vibration
```

---

# 5.5 Newton's Second Law

The fundamental relationship for structural loading is:

$$
F=ma
$$

where:

* \(F\) = force.
* \(m\) = mass.
* \(a\) = acceleration.

For an aircraft maneuvering under a load factor \(n\):

$$
L=nW
$$

where:

* \(L\) = aerodynamic lift.
* \(W\) = aircraft weight.
* \(n\) = load factor.

Therefore, the structural loads can be significantly greater than the aircraft's static weight.

---

# 5.6 Aircraft Weight

From Chapter 1:

$$
m=5kg
$$

and:

$$
W=mg
$$

Therefore:

$$
W=5(9.81)
$$

$$
\boxed{W=49.05N}
$$

This represents approximately \(1g\) vertical loading under the preliminary mass assumption.

The actual structural design should eventually use the measured aircraft mass.

---

# 5.7 Load Factor

The load factor is:

$$
n=\frac{L}{W}
$$

Therefore:

$$
L=nW
$$

For example, if a structural load case uses:

$$
n=3
$$

then:

$$
L=3(49.05)
$$

$$
\boxed{L=147.15N}
$$

This does not mean that the aircraft continuously experiences this load.

It represents a selected design load case.

The final load factors should be justified using the aircraft's intended operating envelope and applicable design requirements.

---

# 5.8 Limit Load and Ultimate Load

Structural design commonly distinguishes between:

### Limit load

The maximum expected operational load.

### Ultimate load

A higher load used to provide structural margin.

A simplified relationship can be written as:

$$
F_{ultimate}
=
F_{limit}\times FS
$$

where \(FS\) is the required ultimate factor.

The exact factor should be selected according to the applicable design standard or project requirements.

The project should document which factor is used rather than selecting one arbitrarily.

---

# 5.9 Factor of Safety

Factor of safety can be expressed as:

$$
FOS=
\frac{\text{Failure Load}}
{\text{Applied Load}}
$$

For stress-based analysis:

$$
FOS=
\frac{\sigma_{failure}}
{\sigma_{applied}}
$$

A simplified allowable-stress relationship is:

$$
\sigma_{allowable}
=
\frac{\sigma_{failure}}{FOS_{required}}
$$

The required factor of safety depends on:

* Material.
* Load uncertainty.
* Manufacturing quality.
* Failure consequences.
* Applicable standards.
* Type of structure.

Therefore, the project should document the chosen value and its justification.

---

# 5.10 Stress

Stress describes the internal force per unit area.

For a simple axial load:

$$
\sigma=
\frac{F}{A}
$$

where:

* \(\sigma\) = normal stress.
* \(F\) = axial force.
* \(A\) = cross-sectional area.

The SI unit is:

$$
Pa=N/m^2
$$

Engineering results are commonly reported in:

$$
MPa
$$

---

# 5.11 Strain

Strain represents deformation relative to the original dimension.

For axial deformation:

$$
\epsilon=
\frac{\Delta L}{L}
$$

where:

* \(\epsilon\) = strain.
* \(\Delta L\) = change in length.
* \(L\) = original length.

Strain is dimensionless.

---

# 5.12 Hooke's Law

For a linearly elastic material:

$$
\sigma=E\epsilon
$$

where:

* \(E\) = Young's modulus.
* \(\sigma\) = stress.
* \(\epsilon\) = strain.

This relationship is valid within the appropriate elastic range.

The value of \(E\) depends on the material.

---

# 5.13 Shear Stress

For a simplified average shear load:

$$
\tau=
\frac{F}{A}
$$

where:

* \(\tau\) = shear stress.
* \(F\) = shear force.
* \(A\) = effective shear area.

Actual shear-stress distributions depend on the geometry and loading condition.

---

# 5.14 Bending Stress

Bending is one of the most important loading conditions for the UAV wing.

The simplified bending-stress equation is:

$$
\sigma=
\frac{My}{I}
$$

where:

* \(M\) = bending moment.
* \(y\) = distance from neutral axis.
* \(I\) = second moment of area.

The maximum bending stress occurs at the outermost fibers:

$$
\sigma_{max}
=
\frac{Mc}{I}
$$

where \(c\) is the maximum distance from the neutral axis.

---

# 5.15 Bending Moment

A force acting at a distance from a reference point produces a moment:

$$
M=Fr
$$

where:

* \(F\) = force.
* \(r\) = moment arm.

For a wing, aerodynamic lift acts over the wing surface and creates bending moments that are transferred toward the wing root.

A simplified representation is:

```text
Wing Tip
   ↑ Lift
   │
   │
   ↑ Lift
   │
   │
   └─────────────────┐
                     │
                     │ Wing Root
                     │
                  Fuselage
```

The wing root generally experiences significant structural loading.

---

# 5.16 Wing as a Beam

For preliminary structural analysis, the wing can be approximated as a beam.

A simplified cantilever representation is:

```text
Fuselage
   │
   │████████████████───────────
   │             Wing
   │
 Fixed          Distributed Load
 Support              ↑ ↑ ↑ ↑ ↑
```

The wing root acts approximately as the fixed region.

The aerodynamic loading is distributed along the wing.

The resulting:

* Shear force.
* Bending moment.

can be evaluated along the span.

---

# 5.17 Distributed Wing Loading

A simple first approximation is to represent total lift as a distributed load.

For level flight:

$$
L\approx W
$$

For a selected load factor:

$$
L=nW
$$

If the lift is approximated as uniformly distributed:

$$
w=
\frac{L}{b}
$$

where:

* \(w\) = load per unit span.
* \(b\) = wing span.

This is a simplified approximation.

The actual lift distribution is not uniform.

---

# 5.18 Elliptical Lift Distribution

A more realistic idealized lift distribution is approximately elliptical for certain wing configurations.

Conceptually:

```text
Lift
 ↑
 │          ______
 │        /        \
 │      /            \
 │____/                \____
 └──────────────────────────→ Span
```

The actual UAV wing loading depends on:

* Planform.
* Airfoil.
* Aspect ratio.
* Twist.
* Angle of attack.
* Flight condition.
* Propeller interference.

The structural model should use an appropriate loading assumption.

---

# 5.19 Wing Shear Force

The distributed aerodynamic load creates a shear-force distribution.

For a simplified beam:

$$
\frac{dV}{dx}=-w(x)
$$

where:

* \(V\) = shear force.
* \(w(x)\) = distributed load.

The wing root generally experiences the highest total shear force.

---

# 5.20 Wing Bending Moment

The relationship between bending moment and shear force is:

$$
\frac{dM}{dx}=V(x)
$$

Therefore, once the loading distribution is known, the bending moment can be determined.

The wing-root bending moment is particularly important for structural design.

---

# 5.21 Wing Spar Design

The main spar carries a large portion of the wing bending load.

A spar may consist of:

* Carbon-fiber tube.
* Carbon-fiber rectangular beam.
* Composite beam.
* Aluminium section.
* Wood structure.
* Hybrid construction.

The choice depends on:

* Required stiffness.
* Required strength.
* Mass.
* Manufacturing method.
* Cost.

---

# 5.22 Spar Section Properties

Important geometric properties include:

### Area

$$
A
$$

### Second moment of area

$$
I
$$

### Section modulus

$$
Z=
\frac{I}{c}
$$

The bending stress can then be written as:

$$
\sigma=
\frac{M}{Z}
$$

A larger section modulus reduces bending stress for the same applied moment.

---

# 5.23 Wing Torsion

The wing can also experience torsion.

Torsion may be caused by:

* Aerodynamic center offset.
* Control-surface forces.
* Propeller interference.
* Asymmetric loading.
* Structural geometry.

A simplified torsion relationship is:

$$
\tau=
\frac{Tr}{J}
$$

where:

* \(T\) = applied torque.
* \(r\) = radial distance.
* \(J\) = polar moment of inertia.

Actual composite or thin-walled structures require more appropriate torsional models.

---

# 5.24 Why Wing Stiffness Matters

A wing can be strong enough against failure but still too flexible.

Excessive deformation can cause:

* Aerodynamic shape changes.
* Control problems.
* Flutter-related concerns.
* Propeller clearance changes.
* Reduced handling quality.

Therefore, structural design should evaluate both:

$$
\boxed{\text{Strength}}
$$

and:

$$
\boxed{\text{Stiffness}}
$$

---

# 5.25 Deflection

For a simple cantilever beam with a point load at the end:

$$
\delta=
\frac{FL^3}{3EI}
$$

where:

* \(\delta\) = tip deflection.
* \(F\) = applied load.
* \(L\) = beam length.
* \(E\) = Young's modulus.
* \(I\) = second moment of area.

This is only a simplified beam relationship.

The actual wing should be analyzed using its distributed load and structural geometry.

---

# 5.26 VTOL Motor Loads

Each VTOL motor must support a significant thrust force.

From Chapter 3:

$$
T_{motor}\approx22.1N
$$

as the preliminary required thrust per motor at the selected total thrust-to-weight target.

The motor mount therefore experiences:

* Thrust force.
* Bending.
* Torque.
* Vibration.

A simplified motor-mount moment is:

$$
M=T r
$$

where \(r\) is the distance between the thrust line and the structural support.

---

# 5.27 VTOL Motor Mount Load Path

The load should travel through a clearly defined structure:

```text
VTOL Propeller
      ↓
    Motor
      ↓
 Motor Mount
      ↓
 Boom / Reinforcement
      ↓
 Wing Spar / Main Structure
      ↓
 Fuselage
```

A motor should not be attached to a weak skin panel without an adequate load path.

---

# 5.28 VTOL Motor Torque

The motor applies a reaction torque to the structure.

The magnitude depends on:

* Motor power.
* Motor rotational speed.
* Propeller loading.

Using:

$$
P=\tau\omega
$$

the approximate shaft torque is:

$$
\tau=
\frac{P}{\omega}
$$

This torque must be considered in motor-mount design.

---

# 5.29 Asymmetric VTOL Loading

The aircraft should not be analyzed only under the assumption that all four motors produce equal thrust.

Potential asymmetric conditions include:

* One motor producing reduced thrust.
* One motor shutting down.
* Unequal motor output.
* Control input.
* Wind disturbance.

For example:

```text
Motor 1: HIGH
Motor 2: HIGH
Motor 3: LOW
Motor 4: HIGH
```

This can create an asymmetric structural load.

The structural consequences should be investigated where relevant.

---

# 5.30 Rear Pusher Motor Structural Load

The rear-mounted pusher motor produces a forward thrust force:

$$
T_{pusher}
$$

The motor mount must transfer this force into the airframe.

The load path is approximately:

```text
Rear Pusher Motor
       ↓
Motor Mount
       ↓
Rear Fuselage Structure
       ↓
Main Fuselage
       ↓
Wing / Central Structure
```

The mount should also resist:

* Motor torque.
* Propeller vibration.
* Gyroscopic loads.
* Dynamic loads.

---

# 5.31 Pusher Propeller Clearance

The rear propeller must remain clear of:

* Fuselage.
* Tail.
* Ground.
* Structural members.

The CAD model should include the complete propeller envelope.

A clearance check should be performed for:

* Static aircraft.
* Landing attitude.
* Possible pitch attitude.
* Possible structural deformation.

---

# 5.32 Tail Loads

The horizontal and vertical tails experience aerodynamic forces.

For the horizontal tail:

$$
L_{HT}
=
\frac12\rho V^2S_{HT}C_{L,HT}
$$

For the vertical tail:

$$
Y_{VT}
=
\frac12\rho V^2S_{VT}C_{Y,VT}
$$

where:

* \(L_{HT}\) = horizontal-tail aerodynamic force.
* \(Y_{VT}\) = side force on vertical tail.

These forces create moments about the aircraft CG.

---

# 5.33 Tail Structural Load Path

A simplified tail load path is:

```text
Tail Aerodynamic Load
        ↓
Tail Surface
        ↓
Tail Spar / Internal Structure
        ↓
Tail Mount
        ↓
Fuselage
```

The tail attachment should be checked carefully because the tail force acts at a significant moment arm from the CG.

---

# 5.34 Fuselage Loads

The fuselage may experience:

* Wing loads.
* Tail loads.
* Motor loads.
* Landing loads.
* Payload loads.
* Battery loads.
* Local attachment loads.

The fuselage therefore acts as an important load-transfer structure.

A simplified load path is:

```text
Wing
 ↓
Wing Root
 ↓
Fuselage
 ↓
Tail / Landing Gear / Other Structures
```

---

# 5.35 Battery and Electronics Structural Restraint

The battery must be mechanically restrained.

A battery that moves during flight can:

* Shift the CG.
* Damage wiring.
* Damage electronics.
* Become a structural hazard.

The battery mounting system should withstand the expected acceleration loads.

A simplified inertial force is:

$$
F=ma
$$

For a selected load factor \(n\):

$$
F_{battery}=nm_{battery}g
$$

This force should be considered when designing the battery tray and retention system.

---

# 5.36 Payload Mounting

The payload should be treated as a structural mass.

Its mounting system should withstand:

* Flight acceleration.
* Landing loads.
* Vibration.
* Maneuvering.

The payload location should also be included in CG calculations.

---

# 5.37 Landing Loads

Landing can create higher transient loads than normal level flight.

Potential landing cases include:

* Normal VTOL landing.
* Hard landing.
* Uneven landing.
* Forward-motion landing.
* Side loading.

A simplified vertical landing load can be represented using:

$$
F=nmg
$$

where \(n\) is the selected landing load factor.

The actual landing impact depends on:

* Vertical velocity.
* Landing gear stiffness.
* Ground contact time.
* Surface characteristics.
* Aircraft attitude.

---

# 5.38 Landing Gear Design

Landing gear should:

* Support aircraft weight.
* Absorb landing loads.
* Maintain ground clearance.
* Protect propellers.
* Protect fuselage.
* Remain structurally attached.

The design should consider both strength and deformation.

---

# 5.39 Material Selection

Potential UAV structural materials include:

* Aluminium.
* Carbon-fiber composite.
* Fiberglass composite.
* Plywood.
* Balsa.
* Foam.
* Engineering polymers.
* 3D-printed thermoplastics.

Material selection should consider:

* Density.
* Young's modulus.
* Tensile strength.
* Compressive strength.
* Shear strength.
* Fatigue performance.
* Temperature resistance.
* Manufacturability.

---

# 5.40 Density

Material density is:

$$
\rho_m=
\frac{m}{V}
$$

where:

* \(\rho_m\) = material density.
* \(m\) = mass.
* \(V\) = volume.

For an aircraft, low density is attractive because structural mass directly affects aircraft performance.

However, density alone is not enough.

---

# 5.41 Specific Strength

A useful material comparison metric is specific strength:

$$
\text{Specific Strength}
=
\frac{\sigma_{strength}}{\rho_m}
$$

This compares strength relative to material density.

A material with high specific strength can be attractive for lightweight structures.

---

# 5.42 Specific Stiffness

Similarly:

$$
\text{Specific Stiffness}
=
\frac{E}{\rho_m}
$$

where:

* \(E\) = Young's modulus.
* \(\rho_m\) = density.

For lightweight aircraft structures, stiffness-to-weight ratio can be particularly important.

---

# 5.43 Aluminium

Aluminium may be useful for:

* Motor mounts.
* Brackets.
* Structural joints.
* Landing gear.
* Mechanical interfaces.

Advantages include:

* Good machinability.
* Good strength-to-weight ratio.
* Easy availability.
* Predictable material properties.

Potential disadvantages include:

* Higher density than many composites.
* Potential fatigue concerns.
* Need for suitable joints.

---

# 5.44 Carbon-Fiber Composite

Carbon-fiber composite can provide high stiffness and low mass.

Potential applications include:

* Wing spars.
* Booms.
* Plates.
* Motor supports.
* Fuselage reinforcement.

However, composites are anisotropic.

This means their properties depend strongly on:

* Fibre direction.
* Laminate orientation.
* Layer sequence.
* Manufacturing quality.

Therefore, isotropic metal assumptions should not automatically be applied to composite structures.

---

# 5.45 3D-Printed Components

3D printing can be useful for:

* Sensor mounts.
* Electronics trays.
* Covers.
* Small brackets.
* Cable guides.
* Prototyping.

Printed parts can have direction-dependent strength because of the layer structure.

Therefore, print orientation must be considered.

A part that is strong in one loading direction may be weaker in another.

---

# 5.46 Joints

Structural joints can often become critical locations.

Examples include:

* Wing-to-fuselage joints.
* Motor mounts.
* Spar connections.
* Tail mounts.
* Landing gear mounts.

A joint should be analyzed for:

* Bearing stress.
* Shear.
* Tension.
* Bending.
* Pull-out.
* Fastener failure.

---

# 5.47 Bolt Shear

For a simplified bolt in single shear:

$$
\tau=
\frac{F}{A}
$$

For a circular bolt:

$$
A=
\frac{\pi d^2}{4}
$$

Therefore:

$$
\tau=
\frac{4F}{\pi d^2}
$$

Actual joint design should also consider:

* Double shear.
* Bearing.
* Edge distance.
* Bolt preload.
* Joint slip.
* Fatigue.

---

# 5.48 Bearing Stress

The material around a fastener hole can experience bearing stress.

A simplified relationship is:

$$
\sigma_b=
\frac{F}{td}
$$

where:

* \(F\) = load.
* \(t\) = material thickness.
* \(d\) = fastener diameter.

This is important for thin plates and composite joints.

---

# 5.49 Finite Element Analysis

Finite Element Analysis (FEA) divides a structure into many smaller elements.

Conceptually:

```text
Real Structure
      ↓
Simplified Geometry
      ↓
Mesh
      ↓
Elements + Nodes
      ↓
Material Properties
      ↓
Boundary Conditions
      ↓
Loads
      ↓
Solver
      ↓
Stress / Deformation
```

FEA allows complex structures to be analyzed numerically.

However:

$$
\boxed{\text{FEA results are only as meaningful as the model assumptions}}
$$

---

# 5.50 FEA Model Preparation

Before running an FEA simulation:

1. Simplify unnecessary geometry.
2. Define material properties.
3. Define contacts.
4. Define fasteners or equivalent connections.
5. Apply realistic boundary conditions.
6. Define loads.
7. Generate the mesh.
8. Run the analysis.
9. Check convergence.
10. Interpret the results.

---

# 5.51 Geometry Simplification

A detailed CAD model may contain:

* Fillets.
* Small holes.
* Screws.
* Threads.
* Cosmetic details.

Not all of these are required for structural FEA.

Small irrelevant features can make the mesh unnecessarily large.

However, features that influence stress concentration should not be removed blindly.

The simplification should preserve the important structural behavior.

---

# 5.52 Boundary Conditions

Boundary conditions define how the structure is constrained.

For example, a wing-root structural analysis may constrain the root region:

```text
Wing
────────────────────────────
████ Fixed
↑ ↑ ↑ ↑
Root Constraint
```

The actual constraint should represent the physical attachment as closely as practical.

An unrealistically fixed boundary can produce misleading results.

---

# 5.53 Applied Loads

Loads may include:

* Aerodynamic pressure.
* Distributed lift.
* Motor thrust.
* Motor torque.
* Tail forces.
* Landing forces.
* Payload loads.
* Battery inertial loads.

Where possible, distributed loads should be used rather than unrealistic concentrated point loads.

---

# 5.54 Mesh

The mesh divides the geometry into finite elements.

A simplified representation is:

```text
┌─┬─┬─┬─┬─┬─┐
├─┼─┼─┼─┼─┼─┤
├─┼─┼─┼─┼─┼─┤
├─┼─┼─┼─┼─┼─┤
└─┴─┴─┴─┴─┴─┘
```

Smaller elements generally allow more detailed representation but increase computational cost.

Mesh quality is important.

---

# 5.55 Mesh Convergence

A result should not be trusted simply because the software produces a number.

A mesh-convergence study can be performed by gradually refining the mesh.

For example:

| Mesh      | Elements | Maximum Stress |
| --------- | -------: | -------------: |
| Coarse    |      TBD |            TBD |
| Medium    |      TBD |            TBD |
| Fine      |      TBD |            TBD |
| Very Fine |      TBD |            TBD |

If the result approaches a stable value as the mesh is refined, confidence in the numerical result increases.

---

# 5.56 Stress Concentrations

High local stresses may occur around:

* Holes.
* Sharp corners.
* Fasteners.
* Motor mounts.
* Cutouts.
* Abrupt geometry changes.

These are called stress concentrations.

The CAD model should use appropriate fillets and geometry transitions where practical.

However, an extremely high stress at a mathematically sharp corner can sometimes be a numerical singularity rather than a realistic physical failure prediction.

Therefore, FEA results must be interpreted carefully.

---

# 5.57 Von Mises Stress

For many ductile isotropic materials, FEA software commonly reports Von Mises stress.

A simplified interpretation is:

$$
\sigma_{VM}
$$

is compared with an appropriate material yield or allowable stress.

The factor of safety can then be estimated as:

$$
FOS=
\frac{\sigma_{yield}}
{\sigma_{VM,max}}
$$

provided that the assumptions of the method are appropriate.

For composites, different failure criteria may be required.

---

# 5.58 Composite Failure

Composite structures cannot always be evaluated using only Von Mises stress.

Composite analysis may require criteria such as:

* Maximum stress.
* Maximum strain.
* Tsai-Hill.
* Tsai-Wu.
* Other laminate failure criteria.

The appropriate criterion depends on:

* Composite material.
* Laminate structure.
* Software.
* Loading.
* Project requirements.

The selected criterion should be documented.

---

# 5.59 Static Structural Analysis

The first FEA should generally investigate static structural loading.

Potential cases include:

### Case 1 — Normal flight

$$
n=1
$$

### Case 2 — Maneuver

Selected higher load factor.

### Case 3 — VTOL thrust

Motor thrust loads applied to the motor mounts.

### Case 4 — Pusher thrust

Rear pusher thrust applied to the rear motor mount.

### Case 5 — Landing

Selected landing load case.

These cases should be analyzed separately before combining more complex loads.

---

# 5.60 Load Case Matrix

A useful structural analysis matrix is:

| Load Case | Main Loads             | Purpose             |
| --------- | ---------------------- | ------------------- |
| LC-01     | 1g flight              | Normal operation    |
| LC-02     | Positive maneuver load | Wing strength       |
| LC-03     | VTOL thrust            | Motor/boom strength |
| LC-04     | Asymmetric VTOL thrust | Motor/structure     |
| LC-05     | Pusher thrust          | Rear mount          |
| LC-06     | Tail load              | Tail structure      |
| LC-07     | Landing                | Landing structure   |
| LC-08     | Battery inertia        | Battery restraint   |
| LC-09     | Payload inertia        | Payload mount       |

The exact values should be added once the project defines the operating envelope.

---

# 5.61 Normal Flight Load Case

For steady level flight:

$$
L=W
$$

Under the preliminary mass:

$$
L\approx49.05N
$$

This represents a baseline structural condition.

The aerodynamic lift distribution should then be transferred into the structural model.

---

# 5.62 Maneuver Load Case

For a selected maneuver load factor:

$$
L=nW
$$

For example, with:

$$
n=3
$$

the total lift requirement becomes:

$$
L=3(49.05)
$$

$$
L=147.15N
$$

The actual selected maneuver load factor should be documented and justified.

---

# 5.63 VTOL Structural Load Case

The VTOL structural model should account for motor thrust.

From Chapter 3:

$$
T_{total}\approx88.3N
$$

for the preliminary thrust target.

For equal thrust:

$$
T_{motor}\approx22.1N
$$

These loads can be applied to the four motor mounting locations.

A more advanced analysis can include:

* Unequal motor thrust.
* Maximum thrust.
* Control moments.
* Motor failure scenarios.

---

# 5.64 Asymmetric Motor Load Case

An asymmetric case can be useful for understanding structural behavior.

For example:

```text
Motor 1 = High
Motor 2 = High
Motor 3 = Low
Motor 4 = High
```

This creates an uneven load distribution.

The structural response may include:

* Roll moment.
* Local wing bending.
* Local mount loading.

This case also connects structural design to flight-control analysis.

---

# 5.65 Pusher Load Case

The rear pusher motor produces forward thrust.

A structural model can apply:

$$
F=T_{pusher}
$$

at the motor mounting interface.

The mount should be checked for:

* Translation.
* Bending.
* Local stress.
* Fastener loads.

The pusher thrust value should eventually come from the propulsion analysis and experimental measurements.

---

# 5.66 Landing Load Case

A simplified landing analysis may apply a selected vertical load factor:

$$
F=nmg
$$

The actual load should eventually be based on:

* Estimated or measured landing speed.
* Landing gear stroke.
* Impact time.
* Aircraft mass.
* Ground condition.

Landing testing can later provide experimental evidence.

---

# 5.67 Vibration

Rotating propulsion systems introduce vibration.

Potential sources include:

* Motor imbalance.
* Propeller imbalance.
* Shaft misalignment.
* Structural resonance.
* Motor electromagnetic forces.

Vibration can cause:

* Fastener loosening.
* Fatigue.
* Sensor noise.
* Electronics failure.
* Structural damage.

Therefore, vibration should eventually be investigated experimentally.

---

# 5.68 Fatigue

A structure may survive a single static load but fail after repeated loading.

Fatigue can occur due to:

* Repeated wing loading.
* Motor vibration.
* Landing cycles.
* Propeller loads.
* Control-surface movement.

For repeated operation, fatigue should be considered where appropriate.

A simplified fatigue workflow is:

```text
Repeated Load
      ↓
Stress Range
      ↓
Material S-N Data
      ↓
Cycles to Failure
      ↓
Fatigue Life
```

---

# 5.69 Structural Resonance

If an excitation frequency approaches a natural structural frequency, vibration can increase significantly.

Sources of excitation include:

* Motor RPM.
* Propeller blade-pass frequency.
* Harmonics.
* Control inputs.

Therefore, modal analysis may eventually be required.

A basic workflow is:

```text
CAD
 ↓
Mass Properties
 ↓
Material
 ↓
Constraints
 ↓
Modal Analysis
 ↓
Natural Frequencies
 ↓
Compare With Excitation Frequencies
```

---

# 5.70 Natural Frequency

A simplified single-degree-of-freedom approximation is:

$$
f_n=
\frac{1}{2\pi}
\sqrt{\frac{k}{m}}
$$

where:

* \(f_n\) = natural frequency.
* \(k\) = stiffness.
* \(m\) = effective mass.

The actual aircraft is a multi-degree-of-freedom system, so detailed modal analysis is more complex.

---

# 5.71 Structural Optimization

Once the initial FEA is complete, the design can be improved.

A typical cycle is:

```text
Initial CAD
   ↓
FEA
   ↓
High Stress Region
   ↓
Reinforce
   ↓
Low Stress Region
   ↓
Remove Unnecessary Material
   ↓
Updated CAD
   ↓
FEA Again
```

The objective is not simply to maximize strength.

The objective is to achieve sufficient strength and stiffness with reasonable mass.

---

# 5.72 Mass Versus Strength

Adding material usually increases strength and stiffness but also increases aircraft mass.

Increasing mass affects:

$$
W=mg
$$

which then affects:

$$
V_{stall}
$$

and:

$$
T_{VTOL}
$$

and:

$$
P_{propulsion}
$$

Therefore, structural over-design can create a system-level penalty.

This is why structural design must be integrated with the rest of the aircraft design.

---

# 5.73 Structural Design Loop

The complete design loop is:

```text
Aerodynamics
     ↓
Aerodynamic Loads
     ↓
Structural Analysis
     ↓
Structural Mass
     ↓
Aircraft Weight
     ↓
Updated Aerodynamics
     ↓
Updated Propulsion
     ↓
Updated Structure
```

This is an iterative engineering process.

---

# 5.74 CAD-to-FEA Workflow

A practical workflow can be:

### Step 1

Create CAD geometry.

### Step 2

Simplify the geometry for FEA.

### Step 3

Assign materials.

### Step 4

Define joints and contacts.

### Step 5

Define load cases.

### Step 6

Define boundary conditions.

### Step 7

Generate mesh.

### Step 8

Run simulation.

### Step 9

Check stress.

### Step 10

Check deformation.

### Step 11

Check factor of safety.

### Step 12

Perform mesh refinement.

### Step 13

Modify CAD if necessary.

### Step 14

Repeat analysis.

---

# 5.75 FEA Verification

FEA results should be checked against simplified calculations wherever possible.

For example, if a wing spar is approximated as a beam:

$$
\sigma=
\frac{Mc}{I}
$$

The analytical result can be compared with the FEA result.

This is called verification.

A useful comparison table is:

| Quantity       | Analytical | FEA | Difference |
| -------------- | ---------: | --: | ---------: |
| Maximum stress |        TBD | TBD |        TBD |
| Tip deflection |        TBD | TBD |        TBD |
| Root moment    |        TBD | TBD |        TBD |

Agreement does not prove that the aircraft is safe, but it increases confidence that the model behaves as expected.

---

# 5.76 Validation Versus Verification

These terms should be distinguished.

### Verification

Asks:

> "Did I solve the mathematical model correctly?"

Examples:

* Mesh convergence.
* Hand calculations.
* Comparison with beam theory.

### Validation

Asks:

> "Does the model represent the real aircraft?"

Examples:

* Strain-gauge measurements.
* Deflection measurements.
* Load testing.
* Flight-test data.

Therefore:

```text
Theory
  ↓
FEA
  ↓
Verification
  ↓
Physical Test
  ↓
Validation
```

---

# 5.77 Physical Structural Testing

After manufacturing, structural testing can provide experimental evidence.

Possible tests include:

* Static wing loading.
* Motor mount loading.
* Landing gear loading.
* Tail loading.
* Deflection measurement.

A basic static-load test can be represented as:

```text
Applied Load
     ↓
Aircraft Structure
     ↓
Measured Deflection
     ↓
Compare With FEA
```

The test load should be applied safely and with an appropriate test procedure.

---

# 5.78 Wing Deflection Test

A simple wing test can measure:

* Applied load.
* Wing-root condition.
* Tip displacement.

For example:

| Load | Predicted Deflection | Measured Deflection |
| ---: | -------------------: | ------------------: |
|  TBD |                  TBD |                 TBD |
|  TBD |                  TBD |                 TBD |
|  TBD |                  TBD |                 TBD |

The comparison helps evaluate the accuracy of the structural model.

---

# 5.79 Motor Mount Test

A motor mount can be tested using an equivalent load.

For example:

```text
Motor Mount
     ↓
Apply Known Force
     ↓
Measure Deflection
     ↓
Inspect Damage
```

The test should be conducted using appropriate safety precautions because propulsion components can store significant mechanical energy.

---

# 5.80 Structural Results

The structural results should eventually include:

* Maximum stress.
* Maximum deformation.
* Factor of safety.
* Critical locations.
* Mesh information.
* Load cases.
* Material properties.
* Boundary conditions.
* Analytical verification.
* Experimental validation.

The results should not consist only of a screenshot from an FEA software package.

The conditions behind the result are equally important.

---

# 5.81 Results File

The separate file should be:

```text id="j4v6f9"
05_Structural_Analysis/
├── 5. Structural Analysis.md
└── Results.md
```

The `Results.md` file should document the actual structural work.

A useful structure is:

```markdown id="gjd2lr"
# Structural Analysis — Results

## 1. Objective

Evaluate the structural performance of the UAV under selected load cases.

## 2. Aircraft Configuration

Describe the geometry and structural configuration analyzed.

## 3. Materials

| Component | Material | Density | Young's Modulus | Strength |
|---|---|---:|---:|---:|
| Wing spar | TBD | TBD | TBD | TBD |
| Fuselage | TBD | TBD | TBD | TBD |
| Motor mount | TBD | TBD | TBD | TBD |

## 4. Load Cases

| Case | Description | Load |
|---|---|---:|
| LC-01 | 1g flight | TBD |
| LC-02 | Maneuver | TBD |
| LC-03 | VTOL thrust | TBD |
| LC-04 | Pusher thrust | TBD |
| LC-05 | Landing | TBD |

## 5. FEA Setup

- Software:
- Mesh:
- Element type:
- Boundary conditions:
- Contacts:
- Material model:

## 6. Mesh Convergence

| Mesh | Elements | Stress | Deflection |
|---|---:|---:|---:|
| Coarse | TBD | TBD | TBD |
| Medium | TBD | TBD | TBD |
| Fine | TBD | TBD | TBD |

## 7. Results

| Load Case | Max Stress | Max Deflection | Factor of Safety |
|---|---:|---:|---:|
| LC-01 | TBD | TBD | TBD |
| LC-02 | TBD | TBD | TBD |
| LC-03 | TBD | TBD | TBD |

## 8. Critical Locations

Document where the highest stresses or deformations occurred.

## 9. Analytical Verification

Compare simplified calculations with FEA.

## 10. Physical Testing

Document experimental structural tests.

## 11. FEA vs Experimental Results

| Parameter | FEA | Experimental | Difference |
|---|---:|---:|---:|
| Deflection | TBD | TBD | TBD |
| Stress | TBD | TBD | TBD |

## 12. Design Changes

Document structural modifications resulting from the analysis.

## 13. Final Structural Configuration

Describe the final selected structure.

## 14. Limitations

Document assumptions and limitations.

## 15. Validation Status

- [ ] Material properties verified
- [ ] Mesh convergence completed
- [ ] Static analysis completed
- [ ] VTOL motor loads analyzed
- [ ] Pusher motor mount analyzed
- [ ] Landing loads analyzed
- [ ] Physical load test completed
- [ ] FEA compared with experiment
```

---

# 5.82 Structural Evidence to Store

The structural-analysis folder can eventually contain:

```text
05_Structural_Analysis/
│
├── 5. Structural Analysis.md
│
├── Results.md
│
├── FEA/
│   ├── Wing/
│   ├── Fuselage/
│   ├── Motor_Mounts/
│   └── Landing_Gear/
│
├── Analytical_Calculations/
│   ├── Wing_Bending.md
│   ├── Spar_Calculation.md
│   └── Motor_Mount_Load.md
│
├── Plots/
│
└── Test_Data/
```

This can be expanded later when actual files become available.

---

# 5.83 Structural Decision Log

Major structural decisions should be recorded.

Example:

| ID      | Decision                      | Reason            | Evidence               | Status      |
| ------- | ----------------------------- | ----------------- | ---------------------- | ----------- |
| STR-001 | Main spar selected            | Wing bending      | Analytical calculation | Preliminary |
| STR-002 | Motor mount reinforced        | VTOL thrust load  | FEA                    | TBD         |
| STR-003 | Battery tray reinforced       | Inertial load     | FEA                    | TBD         |
| STR-004 | Tail mount modified           | High local stress | FEA                    | TBD         |
| STR-005 | Landing gear geometry changed | Landing load      | Test                   | TBD         |

This provides traceability from analysis to physical design.

---

# 5.84 Structural Analysis Checklist

## Loads

* [ ] Aircraft weight calculated.
* [ ] Load factors defined.
* [ ] Aerodynamic loads defined.
* [ ] VTOL thrust loads defined.
* [ ] Pusher thrust defined.
* [ ] Landing loads defined.
* [ ] Payload loads defined.

## CAD

* [ ] Structural geometry imported.
* [ ] Correct material assigned.
* [ ] Critical joints represented.
* [ ] Motor mounts represented.
* [ ] Wing spar represented.

## FEA

* [ ] Boundary conditions defined.
* [ ] Contacts defined.
* [ ] Mesh created.
* [ ] Mesh convergence checked.
* [ ] Load cases analyzed.
* [ ] Stress evaluated.
* [ ] Deformation evaluated.
* [ ] Factor of safety evaluated.

## Verification

* [ ] Hand calculations performed.
* [ ] FEA compared with analytical model.
* [ ] Critical results investigated.

## Validation

* [ ] Physical structural test planned.
* [ ] Deflection measured.
* [ ] Results compared with FEA.
* [ ] Design updated based on evidence.

---

# 5.85 Important Structural Engineering Principles

The following principles should guide the structural design.

### Principle 1 — Follow the load path

Every important load should have a clear path into the primary structure.

### Principle 2 — Avoid unnecessary mass

Additional structure affects aircraft performance.

### Principle 3 — Strength is not enough

Stiffness and deformation also matter.

### Principle 4 — Check connections

A strong beam connected through a weak joint can still fail.

### Principle 5 — Do not trust FEA blindly

FEA requires appropriate assumptions, loads, constraints, and mesh quality.

### Principle 6 — Verify numerical models

Use analytical calculations where possible.

### Principle 7 — Validate with physical testing

A physical aircraft behaves differently from an idealized simulation.

---

# 5.86 Connection With Previous Chapters

The structural analysis depends directly on the previous chapters.

```text
Chapter 1
Preliminary Sizing
      ↓
Aircraft Mass
      ↓
Chapter 2
Aerodynamics
      ↓
Aerodynamic Loads
      ↓
Chapter 3
Propulsion
      ↓
Motor Loads
      ↓
Chapter 4
CAD
      ↓
Structural Geometry
      ↓
Chapter 5
Structural Analysis
      ↓
Stress / Deflection / FOS
```

The results then feed forward into:

```text
Structural Analysis
       ↓
Flight Dynamics
       ↓
Control
       ↓
Electronics
       ↓
Simulation
       ↓
Validation
```

---

# 5.87 What Is Still TBD?

The following values should remain open until they are properly established:

* Final aircraft mass.
* Final load factors.
* Final structural materials.
* Final wing spar geometry.
* Final motor mount geometry.
* Final fuselage structure.
* Landing load case.
* Material allowable stresses.
* FEA mesh.
* FEA boundary conditions.
* Structural factor of safety requirement.
* Fatigue requirements.
* Modal-analysis requirements.
* Physical test loads.
* Experimental structural results.

These values should be updated as the project develops.

---

# 5.88 Limitations of Preliminary Structural Analysis

The preliminary calculations in this chapter are simplified.

Actual structural behavior can differ because of:

* Material variability.
* Manufacturing defects.
* Adhesive properties.
* Composite anisotropy.
* Fastener flexibility.
* Joint deformation.
* Local buckling.
* Dynamic loads.
* Vibration.
* Fatigue.
* Temperature.
* Aerodynamic-structural interaction.

Therefore:

$$
\boxed{
\text{Preliminary structural calculations}
\neq
\text{validated structural performance}
}
$$

The purpose of the preliminary analysis is to identify the important structural requirements and establish a path toward detailed analysis and testing.

---

# 5.89 Summary

Structural analysis determines whether the aircraft structure can withstand its expected operating loads.

The major structural load sources for this UAV are:

* Aerodynamic lift.
* Aerodynamic drag.
* Maneuver loads.
* Four VTOL motor thrust forces.
* Rear pusher motor thrust.
* Motor torque.
* Tail aerodynamic forces.
* Payload inertia.
* Battery inertia.
* Landing loads.
* Vibration.

The primary structural components are:

* Main wing.
* Wing spar.
* Fuselage.
* VTOL motor mounts.
* Rear pusher motor mount.
* Horizontal tail.
* Vertical tail.
* Landing gear.
* Structural joints.

The basic structural design process is:

$$
\boxed{
Loads
\rightarrow
Structural\ Model
\rightarrow
FEA
\rightarrow
Stress
\rightarrow
Deflection
\rightarrow
Factor\ of\ Safety
\rightarrow
Design\ Revision
\rightarrow
Testing
}
$$

The final goal is not simply to obtain a high factor of safety.

The goal is to develop a structure that is:

* Strong enough.
* Stiff enough.
* Lightweight.
* Manufacturable.
* Reliable.
* Testable.

---

# 5.90 Key Engineering Lessons

1. **Every major aircraft load should have a clearly understood load path.**
2. **Wing bending is a major structural consideration for a fixed-wing UAV.**
3. **VTOL motor thrust creates significant local loads at the motor mounts.**
4. **The rear pusher motor also requires a properly designed structural load path.**
5. **Landing loads can be significantly different from normal flight loads.**
6. **Strength and stiffness are both important.**
7. **Aircraft mass and structural mass are strongly coupled.**
8. **FEA should be supported by analytical calculations wherever possible.**
9. **Mesh convergence improves confidence in numerical results.**
10. **Material assumptions must be documented.**
11. **Composite structures require appropriate anisotropic analysis.**
12. **Physical testing is necessary to validate structural predictions.**
13. **Structural design should be iterative rather than treated as a one-time calculation.**
14. **The final structural model should represent the aircraft that is actually manufactured and tested.**

The next chapter will use the aircraft's geometry, mass distribution, aerodynamic characteristics, and propulsion arrangement to develop the **flight-dynamics model** of the UAV.
