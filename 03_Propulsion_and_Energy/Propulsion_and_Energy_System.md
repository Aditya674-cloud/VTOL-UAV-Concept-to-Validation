# Chapter 3 — Propulsion and Energy System Design

## 3.1 Purpose of This Chapter

The propulsion system is one of the most important parts of a hybrid VTOL UAV because the aircraft operates in two fundamentally different flight regimes:

1. **Vertical flight**, where the aircraft must generate enough thrust to support its weight and control the aircraft in hover.
2. **Forward flight**, where the fixed wing generates most of the aerodynamic lift and the propulsion system primarily needs to overcome aerodynamic drag and provide additional thrust for acceleration, climb, and maneuvering.

The propulsion architecture selected for this project consists of:

* Four dedicated VTOL lift motors.
* Four VTOL propellers.
* One independent rear-mounted pusher motor.
* One forward-flight propeller.
* Electronic speed controllers (ESCs).
* A rechargeable battery system.
* Power distribution and wiring.
* Flight-control commands to the motor controllers.

The propulsion system therefore cannot be treated as one single motor-sizing problem.

The VTOL propulsion system and forward-flight propulsion system should be analyzed separately and then integrated into the complete aircraft.

---

# 3.2 Propulsion Architecture

The aircraft uses a fixed-wing hybrid VTOL configuration.

The basic arrangement is:

```text
                    MAIN WING
          ─────────────────────────────
             ↑                    ↑
          VTOL MOTOR           VTOL MOTOR
             ↑                    ↑
          VTOL PROP             VTOL PROP


                 FUSELAGE
        ─────────────────────────

                    ───────►
                  REAR PUSHER
                    MOTOR
                    PROP
```

The four VTOL motors are responsible for:

* Take-off.
* Hover.
* Vertical climbing.
* Vertical descent.
* Landing.
* Attitude control during VTOL operation.

The rear-mounted pusher motor is responsible primarily for:

* Forward acceleration.
* Cruise propulsion.
* Forward-flight climb.
* Overcoming aerodynamic drag.
* Maintaining forward-flight speed.

The main wing provides the majority of aerodynamic lift during forward flight.

Therefore:

$$
L \approx W
$$

during steady level forward flight, while:

$$
T_{pusher} \approx D
$$

during steady cruise.

These relationships are simplified preliminary design relationships. Actual flight conditions include climb angle, acceleration, drag changes, propeller efficiency, and control margins.

---

# 3.3 Propulsion Design Requirements

Before selecting motors or propellers, propulsion requirements should be established.

The major requirements are:

| Parameter                    |          Preliminary Value | Status         |
| ---------------------------- | -------------------------: | -------------- |
| MTOW                         |                       5 kg | Preliminary    |
| Weight                       |                    49.05 N | Calculated     |
| VTOL motors                  |                          4 | Selected       |
| Forward-flight motors        |                          1 | Selected       |
| VTOL thrust-to-weight target |                        1.8 | Preliminary    |
| Total VTOL thrust target     |                     88.3 N | Calculated     |
| Thrust per VTOL motor        |                     22.1 N | Calculated     |
| Cruise speed                 |                     15 m/s | Preliminary    |
| Estimated cruise drag        |                     4.15 N | Preliminary    |
| Cruise propulsion power      | ~89 W aerodynamic estimate | Preliminary    |
| Battery                      |                        TBD | To be selected |
| VTOL propeller               |                        TBD | To be selected |
| Pusher propeller             |                        TBD | To be selected |
| ESC rating                   |                        TBD | To be selected |

These values should not automatically be treated as final component specifications.

They represent the initial engineering requirements from the preliminary aircraft sizing.

---

# 3.4 Mass and Weight

The first propulsion calculation is based on aircraft weight.

From Chapter 1:

$$
m = 5\ kg
$$

Using:

$$
W=mg
$$

where:

* \(W\) = aircraft weight in N
* \(m\) = aircraft mass in kg
* \(g\) = gravitational acceleration

Using:

$$
g=9.81\ m/s^2
$$

gives:

$$
W=5(9.81)
$$

$$
\boxed{W=49.05\ N}
$$

This value is the minimum total thrust required to theoretically hover under ideal conditions.

However, designing the VTOL system for exactly \(T=W\) would provide no useful control or performance margin.

Therefore, a thrust-to-weight ratio greater than 1 is required.

---

# 3.5 VTOL Thrust Requirement

## 3.5.1 Thrust-to-Weight Ratio

The thrust-to-weight ratio is:

$$
\frac{T}{W}
$$

For this preliminary design, a target of:

$$
\frac{T}{W}=1.8
$$

is used.

Therefore:

$$
T_{total}=1.8W
$$

Substituting:

