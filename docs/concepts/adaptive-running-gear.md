# Adaptive Running Gear

[Deutsch](adaptive-running-gear_DE.md) · [Concepts](README.md)

**Status:** Exploratory later-option concept; not part of the first road configuration and not a validated design

For chassis geometry, see the [transforming chassis](transforming-chassis.md) and the [reference vehicle](reference-vehicle.md#4-jack-knife-transforming-chassis). Adaptive Running Gear is a later option, not a baseline feature of the first road prototype.

## Working decisions

Conversation decisions recorded 2026-08-28. They track how this concept should be treated; they are not validated requirements.

| Topic | Working decision |
| --- | --- |
| Role | Later option on the reference vehicle, not part of the first road prototype |
| Chassis host | Uses [Urban](reference-vehicle.md#42-operating-modes) geometry (compact or intermediate wheelbase, increased clearance). **Crawl** is a distinct running-gear mode, not a replacement for Urban, Access, or Cruise |
| Architectures | Three families remain **alternatives to track**, not one selected system: (1) obstacle-triggered pilot wheel and outrigger, (2) rider-operated or cam-phased crutches, (3) B2-W-inspired multi-degree-of-freedom articulation as a comparative lesson |
| Crawl controls | Conventional steering, braking, and rowing are not concurrent with crutch work. A crawl-mode stop/hold method remains an open engineering question |
| Rider | The [reference persona](reference-vehicle.md) has strong upper-body capacity. Crutch handling is analogous to ski poles. Pedalling at crawl speed may use maximum assistance inside the existing 250 W EPAC envelope, not a higher-power or throttle mode |
| First study | A short sequence of **two steps**, with sufficient tread or landing depth, near-square approach, very low speed, and a surface able to carry the deployed wheel load. Isolated rises or drops around **180–220 mm** remain a conversation-derived height band, not an accepted requirement |

Remaining packaging, tadpole support layout, mass and energy budget, and classification questions stay open until this topic is taken up in depth.

## Vision

> The rider should not have to think about the terrain. The vehicle should quietly adapt its running gear, suspension, and geometry so that curbs, pathway steps, uneven surfaces, and trail obstacles become routine rather than barriers.

Adaptive Running Gear extends the project from an adaptive road cycle toward a personal terrain vehicle without turning it into a conventional stair-climbing wheelchair or an all-terrain motor vehicle. If pursued as a later option, the intended system handles occasional, bounded obstacles along otherwise rideable routes while preserving rider dignity, comfort, control, and a plausible bicycle or pedelec design basis. The vision quote above is aspirational; the operating model remains that the rider stops, assesses the maneuver, and selects a running-gear mode.

## Design goals

- Negotiate isolated curbs, shallow trail or pathway steps, discontinuous grade changes, drainage edges, roots, ruts, and uneven transitions.
- Keep the occupied chassis and seat within a controlled pitch-and-roll envelope during ascent and descent.
- Transfer load before a main wheel crosses an edge, rather than allowing the vehicle to fall, pitch, or rely on momentum.
- Increase the effective support polygon only when needed, then retract into a compact road configuration.
- Keep every obstacle mechanism positively stowed and physically inhibited until the rider selects the specific function required.
- Deploy only the front, rear, left, or right support elements needed for the current ascent, descent, or stabilization phase.
- Integrate with the transforming chassis and suspension rather than adding an unrelated climbing appliance.
- Achieve the useful obstacle capability with the fewest articulated joints, actuators, sensors, and control states practical.
- Investigate passive, obstacle-triggered linkage geometry before adding powered actuation or electronic sensing.
- Use deterministic microcontrollers and simple local measurements rather than lidar, cameras, 3D reconstruction, or general autonomous navigation.
- Preserve conventional steering, braking, and propulsion in Access, Urban travel, and Cruise. Crawl is a separate mode in which those tasks are not concurrent with crutch work.
- Default to mechanically stable states during power loss, sensor disagreement, or incomplete deployment.
- Keep mass, width, energy consumption, maintenance, and visual complexity proportionate to the obstacles actually targeted.

## Problem statement

A long-range adaptive cycle may encounter short obstacles that are minor for a walking person but severe for a low, long, heavy tricycle carrying a rider:

- a curb or raised path boundary;
- one or two landscape, trail, or pathway steps rather than a continuous staircase;
- an abrupt transition between a ramp and level surface;
- a vertical discontinuity at a bridge, drainage channel, or damaged path;
- roots, rocks, erosion, potholes, cross-slope, or independently varying wheel heights; and
- a descent where the front wheel dropping first would create an unacceptable pitch transient.

Ordinary suspension can maintain tyre contact over small irregularities, but it cannot necessarily bridge a vertical edge or control the support polygon while a main wheel has no suitable contact surface. Simply increasing suspension travel may raise the centre of gravity, compromise road handling, and still fail to provide a controlled intermediate support point.

This concept is deliberately narrower than “climb a staircase.” The first study goal is a short sequence of **two steps**, with sufficient tread or landing depth, near-square approach, very low obstacle-mode speed, and a surface capable of carrying the deployed wheel load. Isolated rises or drops around **180–220 mm** are a conversation-derived height band, not an accepted requirement.

## Definition

**Adaptive Running Gear** is the coordinated set of deployable support wheels, articulated arms, structural pivots, actuators, locks, sensors, and control logic that temporarily changes how the vehicle is supported by the ground.

The term is intended to distinguish the system from:

- the primary road wheels and their normal suspension;
- an independent auxiliary drivetrain;
- passive anti-tip casters that merely catch a fall;
- fixed-width outriggers; and
- a general-purpose stair-climbing mechanism.

The running gear may lift, lower, brace, level, bridge, or transfer load. Its defining function is management of contact geometry and stability during a bounded obstacle event.

The following three architecture families are alternatives to track. None is selected. A later design pass may keep one, combine elements, or reject all of them.

## Deployable articulated support wheels

This family is **alternative 1**: a hung or reaching support wheel on an articulated arm, including the purely mechanical obstacle-triggered pilot described below.

The baseline concept uses small wheels carried on articulated structural arms. Depending on the final architecture, a forward pair, aft pair, or independently controlled left/right units could stow within the chassis envelope during ordinary travel.

When deployed, a support wheel could:

- reach forward to establish contact on an upper surface before a main wheel climbs;
- reach downward to support a controlled descent before a main wheel crosses an edge;
- widen or lengthen the support polygon during a cross-slope or wheel-lift event;
- carry a controlled share of vehicle weight while another wheel is unloaded; and
- act as temporary “landing gear” while the chassis pivots or translates between levels.

Candidate mechanisms include trailing or leading links, multi-link arms, telescoping links, rotary arms, or compact linkages combining rotation and extension. Wheel arms should have a load path into structural chassis nodes rather than into body panels or lightly loaded suspension brackets.

The design should investigate whether each support wheel needs free castering, constrained steering, alignment with the main wheel path, a brake, a one-way clutch, or only a freely rolling hub. A tri-star wheel cluster remains a comparative concept, but articulated arms appear better suited to this vehicle because their placement, load share, and chassis-leveling contribution can be controlled independently.

## Selective deployment and directional modes

Adaptive Running Gear is not intended to remain exposed during ordinary travel or to deploy every support whenever an obstacle is encountered. **Fully retracted, latched, and mechanically inhibited is the default condition.** The rider deliberately arms a specific obstacle function only after stopping and assessing the maneuver.

The rider-facing selector should contain directional modes rather than separate front/rear commands. Selecting a direction arms the complete front-and-rear system; the mechanism sequences its internal phases as the vehicle progresses:

| Mode | Enabled system | Mechanisms held inhibited | Intended function |
| --- | --- | --- | --- |
| **ASCEND** | Complete ascent system: front pilot/lift followed automatically by rear stabilization/lift | All descent feelers and descent release paths | Carry the whole vehicle upward through mechanically ordered front and rear phases |
| **DESCEND** | Complete descent system: front controlled lowering followed automatically by rear controlled lowering | All ascent pilots and ascent release paths | Carry the whole vehicle downward through mechanically ordered front and rear phases |
| **CRUTCH / CRAWL** | Independently hand-operated crutch arms or mechanically synchronized cam wheels | Ascent/descent triggers not used by the cycle; all Cruise releases | Smooth, deliberate progress across a short otherwise impassable patch |
| **LEVEL / STABILIZE** | Only the selected side or axle support | All lift/step triggers not needed for leveling | Address a bounded cross-slope, wheel lift, parking, or access-stability need |
| **STOWED / CRUISE** | None | Every pilot, feeler, support arm, and release trigger | Normal riding, transport, and storage |

Front and rear remain engineering phases, not choices the rider must manage. The rider selects **ASCEND** once; contact, wheel position, chassis travel, suspension position, or a phase latch advances the mechanism from front lift to rear stabilization. **DESCEND** works the same way in reverse terrain order. The rider may pause or abort, but should not have to decide when to switch axles.

The mode names describe system functions, not necessarily separate hardware. One arm may serve ascent and descent if a mechanical selector changes its trigger, direction, latch, or cam path. Conversely, safety or packaging may justify separate simple mechanisms rather than one highly configurable linkage.

### Arming and inhibition

A purely mechanical implementation could use a guarded selector lever, keyed shaft, sliding cam plate, dog clutch, or cable-operated latch bank. Selecting **ASCEND** would connect the upward-obstacle pilot wheel and the ordered rear-following mechanism while physically disconnecting or latching the complete descent system. Selecting **DESCEND** would do the reverse. Front-to-rear sequencing would occur automatically through wheel position, chassis travel, suspension state, or mechanical phase latches.

An electronically supervised version should preserve the same physical principle: software may monitor the selection, but unselected mechanisms remain mechanically latched or hydraulically/electrically isolated. A single wiring fault or software state should not be able to deploy ascent and descent gear together.

### Deployment rules

- Selection occurs only while stopped or below a tightly bounded crawl threshold with brakes applied.
- The selected directional mode arms the complete maneuver but releases only the mechanism required for the current phase.
- The rear phase remains latched until the required front-wheel state is mechanically or independently confirmed.
- Left/right independent deployment is permitted only where asymmetric support has been explicitly validated; otherwise the sides remain cross-linked.
- Completing or aborting a maneuver returns every selector, trigger, and support to a positively confirmed stowed state.
- Cruise propulsion remains inhibited until all obstacle mechanisms are stowed and retained, except the bounded crawl-speed pedalling and legal EPAC assistance permitted in `CRUTCH / CRAWL`.
- Manual recovery must allow a partially completed maneuver to be held, reversed, or lowered without accidentally switching direction or skipping a phase.

## Purely mechanical candidate: obstacle-triggered pilot wheel

A promising minimum-complexity mechanism is a small **hung pilot wheel** or obstacle follower positioned ahead of the main front wheels. During ordinary travel it is retracted or mechanically disconnected from the lifting linkage. Only after the rider selects **ASCEND** does it enter its active hanging position as the first phase of the complete ascent system. When its wheel contacts the vertical face of a curb or pathway step, the obstacle pushes the pilot wheel rearward relative to the advancing chassis. A bell crank, four-bar linkage, cam, cable, chain, or pushrod converts that relative motion into deployment of a larger load-bearing outrigger wheel.

The exact linkage direction remains to be developed, but the intended mechanical logic is:

```text
NORMAL APPROACH

             pilot wheel
                 o
                /
     front O---/---------------- chassis
             outrigger stowed


PILOT CONTACTS STEP

                       upper surface
                   ───────────────────
                 o │
     front O-----\│   pilot is pushed rearward
                  │
──────────────────┘ lower surface
                    ↘ linkage rotates outrigger


LOAD-TRANSFER POSITION

                       upper surface
                   ───────o───────────  deployed support
                         /
     front O------------/------------- chassis rises/advances
──────────────────┘ lower surface
```

The pilot wheel is the sensor, the linkage is the controller, and the over-centre geometry or latch is the lock. No electronic sensor, microcontroller, or powered actuator is inherently required.

### Provisional ascent sequence

1. The vehicle approaches slowly and approximately square to the obstacle.
2. The lightly loaded pilot wheel contacts the vertical face before the main front wheels.
3. Continued forward force moves the pilot link rearward or upward relative to the chassis.
4. The input motion rotates the outrigger arm over the edge and down toward the upper surface.
5. The outrigger reaches a load-bearing position and engages an over-centre condition, ratchet, pawl, or positive mechanical latch.
6. Continued force through the normal drivetrain loads the outrigger. The linkage redirects part of that force into chassis lift and front-axle unloading.
7. The main front wheels roll across the reduced effective vertical difference instead of striking the full step face under full load.
8. Once the main wheels reach the upper surface, suspension or linkage travel triggers a controlled release, reset, or stow sequence.

The mechanism does not create energy or independent propulsion. The rider and normal pedelec drivetrain still provide the work needed to raise the vehicle’s mass. Mechanical advantage trades motion and travel for force; it may reduce peak tyre force and required traction, but it will increase linkage travel, internal load, or the forward force/distance required.

### Mechanical elements to investigate

- a sprung or gravity-return pilot arm that follows ordinary ground without carrying meaningful vehicle load;
- an adjustable input height so harmless surface texture does not trigger deployment;
- a cam or multi-link ratio that provides high mechanical advantage near first load transfer;
- a dashpot, rotary damper, elastomer, or friction element to prevent impact-driven snap deployment;
- an over-centre link or positive latch so the support does not collapse when loaded;
- a torque limiter, shear pin, or compliant element for obstacles outside the design envelope;
- a one-way clutch or ratchet preventing rollback during the lift phase;
- a deliberate reset condition after the main front wheels are securely on the upper level; and
- a manual release and recovery control accessible without reaching into a pinch zone.

### Scope and limitations

This first mechanism is **front-wheel ascent assistance only**. It does not by itself:

- support the rear wheel during the later part of an ascent;
- detect an approaching downward edge;
- control a descent;
- correct a diagonal approach or large left/right height mismatch; or
- decide whether the upper surface is deep, strong, or unobstructed enough to accept the support wheel.

It may also deploy unintentionally against bollards, roots, debris, walls, pedestrians’ feet, or objects that resemble the target obstacle. The pilot geometry must reject small bumps and ordinary roughness, and the rider needs a way to disable or mechanically secure the system outside the selected running-gear mode.

### Related purely mechanical mechanisms

The same design philosophy can support other phases, but each requires its own trigger geometry:

- **Rear-wheel ascent stabilization:** front-wheel position, chassis translation, or a trailing follower could mechanically release an aft support only after the front axle is established on the upper level. The aft gear would brace and unload the rear wheel as it climbs.
- **Descent preparation:** a forward drop feeler could fall over an edge and release a support arm that reaches the lower surface before the main wheel crosses. This is more safety-critical than ascent because detection may occur too late unless the feeler projects far enough ahead.
- **Rear-wheel descent stabilization:** a mechanically sequenced trailing arm could remain load-bearing until the rear wheel reaches the lower level, preventing a sudden aft drop or pitch change.
- **Left/right accommodation:** paired mechanisms could be mechanically cross-linked for symmetrical deployment, or allowed limited differential movement through a balance beam. Fully independent passive sides could create dangerous twist if only one triggers.

These mechanisms should be evaluated before assuming that every support wheel needs an actuator. A hybrid may ultimately be simplest: passive obstacle-triggered deployment and mechanical locking, with a small powered or manual mechanism used only for reset, stowage, or controlled release.

## Deployable “crutch” concepts

This family is **alternative 2**: rider-operated crutches or synchronized cam wheels. **Crawl** is a separate running-gear mode. Conventional steering, braking, and rowing are not used at the same time as crutch work. The crutches are handled analogously to ski poles. Pedalling may continue at crawl speed with maximum assistance inside the existing 250 W EPAC envelope.

The simplest crutch concept is independently controlled by the rider’s hands. A more synchronized alternative uses deployable **eccentric cam wheels** or rotating, roller-ended arms. In either case, the temporary crutches repeatedly plant, accept load, lift or shift the chassis through a small controlled arc, unload, and return for the next cycle.

The resulting motion is closer to walking with crutches than ordinary rolling:

```text
1. PLANT                2. LIFT / ADVANCE          3. TRANSFER

       chassis                 chassis                  chassis
    O-----------O           O-----------O            O-----------O
        \   /                    |   /                    \   |
         o o                     o  o                      o  o
       crutches              cam under load           load changes side/phase
```

Possible implementations include:

- a round wheel on an eccentric axle, producing a predictable rise-and-fall cycle;
- a shaped cam wheel whose effective radius changes through one rotation;
- a rotating arm with a small free-running roller at its end;
- paired cams phased 180 degrees apart so one remains load-bearing while the other resets; or
- front and rear cam pairs coupled by a shaft, chain, timing belt, or indexed linkage to preserve phase.

The geometry should seek a **slow, smooth, quasi-static** chassis path rather than a hopping or lurching gait. Multiple smaller cam lobes, compliant tyres, dampers, suspension coordination, or overlapping support phases may reduce vertical acceleration and prevent the rider from feeling each support transfer.

### Rider-operated crutch variant

The simplest version may dispense with synchronized camshafts and automatic cycling altogether. A left and right crutch arm could each terminate in a small wheel or roller and connect mechanically to a hand lever beside the rider. The rider deploys, plants, pivots, loads, unloads, and retrieves each side much as a person coordinates actual crutches.

In this version:

- the **hands control support placement and pivoting**;
- the **arms and upper body may contribute lifting or bracing effort** through lever mechanical advantage;
- the **feet continue pedalling** to provide forward motion at crawl speed;
- the normal pedelec drive may provide maximum assistance inside the existing 250 W EPAC envelope at that crawl speed; and
- neither crutch requires a separate traction motor, terrain computer, or automatic gait controller.

A possible crawl rhythm is:

1. Stop or reduce to the validated crawl speed and select `CRUTCH / CRAWL`.
2. Release and lower the left crutch using its hand lever; confirm its roller is planted and its pivot or load latch is engaged.
3. Pedal forward a short distance while using the left crutch to brace, lift, or control chassis attitude.
4. Plant the right crutch before the left reaches the end of its safe support arc.
5. Transfer support gradually to the right side, unload and reposition the left, and continue alternating as required.
6. Once all primary wheels have reliable contact beyond the difficult patch, unload, fold, and positively latch both crutches before leaving crawl mode.

The two sides should be independently operable so the rider can respond to different left/right ground heights. Independence does not mean unconstrained movement: each arm still needs stable planted positions, travel limits, overload protection, and a way to prevent sudden collapse or uncontrolled swing.

### Human interface

Candidate controls include long direct levers, compact levers driving cables or pushrods, ratcheting handles, or removable crutch handles that dock beside the seat. Lever geometry could provide high mechanical advantage near the load-bearing part of the stroke and a faster return while unloaded.

The rider should be able to:

- feel ground contact and increasing crutch load through the control rather than relying only on an indicator;
- lock or hold a planted crutch without continuously sustaining the full vehicle load by arm strength;
- operate one side while the other remains securely planted;
- release load deliberately without a snap, drop, or handle kickback;
- abandon the sequence and leave the vehicle mechanically supported; and
- stow both handles and arms outside steering, pedalling, transfer, and road-clearance envelopes.

Steering and braking remain required vehicle functions, but they are not concurrent with crutch work. Crawl replaces the cruise control set: the hands work the crutches analogously to ski poles, the feet pedal at crawl speed, and conventional steering and rowing are not used. A dedicated crawl-mode stop, hold, and abort method is still required; this page does not treat “no braking” as a requirement. Candidate stop/hold paths include a parking brake already applied before crawl, a foot-accessible hold, or another control that does not reclaim both hands from the crutches.

### Why manual operation may be preferable

- The rider chooses the placement and timing directly instead of trusting imperfect terrain detection, analogously to planting ski poles.
- Each side can respond to the actual surface independently.
- The mechanism can be mostly levers, pivots, cables, latches, springs, and small rollers.
- Failure behavior is visible and tactile.
- Human arm input is easy to distinguish from a hidden autonomous traction system.
- Development can begin with a static rig before adding any automatic functions.

The tradeoff is physical and cognitive demand. Crutch forces, handle travel, coordination, reach, grip strength, shoulder loading, fatigue, and the rider’s ability to pedal simultaneously must be measured rather than assumed. The mechanism should amplify and hold force; it should not expect the rider’s arms to suspend the full occupied vehicle continuously.

### Intended use

`CRUTCH / CRAWL` is a special recovery and terrain-negotiation function for a short section that would otherwise be impassable, such as deep ruts, staggered stones, a broken pathway transition, a narrow eroded patch, or a sequence of small discontinuities that cannot be handled as one ASCEND or DESCEND event.

It is not:

- a normal suspension mode;
- a high-speed rough-terrain system;
- intended for ordinary road or cycle-path travel;
- a substitute for route judgment; or
- permission to attempt stairs, loose slopes, or terrain outside a validated envelope.

The vehicle must stop before deployment. A guarded mode selector then mechanically releases the crutch gear and simultaneously imposes a very-low-speed ratio or crawl-speed limit. Pedalling at that crawl speed may use maximum assistance inside the existing 250 W EPAC envelope; this is not a throttle, a second traction system, or a higher-power class. Returning to Cruise requires complete retraction, positive retention, and confirmation that every manual crutch and any cam mechanism are disengaged from the drivetrain and control envelope.

### Energy and propulsion boundary

Both manual crutches and a cam mechanism require work to lift and translate the occupied vehicle. In the manual version, the rider’s arms place and pivot the supports while the feet pedal the vehicle forward. In a cam version, the timing mechanism may be mechanically coupled to the normal human-powered drivetrain through a very low reduction gear, clutch, and torque limiter. The rider’s input—and only legally permitted pedelec assistance where applicable—supplies the energy.

The cams may generate fore/aft reaction forces as they rotate against the ground, so their functional effect requires careful classification. A separately powered cam drive that walks the vehicle forward without qualifying human input could become an independent propulsion system regardless of whether its contact elements are called crutches, supports, or running gear. The design must be assessed by what it does, not by its name.

### Deployment and phasing

- Crutch elements remain folded inside the road envelope and mechanically disconnected during Access and Cruise.
- Deployment can occur only while stationary, braked, and in the appropriate high-clearance chassis geometry.
- At least three stable ground contacts—or an equivalently proven support polygon—should be maintained throughout a cycle.
- Left/right and front/rear cam phases must prevent simultaneous loss of support and limit chassis twist.
- A mechanical index, Geneva mechanism, keyed shaft, or positive timing drive should preserve phase after shock or partial reversal.
- The system must stop in a statically supportable phase after loss of rider input, power, or control signal.
- Reverse or retreat needs an intentional sequence; simply rotating the cam backward may release a latch or enter an unstable phase.
- Retraction should be possible only from a defined home phase with every main wheel confirmed capable of carrying load.

### Principal risks

- oscillatory rider loads, motion sickness, pressure peaks, or restraint loads;
- very high contact stress at a small crutch roller or cam lobe;
- slip when a planted element produces both vertical and horizontal reaction force;
- phase loss or backlash between mechanically coupled units;
- trapping stones, roots, clothing, or body parts in the rotating envelope;
- structural fatigue from repeated lifting cycles;
- the mechanism becoming a pole-vault pivot when it catches unexpectedly;
- no conventional steering while the crutches carry significant load, so the crawl path must be aligned before entry; and
- ambiguous legal treatment if cam rotation contributes net forward travel.

The concept should initially be modeled as a quasi-static linkage and tested with ballast on a restrained rig. Smoothness, support polygon, contact forces, and safe stopping phase matter more than achievable crawl speed.

## Obstacle negotiation sequence

The following sequences describe the required vehicle-level states, not one mandatory actuator architecture. A passive linkage may combine several steps mechanically; an assisted version may perform them under microcontroller supervision. Both are hypotheses for simulation and low-energy prototype testing.

### Ascent

1. Detect or designate an obstacle and stop at a validated approach distance.
2. Confirm low speed, acceptable steering angle, surface geometry, available clearance, actuator health, and sufficient traction/braking reserve.
3. Transform from Cruise toward Urban geometry: reduce excessive wheelbase if required, increase clearance, move the rider toward the validated posture, and level the seat.
4. Deploy the forward support wheels onto the upper surface or another verified load-bearing contact point.
5. Prove contact and mechanical lock before transferring substantial load.
6. Shift part of the front load into the deployed gear, reducing the pitch moment and unloading the main wheel as required.
7. Advance using the normal human/pedelec drivetrain while the support wheels roll and stabilize; the support arms coordinate height but do not independently drive the vehicle forward.
8. Bring the main front wheels onto the upper level and restore their controlled suspension load.
9. If the rear transition requires it, deploy or reposition aft support wheels before the rear wheel crosses the edge.
10. Advance the rear wheel onto the upper level, verify stable main-wheel contact, unload and retract the support gear, then return to Access or Cruise mode as appropriate.

### Descent

1. Stop before the edge and verify the drop, landing surface, alignment, clearance, and braking reserve.
2. Transform to Urban and arm the selected running-gear mode. Establish the required high-clearance, compact, seat-level geometry.
3. Extend the forward running gear down to the lower surface and prove load-bearing contact and lock.
4. Transfer load gradually to the support wheels before any main front wheel leaves the upper level.
5. Roll forward under controlled braking while lowering the chassis so the main front wheels contact the lower level without a free drop.
6. Re-establish main front-wheel load, then support and lower the rear portion with the aft gear if the geometry demands it.
7. Confirm all primary wheels are loaded and stable before retracting the running gear.

Descending should be treated as the primary safety case because gravity, braking, and forward pitch can combine even when little propulsion is required.

## Integration with the transforming chassis

Adaptive Running Gear does not add a third chassis family. The [reference vehicle](reference-vehicle.md#42-operating-modes) keeps Access, Urban, and Cruise. If this later option is pursued, running-gear functions use **Urban** geometry (compact or intermediate wheelbase, increased clearance, seat held within a safe attitude). **Crawl** is a running-gear mode in that geometry, not a replacement for Urban.

| Chassis mode | Indicative geometry | Running-gear state | Purpose |
| --- | --- | --- | --- |
| **Access** | Short, tall, upright, open transfer path | Retracted, or a separately validated parking stabilizer if that function shares hardware | Entry, exit, loading, parking, and caregiver access |
| **Urban** | Compact or intermediate wheelbase, increased clearance | Host geometry for later running-gear modes; stowed until a running-gear mode is armed | Low-speed manoeuvring today; later host for bounded obstacle work |
| **Cruise** | Long, low, reclined, aerodynamically efficient | Fully retracted and positively retained | Normal road and cycle-path travel |

| Running-gear mode (later option) | Armed from | Intended function |
| --- | --- | --- |
| **STOWED / CRUISE** | Any locked chassis mode | Normal riding; every pilot, feeler, support arm, and release trigger inhibited |
| **ASCEND** | Urban | Complete ascent system; descent gear inhibited |
| **DESCEND** | Urban | Complete descent system; ascent triggers inhibited |
| **CRUTCH / CRAWL** | Urban | Separate slow mode: crutches or cam cycle; conventional steering, braking, and rowing not concurrent; crawl-speed pedalling with maximum legal EPAC assistance |
| **LEVEL / STABILIZE** | Urban, or Access if a parking-stabilizer share is later validated | Selected side or axle support without initiating a climb or descent sequence |

Transitions must be sequenced. Running-gear deployment should not begin from an incompatible Cruise geometry, ascent and descent functions must remain mutually inhibited, and the vehicle should not accelerate into Cruise until every support is retracted or in a separately validated state. This sequencing may be implemented by mechanical selectors and latches, a simple controller, or both; it must not depend on ambiguous rider interpretation of one generic Obstacle mode.

## Relationship to the suspension system

The running gear supplements rather than replaces the [primary suspension](../engineering/suspension.md).

- **Suspension** manages continuous surface variation, tyre contact, comfort, damping, roll behaviour, and road handling.
- **Adaptive Running Gear** creates temporary contact points and support geometry when ordinary wheel travel cannot safely span the discontinuity.

During obstacle mode, suspension position and wheel load are useful control inputs. The system may temporarily change spring/damper settings, cross-linking, ride height, or anti-roll behaviour, but the suspension must not fight the running-gear actuator or unexpectedly release stored energy during load transfer.

Key integration risks include chassis jacking, wheel lift, bump steer, sudden roll-centre movement, suspension topping or bottoming, high local tyre loads, actuator load sharing, and unstable control loops in which active suspension and articulated supports both attempt to level the body.

## Load transfer versus propulsion

The intended principle is:

> The articulated supports manage load and stability; they do not constitute an independent forward-propulsion system.

The support system may consume electrical energy to deploy, retract, lift, lower, lock, level, or regulate contact force. A support wheel may roll as the primary drivetrain advances the vehicle. That differs functionally from applying wheel torque that generates independent net forward travel.

Forward motion should remain attributable to the normal mechanical human drivetrain and, where permitted, its compliant pedelec assistance. The running gear should not provide a hidden throttle, crawler drive, or second traction system. Any braking or anti-rollback device on a support wheel should be designed as a safety function rather than used to ratchet the vehicle forward.

This distinction is a design and documentation target, not a settled legal conclusion. Regulators may assess the complete vehicle and the functional effect of powered actuators, not merely the names assigned to them. Every mode must be included in classification review; see the [classification matrix](../regulatory/classification.md), [German research](../regulatory/germany.md), and [EU context](../regulatory/eu.md).

## Minimum-complexity sensing and control

The design hierarchy is:

1. **Mechanical geometry:** use followers, cams, links, springs, dampers, latches, hard stops, and over-centre locks to make the safe action emerge from obstacle contact and chassis motion.
2. **Mechanical interlocks and rider control:** add mode selectors, manual releases, brake interlocks, and visible state indication without requiring computation.
3. **Simple electronic supervision where justified:** use microcontrollers and scalar sensors only for facts or sequences that cannot be made sufficiently safe and reliable mechanically.
4. **Complex perception:** lidar, computer vision, 3D mapping, and autonomous terrain planning remain outside the baseline.

If electronics are needed, the baseline remains a **bounded electromechanical sequence**, not an autonomous terrain robot. The rider stops, aligns the vehicle, requests the selected running-gear mode, and remains responsible for accepting the maneuver. A small microcontroller system verifies simple measurements, enforces interlocks, and moves the mechanism through known states.

The preferred electronic architecture, if used, is one safety-oriented supervisory microcontroller, with additional small local microcontrollers only when wiring or actuator control justifies them. It should not require a GPU, a general-purpose operating system, a network connection, cloud processing, simultaneous localization and mapping, or a continuously reconstructed 3D model.

### Candidate sensors

- wheel-speed pulses, steering-angle range, brake state, and zero/low-speed confirmation;
- a simple inertial sensor for chassis pitch and roll;
- limit switches, Hall sensors, or low-cost encoders for actuator and suspension position;
- actuator current sensing for obstruction, overload, and contact inference;
- short-range ultrasonic/sonar or time-of-flight sensors aimed forward and downward to estimate edge distance, rise/drop height, and landing clearance;
- simple contact switches or load-threshold sensors at support wheels where motor current is not sufficient evidence;
- positive mechanical-lock confirmation; and
- rider-presence, restraint, access-opening, emergency-stop, and mode-command inputs where required.

The sensor set should be reduced further when mechanical geometry can make a state self-evident. For example, a hard stop plus an independently sensed lock may be safer and simpler than continuous joint-angle estimation. Redundant sensing should be added only for safety-critical facts, not to build a richer terrain model.

### Automation levels

1. **Manual command with hard interlocks:** the rider requests each phase; the controller only permits safe actions.
2. **Assisted sequence:** the rider authorizes the selected running-gear mode, and the system performs a monitored deployment sequence with pause/abort controls.
3. **Bounded automatic positioning:** after rider authorization, simple range and contact measurements stop each arm at its required position and verify that the next load-transfer step is permitted.

The baseline does not automatically recognize general terrain or deploy while cruising. Automatic behavior must never surprise the rider by changing track, wheelbase, height, or support forces. If range measurements disagree, time out, or fall outside the validated envelope, the controller stops and requests manual recovery rather than attempting to interpret the scene.

## Technology precedent: Unitree B2-W

This family is **alternative 3**, tracked as a comparative architecture lesson rather than a candidate to copy. The [Unitree B2-W](https://www.unitree.com/b2-w/) is a useful technology precedent for Adaptive Running Gear. It is **not** a direct vehicle architecture, a regulatory precedent, or evidence that the same maneuvers are safe with a human rider. It is a fully machine-propelled industrial quadruped robot whose four driven wheels are mounted at the ends of multi-jointed legs. Nevertheless, it demonstrates how rolling wheels, articulated limbs, perception, and fast load redistribution can be combined in one mobile platform.

Unitree describes the B2-W as coordinating perception and motion control to maintain balance over stairs, slopes, barriers, grass, stone, and gravel. Its product information attributes rough-surface stability to rapid, coordinated responses across multiple leg joints. Published figures include approximately 85 kg total mass, 225 mm wheel diameter, a standing payload of 120 kg, a walking payload above 40 kg, continuous travel over 20–25 cm stairs, forward ascent or descent of a 40 cm step, and slopes above 45 degrees. Unitree cautions that capabilities vary by configuration and application, and that some functions require human operation or secondary development. These manufacturer figures are examples of the platform’s claimed envelope, not design targets for this project.

The related B2 platform documentation lists configurable 3D lidar, depth cameras, optical cameras, and substantial onboard computing, while Unitree’s B2/B2-W application documentation describes laser mapping and autonomous navigation. Those systems help explain the robot’s broad autonomy, but they are intentionally **outside the baseline scope** of Adaptive Running Gear. This project takes inspiration from the articulation and load-management architecture, not from the B2-W sensing stack.

### What the example demonstrates

- **A wheel need not sit at a fixed chassis coordinate.** A multi-jointed carrier can control wheel height, fore/aft placement, lateral placement, and contact force while the wheel continues rolling.
- **Rolling efficiency and obstacle articulation can coexist.** Wheels handle efficient continuous travel; articulated joints handle discrete terrain and body attitude.
- **The useful control variable is not only joint position.** Coordinated control must consider body pitch and roll, wheel contact, load distribution, terrain geometry, velocity, and the next intended contact point.
- **Four independently articulated contact points can reshape the support polygon.** One wheel can rise, reach, unload, or reposition while the remaining contacts stabilize the body.
- **Terrain capability emerges from the whole system.** Geometry, simple measurements, mechanical articulation, controlled sequencing, and fault handling matter together; adding a hinged outrigger alone does not create comparable capability.

### Translation into the Adaptive Running Gear concept

| B2-W characteristic | Relevant lesson | Deliberate project constraint |
| --- | --- | --- |
| Four wheel-ended articulated legs | Each ground contact can be placed and loaded independently | Begin with a smaller number of deployable support arms; avoid unnecessary degrees of freedom |
| Driven wheels on every leg | A wheel can keep rolling while its carrier changes geometry | Main legal drivetrain provides forward motion; support wheels do not become an independent traction system |
| Dynamic body stabilization | Coordinate articulation to control pitch, roll, clearance, and contact force | Occupied-vehicle motions must be slower, bounded, predictable, and mechanically secured |
| Perception coupled to motion control | Measured clearance, height, attitude, and contact can govern each next action | Use sonar/time-of-flight, position, current, contact, and tilt sensing rather than lidar or 3D scene reconstruction |
| High-bandwidth powered joints | Rapid load redistribution enables difficult terrain maneuvers | Prefer quasi-static load transfer and positive locks over continuous dependence on actuator torque |
| Wheel-leg geometry | Rolling and stepping behaviors can share a structural architecture | Optimize for a short two-step sequence and bounded pathway obstacles, not general quadruped locomotion or stair climbing |

### Important differences

The B2-W’s wheels are active propulsion devices and its legs continuously support an unoccupied robot. Adaptive Running Gear is intended for an occupied cycle whose support arms primarily stabilize and transfer load. The project therefore cannot simply scale up a robot leg or copy its control behavior.

An occupied vehicle must account for rider injury tolerance, comfort, restraint, emergency exit, public proximity, redundant braking, mechanical locking, graceful power-loss behavior, and a much less permissive regulatory context. Dynamic recovery maneuvers that are acceptable for a robot—jumping, rapid body acceleration, wheel slip, momentary unstable states, or recovery by catching itself—may be unacceptable for a rider-carrying platform.

The most valuable B2-W lesson is consequently architectural rather than literal:

> A four-wheeled platform can treat wheel position and wheel load as adaptive variables rather than fixed properties of the chassis.

For this project, that idea should be translated into slow, fail-safe obstacle negotiation: the rider identifies and aligns with the discontinuity; simple sensors verify height, clearance, attitude, and contact; the controller locks the articulated gear, transfers load, permits advance through the normal drivetrain, and restores the road configuration.

### Questions prompted by the B2-W example

- Could four-wheel articulation replace separate “main wheel” and “outrigger” roles, or would that make road operation too heavy and complex?
- What is the minimum number of actively controlled degrees of freedom needed to achieve most of the useful body-leveling and contact-placement behavior?
- Can quasi-static control and mechanical locks provide the needed capability without robot-like actuator bandwidth and energy consumption?
- Which minimum state variables—body attitude, actuator position/current, support contact, wheel motion, and one-dimensional range/height—are essential for a first safe prototype?
- Can fixed sensor placement and known linkage geometry reduce obstacle measurement to a few distances rather than a terrain map?
- How should an occupied vehicle decide that an obstacle is outside its envelope and present a safe retreat rather than attempt dynamic recovery?
- Can the transforming chassis provide much of the gross height and wheelbase change, leaving the running gear responsible only for final contact placement?

### Source note

Manufacturer information reviewed 2026-08-28: [Unitree B2-W product page](https://www.unitree.com/b2-w/), [Unitree B2 platform and sensor configurations](https://www.unitree.com/b2/), and [Unitree Explore application documentation](https://www.unitree.com/app/b2/). Manufacturer performance claims require independent verification before use as engineering evidence.

## Safety systems and mechanical locking

- Positive mechanical locks at every load-bearing deployed state; actuator holding torque alone is insufficient.
- Positive stowage latches and trigger inhibitions that prevent any pilot, feeler, or support from becoming active until its directional mode is deliberately selected.
- Mutual exclusion between ascent and descent mechanisms, preferably enforced mechanically as well as logically.
- A physical crawl-mode reduction or speed governor that makes normal travel speed unavailable whenever cam/crutch gear is deployed.
- Phase-preserving brakes or locks that leave the crutch mechanism statically stable when motion stops unexpectedly.
- Load-holding latches at each manual crutch so the rider never has to sustain the occupied vehicle continuously through hand force alone.
- Independent release control that prevents unloading one crutch before the opposite side or primary wheels can safely accept the transfer.
- Independent confirmation of position and lock engagement, preferably using diverse sensing principles.
- Brake and speed interlocks before deployment, plus acceleration inhibition while the mechanism is in an unsafe intermediate state.
- Anti-rollback and controlled-lowering provisions for ascent, descent, and power loss.
- A defined safe response to asymmetric deployment, lost contact, overload, sensor disagreement, actuator stall, or structural deflection.
- Manual recovery or lowering that can be performed without placing a helper in a crush zone.
- Redundant support or a catch mechanism so one failure does not create an immediate rollover or uncontrolled drop.
- Pinch, shear, entrapment, hot-surface, and ground-strike protection around arms, pivots, and stowage pockets.
- Clear mode indication and rider feedback showing whether the vehicle is safe to move, hold, transform, or exit.
- Structural load limits and refusal logic when obstacle geometry, payload, cross-slope, traction, or landing quality exceeds the validated envelope.
- Physical retention that prevents a stowed arm from deploying at Cruise speed after a latch, wiring, or software failure.

The system needs a fault tree and hazard analysis covering the complete maneuver, not only the actuator hardware. A mechanically locked but poorly placed wheel can still create a dangerous pivot point.

## Future concepts within the simplicity constraint

### Simple obstacle measurement

Several fixed ultrasonic or time-of-flight measurements could estimate the distance to an edge, approximate rise or drop height, and confirm that a landing area exists. A small sensor bar or mechanically swept single-axis range sensor may be considered if fixed sensors leave important blind spots. The goal is a small set of conservative scalar measurements, not an image, point cloud, or 3D terrain model.

### Confirmed pre-deployment

After the rider stops and authorizes the selected running-gear mode, range sensors could confirm that the vehicle is within the permitted approach window and pre-position the supports. The system should not predictively deploy during Cruise mode or rely on route history to decide that an obstacle is safe.

### Adaptive wheelbase

The transforming chassis could shorten the wheelbase to reduce break-over risk and required arm reach, then lengthen after the obstacle. Wheelbase change must not destabilize the rider or create unintended propulsion.

### Active leveling

Coordinated support-arm and suspension control could maintain seat attitude over cross-slope and staggered wheel heights. Comfort leveling must remain subordinate to tyre contact, structural limits, and rollover stability.

### Additional possibilities

- Independently deployable left/right supports for cross-slope and single-wheel obstacles.
- Exchangeable wheel or foot modules for soft ground, snow, or delicate indoor surfaces.
- A passive or spring-assisted emergency deployment state that does not depend on full electrical power.
- Optional wired service telemetry for recording distances, times, currents, positions, and fault states during testing, without making connectivity part of operation.

## Open engineering questions

### Functional envelope

- First study goal (conversation decision, 2026-08-28): a short sequence of two steps. Maximum rise, drop, gap, tread depth, edge radius, cross-slope, and approach angle beyond that band remain open.
- Which surfaces are too weak, slippery, loose, or irregular for a safe support-wheel contact?
- What payload and centre-of-mass range must the mechanism handle?

### Architecture

None of the three architecture families is selected; they remain alternatives to track.

- How many support wheels are required, and where should their pivots attach?
- Should front and rear units be paired, fully independent, telescoping, or multi-link?
- Can a hung pilot wheel distinguish a target step from roughness, debris, a wall, or a person without electronic classification?
- What linkage path places the outrigger on the upper surface before accepting load while remaining compact when stowed?
- Can a passive mechanism achieve sufficient lift without excessive forward force, travel, impact load, or risk of jamming?
- What purely mechanical event should latch, release, and reset front- and rear-support mechanisms in the correct order?
- What selector can arm ascent, descent, and stabilization functions independently while guaranteeing that all other triggers remain physically disconnected?
- Can one support arm serve opposing directions without creating a complicated, ambiguous, or failure-prone reversing linkage?
- Which phases require separate hardware, and which can safely share an arm, wheel, pivot, or lock?
- Can cam/crutch wheels share hardware with ascent/descent supports, or should their repeated-cycle loads and timing remain mechanically separate?
- What hand-lever force and travel let the rider place and load each crutch while continuing to pedal comfortably? The reference persona has strong upper-body capacity; crutches are analogous to ski poles, but force, travel, and fatigue still need measurement.
- Crawl does not require concurrent steering, braking, and rowing. What dedicated crawl-mode stop, hold, abort, and retreat method keeps the vehicle controllable without reclaiming both hands from the crutches?
- Which cam profile and phase relationship produce the smoothest chassis path while maintaining a safe support polygon?
- Can the crutch cycle stop safely at any angle, or must a mechanical index force it to one of several stable dwell positions?
- How can controlled retreat work while crutch elements carry a substantial share of the load?
- Is a cross-linked left/right mechanism safer than independent followers when the approach is not perfectly square?
- Can one mechanism serve access stabilization, parking, and obstacle negotiation without unsafe compromises?
- How are unsprung mass, stowed volume, aerodynamic drag, mud, water, stones, ice, and corrosion managed?

### Dynamics and control

- What load-transfer trajectory minimizes pitch, roll, wheel slip, actuator force, and rider discomfort?
- How are suspension and running-gear controllers prevented from fighting each other?
- What happens if a support wheel loses contact after accepting load?
- What obstacle-mode speed and braking strategy remain controllable on ascent and descent?
- How does the vehicle reverse or retreat safely from an aborted maneuver?

### Structures and actuation

- What peak and fatigue loads occur at arm pivots, locks, and chassis interfaces?
- Can electromechanical actuators meet the required force, travel, duty cycle, backdrivability, and environmental sealing targets?
- Is hydraulic actuation justified, or would leakage, service, and failure behavior outweigh its power density?
- Can gravity-assisted movement and counterbalance reduce actuator size without compromising fail-safe behavior?

### Human factors and accessibility

- How much rider confirmation and attention should a maneuver require?
- Can the rider remain comfortably restrained and still perform an emergency exit?
- What feedback is understandable to riders with different sensory, cognitive, or motor abilities?
- Can a helper recover the vehicle without exceptional strength or exposure to pinch zones?

### Regulation and validation

- How will German and EU authorities classify powered lift, leveling, and support functions on a bicycle or EPAC?
- What functional behavior would cause a support mechanism to be treated as propulsion?
- Must every deployable-width and wheel-count state satisfy bicycle equipment and infrastructure requirements?
- Which machinery, functional-safety, vehicle, cycle, wheelchair, or lifting-device standards provide useful test methods even when not directly mandatory?
- What private-site test progression is required before an occupied obstacle trial?

## Proposed evidence plan

1. Define a two-step obstacle envelope and complete quasi-static free-body and rollover analysis.
2. Build a kinematic model including chassis transformation, suspension travel, arm reach, and collision clearances.
3. Simulate ascent and descent with realistic centre-of-mass and tyre-contact assumptions.
4. Test one full-scale support module against a rigid fixture using proof loads and mechanical-lock fault cases.
5. Use an instrumented ballast vehicle before an occupied prototype.
6. Validate manual sequencing at very low energy on a controlled test stand and access-controlled site.
7. Add bounded assisted positioning only after the mechanical sequence and abort behavior are demonstrated; keep lidar, computer vision, and autonomous terrain mapping outside the baseline.
8. Obtain a written classification opinion for the frozen configuration before public-road testing.

## Related documents

- [Transforming chassis](transforming-chassis.md)
- [Reference vehicle](reference-vehicle.md)
- [Accessibility](accessibility.md)
- [Suspension](../engineering/suspension.md)
- [Variable track](variable-track.md)
- [Vehicle classification matrix](../regulatory/classification.md)
- [Regulatory research: Germany](../regulatory/germany.md)
- [Regulatory research: European Union](../regulatory/eu.md)
