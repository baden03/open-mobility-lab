# Reference vehicle: Adaptive Expedition Trike

[Deutsch](reference-vehicle_DE.md) · [Concepts](README.md) · [Regulatory classification](../regulatory/classification.md)

**Status:** Consolidated concept from the initial design conversation; requirements and architecture are provisional  
**Legal target:** German bicycle / 250 W EPAC, subject to confirmation and validation  
**Primary journey:** 12 km each way on German country cycle routes  
**Reference persona:** Ol’ Captain Hinkebein, a tall and heavy rider with limited knee flexion and one replaced or otherwise troublesome knee

## 1. Design intent

The reference vehicle is a transforming, electrically assisted recumbent tadpole tricycle. It is intended to let a rider who cannot comfortably lower themself into a conventional recumbent trike approach a chair-height seat, sit with dignity, and have the machine transform around them into a stable, efficient riding posture.

It is not a mobility scooter with decorative pedals. The road concept uses genuine continuous human propulsion and a legally limited auxiliary motor. The rider should obtain useful leg exercise at a comfortable cadence and load. Optional hand propulsion can add upper-body power without forcing the arms and legs to share a cadence.

## 2. Consolidated requirement set

| Area | Provisional requirement | Origin / confidence |
| --- | --- | --- |
| Journey | Complete a 24 km round trip, plus a defined reserve | Explicit need; high confidence |
| Infrastructure | Fit and behave safely on country cycle paths and ordinary access routes | Explicit need; high confidence |
| Assisted speed | Assistance progressively ends before or at 25 km/h | Legal target; high confidence |
| Human input | Genuine adjustable foot pedalling remains available and useful | Explicit preference; high confidence |
| Access | Rider enters and exits at approximately chair height without lowering themself into a recumbent | Explicit need; high confidence |
| Ride posture | Low, supported, semi-recumbent or recumbent posture for stability and reduced drag | Explicit concept; high confidence |
| Geometry | Two front wheels and one rear wheel (tadpole) | Repeated concept; medium-high confidence |
| Transformation | Short/high/upright for access; long/low/reclined for cruise | Explicit concept; high confidence |
| Hand drive | Optional independent left/right rowing-like hand inputs add mechanical human power | Developed option; medium confidence |
| Safety | Mechanical locks—not an actuator—carry riding loads | Explicit principle; high confidence |
| Road class | Target ordinary bicycle/EPAC treatment, not L-category or mobility-chair treatment | Explicit direction; medium confidence pending review |

Numbers in this document are packaging hypotheses, not released design dimensions.

## 3. Vehicle architecture

```text
                         RIDER
              feet                    hands
                │                        │
      adjustable foot crank    independent rowing grips
                │                        │
           freewheel / gear       one-way clutches
                └──────────┬─────────────┘
                           │
                   common jackshaft
                           │
                 transmission / driven wheel
                           ↑
             ≤250 W continuous-rated assistance
             progressive cutoff by 25 km/h

      two steered/braked front wheels ── one driven rear wheel
```

The diagram shows the functional idea, not a selected chain line or gearbox. Direct mechanical foot drive is the conservative baseline. The motor may drive the rear wheel, crank, or an intermediate shaft, provided assistance behaviour and rated power comply with the selected classification.

## 4. Jack-knife transforming chassis

### 4.1 Structural concept

The chassis consists conceptually of front and rear structural modules connected by a controlled linkage near the rider’s hip/seat region. Contracting the linkage draws the wheel modules toward each other while raising and rotating the seat. Extending it lengthens the wheelbase, lowers the seat, reclines the backrest, and increases hip-to-crank distance.

A four-bar or related constrained linkage is preferred over several independent seat slides because one controlled degree of freedom can coordinate:

- wheelbase;
- seat height;
- backrest angle;
- crank-to-hip distance;
- step-through clearance; and
- stowed versus deployed hand controls.

### 4.2 Operating modes

| Mode | Geometry | Intended use | Propulsion envelope |
| --- | --- | --- | --- |
| **ACCESS** | Short wheelbase, high chair-height seat, upright back, generous knee clearance | Entry, exit, parking, indoor positioning | Stationary transformation; any manoeuvring only at a tightly limited walking speed after locks confirm |
| **URBAN** | Intermediate length and seat angle | Shops, constrained infrastructure, conversation, low-speed manoeuvring | Reduced speed/acceleration until an independently safe geometry is validated |
| **CRUISE** | Long wheelbase, low seat, reclined back, forward crank | Country cycle paths and efficient 25 km/h travel | Full legal assistance only after all ride locks confirm |

The conversation suggested packaging starting points of roughly 550–650 mm seat height in ACCESS, 300–400 mm in CRUISE, about 400–600 mm longitudinal transformation, and approximately 1.9–2.1 m deployed length. These are visualization aids only. Anthropometric mock-ups, stability analysis, path geometry, transport constraints, and structural design must determine actual dimensions.