$$
T_{total}=1.8(49.05)
$$

$$
\boxed{T_{total}=88.29\ N}
$$

Therefore, the four VTOL motors together should be capable of producing approximately:

$$
\boxed{88.3\ N}
$$

of total thrust under the selected design condition.

---

# 3.6 Thrust Requirement Per VTOL Motor

The aircraft uses four VTOL lift motors.

Assuming equal thrust distribution:

$$
T_{motor}=\frac{T_{total}}{4}
$$

Therefore:

$$
T_{motor}=\frac{88.29}{4}
$$

$$
\boxed{T_{motor}\approx22.1\ N}
$$

Converting to kilogram-force:

$$
1\ kgf\approx9.81\ N
$$

Therefore:

$$
T_{motor}\approx\frac{22.1}{9.81}
$$

$$
\boxed{T_{motor}\approx2.25\ kgf}
$$

This means each VTOL propulsion unit should have a practical maximum thrust capability greater than approximately \(2.25\ kgf\) under the selected operating conditions.

The actual motor-propeller combination should normally provide additional margin above the minimum calculated requirement.

---

# 3.7 Why Motor Thrust Alone Is Not Enough

A motor should not be selected only by looking at its maximum thrust specification.

The motor, propeller, ESC, and battery form an interconnected system.

For example:

```text
Battery
   ↓
ESC
   ↓
Motor
   ↓
Propeller
   ↓
Thrust
```

Changing any component can affect the others.

A motor may produce high thrust with one propeller but operate inefficiently with another propeller.

Therefore, the correct engineering question is not:

> "Which motor has the highest thrust?"

Instead:

> "Which motor-propeller combination can produce the required thrust efficiently while remaining within the electrical and thermal limits of the system?"

---

# 3.8 Propeller Selection

A propeller converts motor shaft power into aerodynamic thrust.

Important propeller parameters include:

* Diameter.
* Pitch.
* Number of blades.
* Material.
* Rotational speed.
* Propeller efficiency.
* Static thrust.
* Current consumption.
* Power consumption.

For VTOL operation, propeller diameter is particularly important because it affects the effective rotor disk area.

For preliminary comparison:

$$
A=\frac{\pi D^2}{4}
$$

where:

* \(A\) = propeller disk area
* \(D\) = propeller diameter

A larger propeller can generally generate a given amount of thrust with lower disk loading, although the actual result depends on rotational speed, blade geometry, motor characteristics, installation effects, and available clearance.

---

# 3.9 Disk Loading

Disk loading is defined as:

$$
DL=\frac{T}{A}
$$

where:

* \(DL\) = disk loading
* \(T\) = thrust
* \(A\) = rotor disk area

For a propeller:

$$
A=\frac{\pi D^2}{4}
$$

Therefore:

$$
DL=
\frac{T}
{\pi D^2/4}
$$

Lower disk loading is generally desirable for efficient hovering.

However, the practical propeller diameter is constrained by:

* Wing geometry.
* Fuselage geometry.
* Ground clearance.
* Motor placement.
* Propeller interference.
* Structural design.
* Transport requirements.
* Propeller availability.

Therefore, propeller selection is a multi-variable design problem.

---

# 3.10 Ideal Hover Power

An idealized actuator-disk approximation can be used to estimate hover power.

The ideal induced power is approximately:

$$
P_{ideal}
=
\frac{T^{3/2}}
{\sqrt{2\rho A}}
$$

where:

* \(P_{ideal}\) = ideal induced power
* \(T\) = thrust
* \(\rho\) = air density
* \(A\) = rotor disk area

This equation represents an ideal aerodynamic model.

Real propellers do not operate at 100% efficiency.

Therefore, actual power is higher.

A simplified estimate can be written as:

$$
P_{actual}
=
\frac{P_{ideal}}{FM}
$$

where \(FM\) is an assumed figure of merit or equivalent efficiency factor.

The value of \(FM\) should be treated as an assumption unless supported by manufacturer data, propeller test data, or experimental measurements.

---

# 3.11 Why Hover Power Is Important

Hover power can become one of the largest energy demands of a hybrid VTOL aircraft.

During forward flight:

$$
L\approx W
$$

is primarily produced by the wing.

During hover:

$$
T\approx W
$$

must be generated by the VTOL propellers.

Therefore, the aircraft can have relatively low forward-flight power requirements while still requiring substantial instantaneous electrical power during VTOL operation.

This is one of the important differences between:

* Energy required for cruise.
* Power required during VTOL.

Energy and power should therefore not be confused.

---

# 3.12 Power and Energy

Power is the rate at which energy is used:

$$
P=\frac{E}{t}
$$

Therefore:

$$
E=Pt
$$

where:

* \(P\) = power
* \(E\) = energy
* \(t\) = time

