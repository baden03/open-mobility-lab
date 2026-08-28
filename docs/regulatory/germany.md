# Regulatory research: Germany

[Deutsch](germany_DE.md) · [Classification matrix](classification.md) · [EU context](eu.md) · [Reference vehicle](../concepts/reference-vehicle.md)

**Status:** Primary-source review dated 2026-08-28 — not legal advice; re-verify before relying on it

## Purpose

Determine how each proposed configuration would be classified and what construction, operation, insurance, registration, equipment, and rider rules would follow in Germany.

## Questions to answer

- When does a configuration qualify as a bicycle or electrically assisted cycle?
- How are pedal, hand-crank, and indirect reciprocating human inputs treated?
- Which limits apply to continuous rated motor power, assistance behaviour, and assisted speed?
- Does track width, wheel count, seat configuration, or transformation change classification?
- What rules apply to braking, lighting, dimensions, paths, insurance, licensing, and type approval?
- Could any configuration qualify as a mobility aid, and with what consequences?

## Research method

Record exact configuration assumptions. Cite current primary law and official guidance, including section and access date. Separate statutory text, authority guidance, legal interpretation, and engineering inference. Preserve quotations only when necessary and retain the original German wording beside any translation.

## Configuration matrix to build

| Configuration | Human input | Motor behaviour | Geometry | Candidate class | Confidence |
| --- | --- | --- | --- | --- | --- |
| Baseline | To be defined | To be defined | To be defined | Unassessed | Low |

## Open items

- Obtain written classification advice after configurations and use cases are frozen.
- Confirm how the competent authority treats assisted hand-crank/rowing input under the different wording of StVG and StVZO.
- Confirm every applicable technical rule and standard with an approval engineer before public-road testing.
- Track legal changes and assumptions in the [research log](../research/README.md).

## Current conclusion for the reference vehicle

The most defensible target is a three-wheel bicycle with genuine foot propulsion and a maximum 0.25 kW continuous-rated auxiliary motor. Assistance must progressively reduce and stop by 25 km/h and must stop when foot pedalling stops. The optional rowing mechanism should initially contribute mechanical human power only. This keeps the design within the clearest overlap of §63a StVZO, §1(3) StVG, and the EU EPAC exclusion.

The transforming chassis does not create an exemption. Every drivable ACCESS, URBAN, CRUISE, narrow, or wide state must remain safe and must not introduce a motor mode outside the declared configuration. Human-powered travel above 25 km/h is possible; powered assistance above the cutoff is not.

## 1. Ordinary bicycle and 250 W pedelec

### Definition