### 4.3 Transformation sequence

**Entry:** park → apply independent parking brake → inhibit traction → verify level/stable condition → unlock transformation → move to ACCESS → engage access locks → move armrest/controls clear → rider transfers into seat → adjust supports → close controls → command CRUISE → engage primary structural locks → cross-check lock sensors → enable propulsion.

**Exit:** stop → parking brake → inhibit traction → verify safe transform conditions → unload or control drivetrain tension → release ride locks → transform to ACCESS → engage access locks → clear armrest/controls → rider stands or transfers.

Transformation while moving is not part of the reference concept. ACCESS or URBAN movement, if retained, must occur only in a mechanically locked configuration.

### 4.4 Load path and fault policy

The actuator moves the structure; it does not carry normal riding loads. Large pins, dogs, wedges, or over-centre locks create a direct structural load path in each permitted driving mode. Loss of electrical power must leave a locked chassis locked. A single position switch is not sufficient evidence of engagement: sensing should plausibly detect both commanded position and physical lock state.

Hazards requiring analysis include asymmetric or incomplete deployment, uncontrolled gravity motion, pinch/crush/shear zones, actuator runaway, lock contamination, fatigue around pivots, ground strike, rider entrapment, and emergency extraction. Manual recovery must be possible without placing a helper beneath an unsupported structure.

## 5. Running gear and stability

The baseline is a tadpole layout: two steered and independently braked front wheels, one rear wheel, with the heavy battery and transmission low and near the longitudinal centre. The layout supports stable braking and a clear rear drive path.

Required work includes rollover thresholds in every locked mode, centre-of-mass migration during transformation, Ackermann steering, scrub radius, trail/self-centring, bump steer, brake steer, rear-wheel unloading, turning circle, kerb interaction, tyre clearance, and behaviour after one brake channel fails.

A variable front track remains a research option, not a baseline road feature. A storage-only fold with a rigid deployed lock is more tractable than continuously changing width. Any drivable narrow and wide modes must each be treated as real configurations for stability, electromagnetic compatibility, control safety, and classification—not as an “inspection mode” and an undeclared operating mode.

## 6. Rider accommodation and biomechanics

The rider approaches a supportive seat rather than climbing over a frame or dropping into a low sling. The seat concept includes a broad base, supportive back, adjustable lumbar support, modest lateral support, swing-away armrests, and pressure management. Restraint requirements depend on risk analysis and final classification.

The foot crank must support meaningful exercise without forcing the problematic knee through an unsuitable range. Candidate adjustments include crank-to-seat distance, seat/back angle, pedal position, crank length, and possibly different effective crank radii left and right. Independent crank mechanisms are an option, but their benefit must outweigh complexity and unfamiliar failure modes.

No joint range, power, cadence, or transfer target is assumed from diagnosis. An adjustable stationary rig should establish comfortable motion and force envelopes before packaging the chassis.

## 7. Human and electric propulsion

### 7.1 Foot drive

Foot pedalling is the baseline qualifying human input and the primary exercise interface. It must transmit useful mechanical power to the driven wheel; a token pedal sensor with no meaningful drive path is outside the design intent.

For the conservative EU/German road configuration, motor assistance is enabled by genuine foot-pedal rotation, progressively reduces as speed approaches 25 km/h, and stops when pedalling stops. A start/push aid up to 6 km/h may be considered only if implemented within the German rule and verified against the complete applicable framework.

### 7.2 Rowing-inspired hand drive

Two long hand levers or grips produce a reciprocating motion comfortable for the shoulders, back, arms, and core. Cables, chains, links, cams, or variable-radius pulleys convert each stroke into rotation. Each side feeds the common jackshaft through an overrunning clutch:

```text
left pull  ── one-way clutch ──┐
right pull ── one-way clutch ──┼── jackshaft ── transmission
foot crank ── freewheel ───────┘
```

The return stroke must not back-drive the other hand or the feet. One hand may contribute while the other steers; both may work on a straight, predictable section. Ratio and force progression can be tuned so the weak ends of the stroke are lightly loaded and the strong middle produces more torque.

The legal wording is not uniform: German StVZO §63a names pedals **or hand cranks**, while German StVG §1(3) and the EU EPAC exclusion use pedalling language. Therefore the reference configuration does not depend on a rowing linkage being accepted as the qualifying input. The feet preserve the conservative pedelec basis; the hands add purely human mechanical power. Whether motor assistance may also be triggered by the hand mechanism requires written classification advice.

### 7.3 Speed above 25 km/h