For a flight mission consisting of several phases:

$$
E_{mission}
=
\sum_i P_i t_i
$$

For example:

```text
Vertical take-off
        ↓
Transition
        ↓
Forward cruise
        ↓
Maneuver / climb
        ↓
Transition
        ↓
Vertical landing
```

Each phase may require a different amount of power.

Therefore, battery sizing should be based on the complete mission rather than cruise power alone.

---

# 3.13 Forward-Flight Propulsion

The forward-flight propulsion system is independent of the four VTOL lift motors.

The aircraft uses a **rear-mounted pusher motor**.

The pusher motor provides thrust in the forward direction.

During steady level flight:

$$
L\approx W
$$

and:

$$
T_{pusher}\approx D
$$

where:

* \(L\) = aerodynamic lift
* \(W\) = aircraft weight
* \(T_{pusher}\) = forward propulsion thrust
* \(D\) = aerodynamic drag

The wing therefore carries most of the aircraft weight while the pusher propulsion system compensates for aerodynamic drag.

---

# 3.14 Cruise Drag From Chapter 1

The preliminary aerodynamic analysis estimated:

$$
C_D\approx0.070
$$

at the selected cruise condition.

The drag equation is:

$$
D=
\frac{1}{2}\rho V^2SC_D
$$

or:

$$
D=qSC_D
$$

where:

$$
q=\frac{1}{2}\rho V^2
$$

Using the preliminary design values:

$$
\rho=1.225\ kg/m^3
$$

$$
V=15\ m/s
$$

$$
S=0.428\ m^2
$$

$$
C_D\approx0.070
$$

gives an estimated cruise drag of approximately:

$$
\boxed{D\approx4.15\ N}
$$

This is a preliminary aerodynamic estimate and should not be treated as the final pusher motor requirement.

---

# 3.15 Cruise Propulsion Power

The aerodynamic power required to overcome drag is:

$$
P_{aero}=DV
$$

Using:

$$
D=4.15\ N
$$

and:

$$
V=15\ m/s
$$

gives:

$$
P_{aero}=4.15(15)
$$

$$
\boxed{P_{aero}\approx62.3\ W}
$$

This is the useful aerodynamic power delivered to overcome drag.

The motor must provide more electrical power because the propulsion system has losses.

If the assumed propulsive efficiency is:

$$
\eta_{prop}=0.70
$$

then:

$$
P_{motor}
=
\frac{P_{aero}}{\eta_{prop}}
$$

Therefore:

$$
P_{motor}
=
\frac{62.3}{0.70}
$$

$$
\boxed{P_{motor}\approx89\ W}
$$

This is a preliminary cruise estimate.

---

# 3.16 Why 89 W Is Not the Final Pusher Motor Specification

It would be incorrect to select a motor simply because it is rated at approximately 89 W.

The aircraft must also be capable of:

* Accelerating from low speed.
* Climbing.
* Overcoming additional drag.
* Operating during transition.
* Handling wind.
* Maintaining safe control margins.
* Operating efficiently rather than continuously at maximum output.

Therefore, final pusher motor sizing should consider:

$$
P_{required}
=
P_{cruise}
+
P_{climb}
+
P_{acceleration}
+
P_{margin}
$$

A detailed motor-propeller analysis should therefore use manufacturer test data or experimental thrust data.

---

# 3.17 Static Thrust Versus Forward Thrust

Static thrust and forward-flight thrust are not identical.

### Static condition

The aircraft is approximately stationary relative to the air:

$$
V\approx0
$$

This is relevant to:

* Take-off testing.
* Motor testing.
* Propeller test stands.
* Static thrust measurements.

### Forward-flight condition

The propeller experiences significant inflow velocity.

The thrust generated by the propeller changes with:

* Airspeed.
* RPM.
* Propeller pitch.
* Diameter.
* Air density.
* Motor torque.

Therefore, a propeller that produces high static thrust does not automatically provide the best cruise performance.

This distinction is particularly important when selecting the rear pusher system.

---

# 3.18 Motor Kv

Brushless motor specifications often include a parameter called \(K_V\).

\(K_V\) represents the approximate no-load rotational speed per volt:

$$
RPM\approx K_VV
$$

under idealized no-load conditions.

For example, a motor with:

$$
K_V=500\ RPM/V
$$

at:

$$
V=20\ V
$$

would have an approximate no-load speed of:

$$
RPM\approx500(20)
$$

$$
RPM\approx10,000
$$

Actual loaded RPM will be lower because of:

* Motor torque.
* Propeller load.
* Electrical losses.
* Battery voltage drop.
* Motor resistance.
* ESC operation.

Therefore, \(K_V\) alone is not enough to select a motor.

---