[§63a(1) StVZO](https://www.gesetze-im-internet.de/stvzo_2012/__63a.html) defines a bicycle as a vehicle with at least two wheels driven exclusively by the muscle power of people on it using pedals or hand cranks. Therefore a tadpole tricycle can be a bicycle; the section does not impose a two-wheel-only definition.

Under §63a(2), a vehicle of that kind remains a bicycle with electric pedal assistance when:

- maximum continuous rated auxiliary-motor power is no more than **0.25 kW**;
- support progressively decreases as speed rises;
- support stops at **25 km/h** or when the rider stops pedalling or cranking; and
- an optional start/push aid without simultaneous human input accelerates only up to **6 km/h**.

[§1(3) StVG](https://www.gesetze-im-internet.de/stvg/__1.html) provides the corresponding exclusion from “motor vehicle,” but its text says assistance stops when the rider stops **pedalling**. This wording difference matters for a hand-only assisted vehicle. The reference trike retains foot pedals and keys assistance to foot pedalling until the issue is resolved.

### Administrative consequences

A compliant 250 W pedelec is treated as a bicycle rather than a motor vehicle. It therefore does not need motor-vehicle registration, an operating permit/type approval under the motor-vehicle route, a driving licence, or a motor-vehicle insurance plate. That does not mean “unregulated”: §63a(3) allows public-road operation only when the bicycle complies with StVZO, official implementation notices, and the state of the art at manufacture.

### Required bicycle equipment relevant to this project

- [§64 StVZO](https://www.gesetze-im-internet.de/stvzo_2012/__64.html): vehicles must be easy to steer.
- [§64a StVZO](https://www.gesetze-im-internet.de/stvzo_2012/__64a.html): at least one clear-sounding bell.
- [§65 StVZO](https://www.gesetze-im-internet.de/stvzo_2012/__65.html): two independent brakes for bicycles. Regeneration is not one of the two dependable friction/mechanical brake channels.
- [§67 StVZO](https://www.gesetze-im-internet.de/stvzo_2012/__67.html): approved headlamp, rear lamp, front/rear/side/pedal reflectors, mounting ranges, and energy-supply rules. When lights use the traction battery, illumination must remain available as the section requires after assistance shuts down.

This list is an entry point, not a complete verification checklist. The unusual mass, recumbent seating, transformation, independent front brakes, and hand controls require an explicit state-of-the-art safety case even where ordinary bicycle text is terse.

### Where it may be used

[§2(4) StVO](https://www.gesetze-im-internet.de/stvo_2013/__2.html) governs bicycle road and cycle-path use. Signed cycle paths (signs 237, 240, 241) are generally mandatory in the direction of travel; unsigned right-hand cycle paths may be used. Adult bicycle users generally do not use ordinary sidewalks; the narrow child exceptions are in §2(5). A multi-track or unusually wide cycle remains a bicycle, but local infrastructure may make a signed path objectively unusable or unsafe; obtain route-specific advice rather than assuming a blanket width exemption.

There is no general German bicycle helmet mandate for this configuration. A suitable helmet remains a project safety recommendation subject to transfer and seating considerations.

## 2. Motorized mobility chair (motorisierter Krankenfahrstuhl)

This was the first route discussed, but it is not the selected 25 km/h cycle-path concept.

### Definition and licence

[§2 no. 13 FZV](https://www.gesetze-im-internet.de/fzv_2023/BJNR0C70B0023.html) and [§4(1) no. 2 FeV](https://www.gesetze-im-internet.de/fev_2010/__4.html) define the category cumulatively:

- one seat;
- designed for use by physically disabled persons;
- electric drive;
- empty mass no more than **300 kg including batteries, without driver**;
- permissible gross mass no more than **500 kg**;
- maximum design speed no more than **15 km/h**; and
- overall width no more than **110 cm**.

It is exempt from a driving licence under FeV §4. Under [FeV §10(3)](https://www.gesetze-im-internet.de/fev_2010/__10.html), the normal minimum age for licence-exempt motor vehicles is 15; the stated exception covers disabled users of mobility chairs no faster than 10 km/h.

### Approval, registration, insurance, and markings

“Registration-exempt” does not mean “approval-free.” [FZV §3(3)](https://www.gesetze-im-internet.de/fzv_2023/BJNR0C70B0023.html) exempts the category from registration, while **FZV §4(1)** requires an approved type or vehicle individual approval for public-road use.

For vehicles above the FZV/PflVG 6 km/h scope threshold, **FZV §4(3)** requires a valid insurance plate. [PflVG §§1 and 1a](https://www.gesetze-im-internet.de/pflvg/__1a.html) impose motor liability insurance for machine-powered land vehicles with a design speed above 6 km/h; the vehicle exceptions in [§2a PflVG](https://www.gesetze-im-internet.de/pflvg/__2a.html) do not generally exempt mobility chairs. [FZV §52](https://www.gesetze-im-internet.de/fzv_2023/__52.html) explains the insurance plate as proof of cover.

FZV §4(4) also requires the rear slow-moving-vehicle marking under UNECE Regulation No. 69, and §4(5) requires the applicable conformity/data/individual-approval document to be carried if no registration certificate Part I was issued.

The original conversation’s statement that ordinary 15 km/h mobility scooters generally need no motor liability insurance was too broad and is superseded by this review.

### Periodic inspection

The normal insurance-plate mobility chair is not among the vehicles for which [§29(1) StVZO](https://www.gesetze-im-internet.de/stvzo_2012/__29.html) requires periodic Hauptuntersuchung: that section covers registration-required vehicles and the official-plate cases in FZV §4(2) and §4(3) sentence 2, not the insurance-plate case in §4(3) sentence 1. Thus the usual statement “no recurring TÜV/HU” is correct for this route. It must not be confused with **initial approval**: a one-off public-road build still needs an approved type or individual approval under FZV §4(1).

### Where it may be used

[§24(2) StVO](https://www.gesetze-im-internet.de/stvo_2013/__24.html) allows mobility chairs where pedestrian traffic is permitted, but only at walking speed. This is not a general right to operate at 15 km/h on sidewalks. Dedicated bicycle paths are provided for bicycle traffic; a mobility chair does not become a bicycle merely because it is driven there. Route permissions and signs must be checked.

## 3. Faster or more powerful assisted cycles

Once the build leaves the 250 W/25 km/h bicycle envelope, “it still has pedals” is not enough. Relevant EU routes include L1e-A powered cycle and, depending on wheel count and performance, L1e-B or L2e. These require an approval route under Regulation (EU) 168/2013. In Germany, [FeV §6](https://www.gesetze-im-internet.de/fev_2010/__6.html) assigns L1e-B and L2e to licence class AM; [StVO §21a(2)](https://www.gesetze-im-internet.de/stvo_2013/__21a.html) requires a suitable helmet for open three- or multi-wheel motor vehicles with a design speed above 20 km/h unless prescribed seat belts are used.

Motor vehicles do not receive ordinary bicycle-path access merely because they resemble cycles. Full operational consequences—licence, minimum age, insurance, plate, helmet/restraint, and permitted infrastructure—must be mapped to the approved class.

## 4. Elektrokleinstfahrzeug is not a fallback

[§1 eKFV](https://www.gesetze-im-internet.de/ekfv/__1.html) requires, among other things, a vehicle without a seat unless self-balancing, a qualifying handle/steering bar, >6–20 km/h design speed, no more than 500 W, no more than 700 mm width, 2,000 mm length, and 55 kg without driver. The transforming seated trike does not fit. [§10 eKFV](https://www.gesetze-im-internet.de/ekfv/__10.html) provides its own traffic-area rules and cannot be borrowed by another class.

## 5. Design-specific legal risks

### Jack-knife transformation

No cited rule grants a special transforming-cycle category. The safe inference is that every configuration available for driving is part of the vehicle presented for classification and safety review. Transformation must not temporarily permit autonomous propulsion outside the EPAC rule. Structural locks, brake interlock, and safe steering in every drivable state are engineering evidence for §63a(3)’s state-of-the-art obligation.

### Rowing-to-crank drive

§63a expressly accepts hand cranks for a bicycle. A reciprocating lever that drives a rotating jackshaft through one-way clutches is not expressly interpreted in the statute. Document the rotary hand-crank endpoint and genuine mechanical power path, but do not claim legal certainty. Retaining conventional foot pedals and using them as the sole assistance trigger is the conservative route.

### Variable track

The 110 cm figure belongs to the motorized-mobility-chair definition, not the ordinary bicycle definition. Nevertheless, a deployable wider state is part of the actual design, affects infrastructure fit, and cannot safely be treated as invisible during approval. Prefer a fixed road track or storage-only folding arrangement until written advice supports multiple drivable widths.

### Power, motors, and overrides

The 0.25 kW rule is maximum continuous rated power for the auxiliary electric drive, not “250 W per wheel.” Multiple traction motors must be assessed as one auxiliary-drive system. Three 300–500 W hub motors are outside the reference EPAC basis. A user-selectable override that restores assistance above 25 km/h contradicts that basis. Private-site prototypes must use separately controlled configurations that cannot accidentally enter public-road use.

## 6. Approval and evidence plan

1. Freeze one road configuration and issue a configuration manifest.
2. Obtain an early written classification opinion from a German technical service/approval expert.
3. Create a requirements matrix from StVZO §§63a–67 plus applicable notices and standards.
4. Document motor rated-power evidence, cutoff curves, start-aid behaviour, and tamper resistance.
5. Document steering, independent braking, lighting, structural locks, stability, and all failure modes.
6. Keep prototypes on genuinely access-controlled private test areas until the public-road gate is signed off.
7. Re-check every linked consolidated statute immediately before approval or road use.

## Primary-source register

All sources accessed 2026-08-28:

- [StVG §1](https://www.gesetze-im-internet.de/stvg/__1.html)
- [StVZO §63a](https://www.gesetze-im-internet.de/stvzo_2012/__63a.html), [§64](https://www.gesetze-im-internet.de/stvzo_2012/__64.html), [§64a](https://www.gesetze-im-internet.de/stvzo_2012/__64a.html), [§65](https://www.gesetze-im-internet.de/stvzo_2012/__65.html), [§67](https://www.gesetze-im-internet.de/stvzo_2012/__67.html), [§29](https://www.gesetze-im-internet.de/stvzo_2012/__29.html)
- [StVO §2](https://www.gesetze-im-internet.de/stvo_2013/__2.html), [§21a](https://www.gesetze-im-internet.de/stvo_2013/__21a.html), [§24](https://www.gesetze-im-internet.de/stvo_2013/__24.html)
- [FZV consolidated text, especially §§2–4 and 52–53](https://www.gesetze-im-internet.de/fzv_2023/BJNR0C70B0023.html)
- [FeV §4](https://www.gesetze-im-internet.de/fev_2010/__4.html), [§6](https://www.gesetze-im-internet.de/fev_2010/__6.html), [§10](https://www.gesetze-im-internet.de/fev_2010/__10.html)
- [PflVG §1](https://www.gesetze-im-internet.de/pflvg/__1.html), [§1a](https://www.gesetze-im-internet.de/pflvg/__1a.html), [§2a](https://www.gesetze-im-internet.de/pflvg/__2a.html)
- [eKFV §1](https://www.gesetze-im-internet.de/ekfv/__1.html), [§10](https://www.gesetze-im-internet.de/ekfv/__10.html)