Twenty-five kilometres per hour is the assistance cutoff, not a bicycle speed limiter. Above it, the motor contributes no propulsive assistance; the rider may continue through feet and hands. Gearing should allow this without overspeeding either limb group. The design must not include an override that restores motor assistance above the cutoff.

## 8. Steering and braking

The baseline uses conventional hand-reachable steering with strong straight-line stability and self-centring—not foot steering. Controls must allow immediate steering and braking when one or both hands have been propelling. Candidate layouts include a central or side control that can be acquired without searching, steering integrated into the hand-drive grips, or mechanically linked one-handed control.

Two independent service brakes are required for a bicycle. The heavy, low trike needs brake-force distribution based on dynamic wheel loads and resistance to brake steer. A parking brake is essential for transfer and transformation. Regenerative braking may smooth deceleration and recover energy, but it is supplementary: safe stopping cannot depend on battery acceptance, software, or traction power.

## 9. Energy system

The sizing requirement is the defined 24 km return journey plus reserve under specified rider mass, gradients, surface, wind, temperature, starts, tyre pressure, auxiliary loads, and battery ageing. Earlier conversation estimates ranging from 1–3 kWh came from different mobility-rover assumptions and are not adopted as a requirement. A pedelec duty-cycle model must set capacity.

The primary pack should remain low in the chassis and should not require the rider to lift it. Optional smaller range modules require keyed connectors, isolation, secure retention, state estimation, and regulatory review. Lighting must retain the supply required by StVZO after assistance shuts down.

A flywheel was discussed as a small high-power buffer for one braking/acceleration event and transformation energy. It is not baseline because burst containment, bearings, overspeed control, mass, losses, and the legal treatment of stored human energy create substantial complexity. Battery-based transformation with a manual recovery path is the reference solution.

## 10. Controls and information

The control system manages assistance, lock interlocks, traction inhibition during transformation, battery protection, diagnostics, lighting, and a useful return-range display. It must not hide safety-critical state behind a generic “ready” icon.

Minimum visible states should include driving mode, each required structural lock, parking brake, propulsion enabled/inhibited, assistance status, battery/reserve, and active faults. The controller must treat sensor disagreement, interrupted transformation, loss of communication, low voltage, and unintended command as explicit states. Mechanical braking and locked structural integrity remain available after software failure.

## 11. Regulatory architecture

The intended road configuration is:

- at least two wheels (three in the reference layout);
- genuine foot-pedal muscle propulsion;
- one auxiliary electric drive with maximum continuous rated power no greater than 0.25 kW;
- assistance that progressively reduces and ends by 25 km/h;
- assistance that ends when foot pedalling ends;
- optional German-compliant start/push assistance no faster than 6 km/h;
- no throttle for normal powered travel and no speed override;
- bicycle-compliant steering, two independent brakes, bell, lighting, and reflectors.

See [classification](../regulatory/classification.md), [Germany](../regulatory/germany.md), and [EU](../regulatory/eu.md). Classification must be confirmed against a frozen configuration before public-road testing.

## 12. Explicitly non-baseline ideas

The following remain valuable alternatives but are not part of the reference road configuration:

- three 300–500 W hub motors / electronically coupled 3WD;
- a 15 km/h motorized mobility-rover version;
- a user-selectable speed-limit override;
- foot steering with hand-crank-only propulsion;
- continuously variable track width while driving;
- pedal-by-wire with no mechanical human-to-wheel path;
- a flywheel as a significant propulsion-energy store; and
- an exoskeleton used to continue powered assistance beyond 25 km/h.

These should be evaluated as separate vehicle configurations and legal classes, not hidden modes of one approved vehicle.

## 13. Validation gates

1. **Needs gate:** observed transfer, posture, cadence, force, route, storage, and support requirements.
2. **Classification gate:** written review of the frozen reference configuration, particularly transformation and hand drive.
3. **Rig gate:** safe biomechanics and rowing-drive results on stationary adjustable fixtures.
4. **Analysis gate:** structural, fatigue, stability, steering, braking, energy, thermal, electrical, and fault analyses.
5. **Lock gate:** proof-load, fatigue, contamination, incomplete-engagement, power-loss, and manual-recovery tests.
6. **Rolling prototype gate:** private controlled-site tests at progressively increased speed and load.
7. **Road gate:** all construction rules met, classification recorded, hazards closed or accepted, and qualified review completed.

## 14. Open decisions

- Exact access, urban, and cruise dimensions and whether URBAN earns its complexity.
- Fixed or storage-folding front track.
- Rear hub, mid-drive, or jackshaft motor location.
- Chain, belt, gearbox, CVT, differential, and independent cadence architecture.
- Steering interface compatible with one- and two-hand propulsion.
- Battery capacity, voltage, chemistry, removal strategy, and charging interface.
- Mechanical lock topology and emergency recovery.
- Whether the hand drive ships on the first road prototype or follows after foot-only validation.