# 3.19 Motor Torque

Motor power is related to torque and angular velocity:

$$
P=\tau\omega
$$

where:

* \(P\) = mechanical power
* \(\tau\) = torque
* \(\omega\) = angular velocity

Angular velocity is:

$$
\omega=\frac{2\pi RPM}{60}
$$

Therefore:

$$
P=
\tau
\frac{2\pi RPM}{60}
$$

This relationship explains why a motor-propeller combination must be considered as a complete system.

A larger propeller generally requires greater torque for a given rotational speed.

---

# 3.20 ESC Selection

An Electronic Speed Controller (ESC) regulates electrical power delivered to the brushless motor.

The ESC must be compatible with:

* Battery voltage.
* Motor current.
* Motor type.
* Required switching frequency.
* Control protocol.
* Thermal environment.

A simplified selection rule is:

$$
I_{ESC,rated}>I_{motor,max}
$$

with an appropriate engineering margin.

For example, if a motor-propeller test indicates:

$$
I_{max}=30A
$$

an ESC should not be selected with a nominal continuous rating of exactly \(30A\) without considering operating conditions and manufacturer specifications.

Thermal performance and continuous current capability are important.

---

# 3.21 Battery Voltage

Battery voltage strongly affects the electrical system.

Electrical power is:

$$
P=VI
$$

Therefore:

$$
I=\frac{P}{V}
$$

For a fixed power requirement, increasing voltage reduces the required current.

For example, if:

$$
P=1000W
$$

at:

$$
V=20V
$$

then:

$$
I=\frac{1000}{20}
$$

$$
I=50A
$$

At:

$$
V=40V
$$

the same power would require:

$$
I=\frac{1000}{40}
$$

$$
I=25A
$$

This demonstrates the relationship between system voltage and current.

However, battery voltage must be selected based on the motor, ESC, propeller, avionics, and battery architecture rather than this relationship alone.

---

# 3.22 Battery Capacity

Battery capacity is commonly expressed in:

$$
mAh
$$

or:

$$
Ah
$$

The approximate stored energy is:

$$
E(Wh)
=
V_{nominal}
\times
Capacity(Ah)
$$

Therefore:

$$
Capacity(Ah)
=
\frac{E(Wh)}
{V_{nominal}}
$$

For mAh:

$$
Capacity(mAh)
=
\frac{E(Wh)\times1000}
{V_{nominal}}
$$

This provides a first-order battery capacity estimate.

---

# 3.23 Usable Battery Energy

The full nominal battery capacity should not automatically be considered usable mission energy.

Factors include:

* Maximum recommended discharge.
* Voltage sag.
* Battery temperature.
* Current demand.
* Battery aging.
* Safety reserve.
* ESC cutoff voltage.
* Required landing reserve.

Therefore:

$$
E_{usable}<E_{nominal}
$$

A practical battery-sizing calculation should include an appropriate reserve.

---

# 3.24 C-Rating

A battery may have a rated discharge capability expressed using a C-rating.

The approximate maximum current is:

$$
I_{max}=C_{rating}\times Capacity(Ah)
$$

For example, a:

$$
5Ah
$$

battery with:

$$
20C
$$

rating theoretically corresponds to:

$$
I_{max}=20(5)
$$

$$
I_{max}=100A
$$

However, manufacturer ratings should be treated carefully because actual continuous performance depends on:

* Battery temperature.
* Cell chemistry.
* Battery condition.
* Measurement method.
* Manufacturer rating conventions.

---

# 3.25 Battery Sizing From Mission Energy

The aircraft mission should first be divided into phases.

A preliminary mission could be:

| Flight Phase       | Approximate Duration | Power Level | Status |
| ------------------ | -------------------: | ----------: | ------ |
| VTOL take-off      |                  TBD |        High | TBD    |
| Transition         |                  TBD | High/Medium | TBD    |
| Cruise             |                  TBD |      Medium | TBD    |
| Climb/maneuver     |                  TBD |        High | TBD    |
| Transition to VTOL |                  TBD | High/Medium | TBD    |
| Landing            |                  TBD |        High | TBD    |

Mission energy can then be estimated using:

$$
E_{mission}
=
\sum_i P_i t_i
$$

If power is in watts and time is in hours:

$$
E(Wh)=P(W)t(h)
$$

For multiple phases:

$$
E_{mission}
=
P_1t_1+
P_2t_2+
P_3t_3+\cdots
$$

Battery capacity can then be estimated from:

$$
E_{battery}
\geq
\frac{E_{mission}}{\eta_{system}}
$$

with additional reserve included.

---

# 3.26 Example of Mission Energy Calculation

Consider a simplified hypothetical mission:

| Phase        |  Power |   Time |
| ------------ | -----: | -----: |
| VTOL         | 1500 W |   30 s |
| Cruise       |  150 W | 10 min |
| Climb        |  500 W |   60 s |
| Landing VTOL | 1200 W |   30 s |

The energy for each phase can be calculated separately.

For VTOL:

$$
E_{VTOL}
=
1500
\left(\frac{30}{3600}\right)
$$

$$
E_{VTOL}=12.5Wh
$$

For cruise:

$$
E_{cruise}
=
150
\left(\frac{10}{60}\right)
$$

$$
E_{cruise}=25Wh
$$

For climb:

$$
E_{climb}
=
500
\left(\frac{60}{3600}\right)
$$

$$
E_{climb}\approx8.33Wh
$$

For landing:

$$
E_{landing}
=
1200
\left(\frac{30}{3600}\right)
$$

$$
E_{landing}=10Wh
$$

Total:

$$
E_{mission}
=
12.5+25+8.33+10
$$

$$
\boxed{E_{mission}\approx55.83Wh}
$$

This is only an example demonstrating the method.

The actual project should use measured or justified power values.

---

# 3.27 Propulsion Efficiency

The overall propulsion system has multiple losses.

A simplified efficiency chain is:

```text
Battery
   ↓
Electrical Power
   ↓
ESC
   ↓
Motor
   ↓
Mechanical Shaft Power
   ↓
Propeller
   ↓
Useful Thrust Power
```

A simplified overall efficiency can be represented as:

$$
\eta_{overall}
=
\eta_{ESC}
\eta_{motor}
\eta_{prop}
$$

The actual system may include additional losses.

Therefore:

$$
P_{electrical}
>
P_{useful}
$$

This difference becomes heat and other losses.

---

# 3.28 Motor and Propeller Matching

Motor-propeller matching should be based on actual operating data.

Important data points include:

* Voltage.
* Current.
* RPM.
* Static thrust.
* Power.
* Efficiency.
* Motor temperature.

A useful test table is:

| Voltage | Propeller | RPM | Current | Power | Thrust | Efficiency |
| ------: | --------- | --: | ------: | ----: | -----: | ---------: |
|     TBD | TBD       | TBD |     TBD |   TBD |    TBD |        TBD |
|     TBD | TBD       | TBD |     TBD |   TBD |    TBD |        TBD |
|     TBD | TBD       | TBD |     TBD |   TBD |    TBD |        TBD |

The objective is to identify a combination that satisfies the aircraft requirement without exceeding the motor or ESC limits.

---

# 3.29 Thrust-to-Power Ratio

One useful metric for propulsion comparison is:

$$
\frac{T}{P}
$$

where:

* \(T\) = thrust
* \(P\) = power

Higher thrust per unit power indicates better efficiency under that particular operating condition.

However, this metric should only be compared under equivalent conditions.

For example:

* Same voltage.
* Same air density.
* Same propeller condition.
* Same flight speed.
* Same measurement method.

---

# 3.30 VTOL and Forward Propulsion Should Be Analyzed Separately

The aircraft has two propulsion problems.

### VTOL system

Main requirements:

* High thrust.
* Good hover efficiency.
* Rapid response.
* Reliable control.
* Adequate redundancy/margin.
* Thermal capability.

### Pusher system

Main requirements:

* Efficient forward thrust.
* Cruise efficiency.
* Acceleration.
* Climb capability.
* Transition support.
* Suitable propeller-airframe integration.

Therefore, one motor type does not necessarily need to be used for all five motors.

The final configuration should be selected based on engineering analysis.

---

# 3.31 Electrical Power Distribution

The electrical architecture can be represented as:

```text
                    BATTERY
                       │
                       ▼
              POWER DISTRIBUTION
                ┌──────┼──────┐
                │      │      │
                ▼      ▼      ▼
             ESC 1   ESC 2   ESC 3 ...
                │      │      │
                ▼      ▼      ▼
             VTOL    VTOL    VTOL
             Motor   Motor   Motor

                       │
                       ▼
                 Pusher ESC
                       │
                       ▼
                 Pusher Motor
```

The actual system may also include:

* Power module.
* Voltage regulator.
* Flight controller.
* GPS.
* Telemetry.
* Sensors.
* Companion computer.
* Cameras.
* Other avionics.

High-current propulsion wiring should be separated appropriately from sensitive signal wiring.

---

# 3.32 Electrical Current Estimation

Electrical current can be estimated from:

$$
I=\frac{P}{V}
$$

For a multi-motor system:

$$
I_{total}
=
I_1+I_2+I_3+I_4+I_5
$$

during a condition where all five propulsion systems are operating.

However, hybrid VTOL aircraft may not operate all propulsion systems at maximum power simultaneously during normal steady flight.

Therefore, the electrical architecture should be evaluated for multiple operating modes.

---

# 3.33 Operating Modes

A useful way to analyze the propulsion system is by flight mode.

## Mode 1 — VTOL Take-Off

```text
VTOL Motors: HIGH
Pusher: OFF / TBD
Wing Lift: LOW
```

The VTOL system provides nearly all required vertical force.

---

## Mode 2 — Hover

```text
VTOL Motors: ACTIVE
Pusher: OFF / LOW
Wing Lift: LOW
```

The aircraft is primarily supported by rotor thrust.

---

## Mode 3 — Transition

```text
VTOL Motors: ACTIVE / REDUCING
Pusher: INCREASING
Wing Lift: INCREASING
```

This is one of the most important phases for later flight-dynamics and control analysis.

---

## Mode 4 — Forward Flight

```text
VTOL Motors: OFF / MINIMAL
Pusher: ACTIVE
Wing Lift: HIGH
```

The fixed wing generates most of the required lift.

---

## Mode 5 — Transition to VTOL

```text
Pusher: REDUCING
VTOL Motors: INCREASING
Wing Lift: DECREASING
```

---

## Mode 6 — Landing

```text
VTOL Motors: ACTIVE
Pusher: OFF / LOW
Wing Lift: LOW
```

These modes will later connect directly to:

* Flight dynamics.
* Control-system design.
* Flight-controller logic.
* Energy management.
* Transition analysis.

---

# 3.34 Propulsion Requirements Traceability

The propulsion design should maintain traceability back to the aircraft requirements.

For example:

```text
MTOW
  ↓
Weight
  ↓
Required VTOL thrust
  ↓
Required thrust per motor
  ↓
Motor selection
  ↓
Propeller selection
  ↓
ESC selection
  ↓
Battery current requirement
  ↓
Battery selection
  ↓
Electrical architecture
```

For forward flight:

```text
Aircraft geometry
  ↓
Aerodynamic analysis
  ↓
Cruise drag
  ↓
Required forward thrust
  ↓
Pusher motor
  ↓
Pusher propeller
  ↓
ESC
  ↓
Battery power requirement
```

This is an important engineering design chain.

---

# 3.35 Preliminary Motor Selection Procedure

The motor selection process should follow a defined procedure.

### Step 1 — Determine required thrust

For VTOL:

$$
T_{required,motor}
=
\frac{kW}{4}
$$

where \(k\) is the selected thrust-to-weight ratio.

### Step 2 — Define operating voltage

Select a preliminary battery voltage range.

### Step 3 — Select candidate motors

Candidate motors should be evaluated based on:

* \(K_V\).
* Maximum current.
* Maximum power.
* Recommended propellers.
* Weight.
* Efficiency.
* Manufacturer test data.

### Step 4 — Evaluate propellers

Test or compare several compatible propellers.

### Step 5 — Check thrust

Verify:

$$
T_{available}>T_{required}
$$

### Step 6 — Check power

Verify:

$$
P_{motor}
$$

is compatible with the electrical system.

### Step 7 — Check thermal limits

The motor and ESC should remain within their specified operating limits.

### Step 8 — Select the complete propulsion unit

The final decision should be based on the complete motor-propeller-ESC-battery system rather than motor specifications alone.

---

# 3.36 Propulsion Selection Criteria

A propulsion candidate can be compared using:

| Parameter                 | Importance |
| ------------------------- | ---------- |
| Maximum thrust            | High       |
| Thrust at operating point | Very High  |
| Power consumption         | Very High  |
| Current                   | High       |
| Motor mass                | High       |
| Propeller compatibility   | High       |
| Efficiency                | Very High  |
| Thermal performance       | High       |
| Cost                      | Medium     |
| Availability              | Medium     |
| Reliability               | High       |

The final selection should be documented in the Results section.

---

# 3.37 Experimental Propulsion Testing

Once components are selected, the propulsion system should ideally be tested before installation on the aircraft.

A basic test setup can be:

```text
Battery
   ↓
ESC
   ↓
Motor
   ↓
Propeller
   ↓
Thrust Stand
   ↓
Load Cell
```

Measurements can include:

* Thrust.
* Voltage.
* Current.
* RPM.
* Electrical power.
* Motor temperature.
* ESC temperature.

Electrical power:

$$
P=VI
$$

Propulsive efficiency can then be estimated depending on the test condition and available measurement data.

---

# 3.38 Example Experimental Data Table

The project should eventually maintain a table such as:

| Test | Motor | Propeller | Voltage | Current | RPM | Thrust | Power | Temperature |
| ---- | ----- | --------- | ------: | ------: | --: | -----: | ----: | ----------: |
| 001  | TBD   | TBD       |     TBD |     TBD | TBD |    TBD |   TBD |         TBD |
| 002  | TBD   | TBD       |     TBD |     TBD | TBD |    TBD |   TBD |         TBD |
| 003  | TBD   | TBD       |     TBD |     TBD | TBD |    TBD |   TBD |         TBD |

These measurements are more valuable than relying only on catalogue specifications.

---

# 3.39 Data Traceability

Every final propulsion decision should have a source.

For example:

| Parameter          |  Value | Source               | Status      |
| ------------------ | -----: | -------------------- | ----------- |
| Aircraft mass      |   5 kg | Chapter 1 assumption | Preliminary |
| VTOL thrust target | 88.3 N | Calculation          | Calculated  |
| Thrust per motor   | 22.1 N | Calculation          | Calculated  |
| Motor              |    TBD | Motor comparison     | TBD         |
| VTOL propeller     |    TBD | Propeller comparison | TBD         |
| Pusher motor       |    TBD | Propulsion analysis  | TBD         |
| Pusher propeller   |    TBD | Propeller analysis   | TBD         |
| Battery            |    TBD | Energy analysis      | TBD         |
| ESC                |    TBD | Electrical analysis  | TBD         |

This prevents the final design from appearing arbitrary.

---

# 3.40 Important Difference Between Assumption and Result

At this stage, several values are preliminary.

For example:

$$
T/W=1.8
$$

is a **design assumption/target**.

The calculated result:

$$
T_{total}=88.3N
$$

is a **calculated requirement**.

A selected motor producing, for example, a measured thrust value would become a **selected/validated result** only after appropriate evidence exists.

Therefore, the project documentation should distinguish between:

* Assumed.
* Calculated.
* Selected.
* Simulated.
* Measured.
* Validated.

---

# 3.41 Connection With Previous Chapters

Chapter 1 established the preliminary aircraft requirements.

Chapter 2 established the aerodynamic design process.

Chapter 3 converts these requirements into propulsion requirements.

The design chain is:

```text
Chapter 1
Concept and Preliminary Sizing
        ↓
Aircraft Weight
        ↓
Wing Geometry
        ↓
Cruise Condition
        ↓
Chapter 2
Aerodynamic Analysis
        ↓
Lift and Drag
        ↓
Chapter 3
Propulsion Requirements
        ↓
VTOL Thrust
        ↓
Pusher Thrust
        ↓
Motor / Propeller / ESC
        ↓
Battery
        ↓
Electrical Architecture
```

Later chapters will use this information for:

```text
Propulsion
    ↓
Mechanical Design
    ↓
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

# 3.42 What Should Be Recorded in the Results File?

The separate `Results.md` file inside the Chapter 3 folder should contain the **actual work performed on the project**.

For example:

```text
03_Propulsion_and_Energy/
├── 3. Propulsion and Energy.md
└── Results.md
```

The chapter explains:

> How propulsion systems are designed.

The Results file records:

> What propulsion system was actually analyzed and selected.

The Results file can eventually contain:

### VTOL propulsion

* Required thrust.
* Candidate motors.
* Candidate propellers.
* Manufacturer data.
* Thrust-test results.
* Current measurements.
* Power measurements.
* Motor temperature.
* ESC temperature.

### Pusher propulsion

* Required cruise thrust.
* Candidate motors.
* Candidate propellers.
* Static thrust.
* Forward-flight estimates.
* Power requirements.
* Motor selection.

### Battery

* Nominal voltage.
* Capacity.
* Maximum current.
* Estimated mission energy.
* Measured energy consumption.
* Flight-time estimate.

---

# 3.43 Example Results Structure

A future `Results.md` can be organized as:

```markdown
# Propulsion and Energy — Results

## 1. Objective

Evaluate the propulsion system for the hybrid VTOL UAV.

## 2. Aircraft Requirements

| Parameter | Value |
|---|---:|
| MTOW | 5 kg |
| VTOL motors | 4 |
| Pusher motors | 1 |
| VTOL thrust target | 88.3 N |
| Thrust per VTOL motor | 22.1 N |

## 3. VTOL Motor Candidates

| Motor | Propeller | Voltage | Current | Thrust | Power |
|---|---|---:|---:|---:|---:|
| Candidate A | TBD | TBD | TBD | TBD | TBD |
| Candidate B | TBD | TBD | TBD | TBD | TBD |

## 4. Pusher Candidates

| Motor | Propeller | Voltage | Current | Thrust | Power |
|---|---|---:|---:|---:|---:|
| Candidate A | TBD | TBD | TBD | TBD | TBD |
| Candidate B | TBD | TBD | TBD | TBD | TBD |

## 5. Battery Analysis

| Parameter | Value |
|---|---:|
| Nominal voltage | TBD |
| Capacity | TBD |
| Estimated energy | TBD |
| Maximum current | TBD |
| Estimated mission energy | TBD |

## 6. Observations

Record what was observed from calculations, simulations, manufacturer data, or experiments.

## 7. Design Decision

Document which propulsion configuration was selected and why.

## 8. Limitations

Document assumptions, uncertainties, manufacturer-data limitations, and unvalidated calculations.

## 9. Validation Status

- [ ] Motor selection validated
- [ ] Propeller selection validated
- [ ] Static thrust tested
- [ ] Current measured
- [ ] Power measured
- [ ] Battery performance tested
- [ ] Flight test completed
```

---

# 3.44 What Is Still TBD?

The following parameters should remain open until proper analysis or component testing is performed:

* VTOL motor model.
* VTOL propeller size.
* VTOL propeller pitch.
* Pusher motor model.
* Pusher propeller size.
* Pusher propeller pitch.
* ESC rating.
* Battery voltage.
* Battery capacity.
* Battery C-rating.
* Power distribution architecture.
* Motor mounting arrangement.
* Propeller clearance.
* Maximum electrical current.
* Thermal performance.
* Actual hover power.
* Actual cruise power.
* Actual flight endurance.

These should be filled using engineering evidence rather than guessed values.

---

# 3.45 Limitations of the Preliminary Propulsion Model

The calculations in this chapter are preliminary.

The actual propulsion system will differ because:

1. Propeller efficiency is not constant.
2. Motor efficiency changes with load.
3. Battery voltage changes during discharge.
4. Battery internal resistance causes voltage sag.
5. Propeller thrust changes with airspeed.
6. Air density changes with altitude and temperature.
7. Motor and ESC temperatures affect performance.
8. Propeller-airframe interference can change performance.
9. VTOL rotors may experience aerodynamic interference with the wing and fuselage.
10. Transition conditions are not represented by simple hover or cruise equations.

Therefore:

$$
\boxed{\text{Preliminary calculations} \neq \text{final validated propulsion performance}}
$$

The purpose of this stage is to narrow the design space and establish engineering requirements.

---

# 3.46 Engineering Decision Process

The final propulsion decision should follow:

```text
Aircraft Requirements
        ↓
Thrust Requirements
        ↓
Power Requirements
        ↓
Candidate Motors
        ↓
Candidate Propellers
        ↓
Motor-Propeller Matching
        ↓
Electrical Analysis
        ↓
Battery Analysis
        ↓
Thermal Analysis
        ↓
Bench Testing
        ↓
Flight Testing
        ↓
Validated Propulsion System
```

This creates a traceable engineering process.

---

# 3.47 Summary

The hybrid VTOL UAV requires two different propulsion systems:

* Four dedicated VTOL lift motors.
* One rear-mounted pusher motor for forward flight.

For the preliminary 5 kg aircraft:

$$
W=49.05N
$$

Using a preliminary VTOL thrust-to-weight target of:

$$
T/W=1.8
$$

the required total VTOL thrust is:

$$
\boxed{T_{total}\approx88.3N}
$$

For four VTOL motors:

$$
\boxed{T_{motor}\approx22.1N}
$$

or approximately:

$$
\boxed{2.25kgf}
$$

per motor.

The preliminary aerodynamic model estimates approximately:

$$
D\approx4.15N
$$

at the selected cruise condition.

The corresponding aerodynamic power is:

$$
P_{aero}\approx62.3W
$$

and using a preliminary propulsive efficiency of \(0.70\):

$$
P_{motor}\approx89W
$$

This cruise power estimate is not sufficient by itself to select the final pusher motor because acceleration, climb, transition, propeller efficiency, and operating margins must also be considered.

The next stage is therefore to move from theoretical requirements toward actual propulsion candidates, manufacturer data, motor-propeller matching, battery sizing, and eventually experimental validation.

---

# 3.48 Key Engineering Lessons

The major lessons from this chapter are:

1. **VTOL thrust and forward-flight thrust are different design problems.**
2. **Motor selection must include the propeller, ESC, and battery.**
3. **Maximum motor thrust is not the same as efficient operating thrust.**
4. **Static thrust does not completely describe forward-flight performance.**
5. **Power and energy are different quantities.**
6. **Battery sizing should consider the complete mission.**
7. **The electrical system must be sized for peak as well as continuous demand.**
8. **Manufacturer data should be distinguished from experimental measurements.**
9. **Preliminary calculations should not be presented as validated results.**
10. **Every major propulsion decision should be traceable to a requirement, calculation, simulation, or experiment.**

The propulsion design therefore becomes the bridge between the aerodynamic requirements established in Chapter 2 and the mechanical, structural, electrical, and control systems developed in later chapters.
