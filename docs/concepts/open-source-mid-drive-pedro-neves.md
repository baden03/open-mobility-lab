# Open-source drivetrain precedent: Pedro Neves mid-drive

[Deutsch](open-source-mid-drive-pedro-neves_DE.md) · [Concepts](README.md) · [Energy system](energy-system.md) · [Reference vehicle](reference-vehicle.md)

**Status:** Tracked early prototype and design precedent; not a selected component

**Reviewed:** 2026-08-29

**Canonical project home:** [Pedro Neves / Powercircuits — Open Source Electric Mid-Drive](https://www.powercircuits.nl/home/open-source-electric-mid-drive)

This page tracks an early open-source mid-drive project built around repairability, editable CAD, accessible fabrication, and a reported 25 km/h design goal, together with its lineage in an open-source tilting tadpole cargo trike. The Powercircuits project and downloads are the primary sources; the user-submitted [Hackaday article](https://hackaday.com/2026/07/18/open-source-mid-drive-e-bike-motor-has-lots-of-promise-and-hyphens/) is retained as secondary discovery coverage.

Related project documentation: [dual human propulsion](dual-human-propulsion.md) · [tadpole layout](tadpole-layout.md) · [electronics](../engineering/electronics.md) · [classification](../regulatory/classification.md) · [Germany](../regulatory/germany.md) · [EU](../regulatory/eu.md)

## Why track this project

The Adaptive Cycle needs a drivetrain that is understandable, repairable, configurable, and compatible with genuine human propulsion. Most commercial mid-drives are highly integrated systems whose mechanical parts, firmware, sensors, diagnostics, batteries, and spares may be difficult for an independent builder to modify or maintain.

Pedro Neves’s project is relevant because it starts from the opposite premise: publish editable mechanical files and a bill of materials, use accessible fabrication methods where practical, retain a pedal-home path, and let other builders inspect and improve the design.

It is also relevant because Neves has developed an [open-source tadpole tilting cargo trike](https://www.powercircuits.nl/home/open-source-tadpole-tilting-cargo-trike). That adjacent work makes the mid-drive more interesting to this project than an isolated hobby motor: the designer has direct experience packaging components into a leaning three-wheel cargo-cycle architecture.

## Primary projects

### Open Source Electric Mid-Drive

Canonical project and download page: [Powercircuits — Open Source Electric Mid-Drive](https://www.powercircuits.nl/home/open-source-electric-mid-drive)

This Powercircuits page—not the Hackaday article—is the source of truth for the current public project. It hosts or links the editable CAD, bill of materials, and build-video series. Revision checks should always begin there because secondary articles may describe an older build.

As reviewed on 2026-08-29, the project page describes the work as the beginning of a journey and publishes:

- an editable `Drive_Unit_R3.step` assembly, identified as CAD revision 3 from August 2026;
- a revision 2 bill of materials; and
- a linked build-video playlist.

User-supplied primary video source:

- [Open Source Electric Mid-Drive build playlist](https://www.youtube.com/watch?v=ENQmXIPajfI&list=PLKUZZkTf8y0U) — playlist ID `PLKUZZkTf8y0U`, entry video `ENQmXIPajfI`

Identified videos supplied by the user:

1. [#1 Open Source eBike Mid-Drive — Project Start with Revopoint MetroX 3D Scanner](https://www.youtube.com/watch?v=irtROmmcAvQ) — video ID `irtROmmcAvQ`
2. [DIY eBike Mid-Drive](https://www.youtube.com/watch?v=0jco-RKzRSo) — video ID `0jco-RKzRSo`
3. [3D Printed eBike Mid-Drive with Helical Gears](https://www.youtube.com/watch?v=ENQmXIPajfI) — video ID `ENQmXIPajfI`

The numbered ordering above reflects the apparent project narrative implied by the supplied titles, not independently verified publication chronology. The Revopoint MetroX scanner belongs to Pedro’s component-development and reverse-engineering workflow; it does not imply that the finished mid-drive—or the Adaptive Cycle—needs a 3D scanner in operation.

The playlist should be reviewed alongside the CAD and BOM because it may document design intent, assembly order, tests, failures, and revision changes that are not captured on the compact project page. Video demonstrations remain evidence of the shown configuration only; they do not replace drawings, measurements, or test records.

The [Hackaday discovery article](https://hackaday.com/2026/07/18/open-source-mid-drive-e-bike-motor-has-lots-of-promise-and-hyphens/) reports that the prototype uses a motor recovered from a battery angle grinder, extensive 3D-printed parts with metal bearing surfaces, a clutch bearing intended to allow unassisted pedalling if the motor fails, and a later CNC replacement for an initially printed axle. It also reports a 25 km/h goal.

Those details should be confirmed against the current CAD, BOM, and build videos before engineering reliance. The primary project page does not yet publish a validated performance specification, rated-power determination, durability report, controller logic, thermal data, or compliance evidence.

### Open Source Tadpole Tilting Cargo Trike

Primary page: [Powercircuits — Open Source Tadpole Tilting Cargo Trike](https://www.powercircuits.nl/home/open-source-tadpole-tilting-cargo-trike)

The page describes a fully built open-source design that is rideable but still needs improvements. As reviewed on 2026-08-29, it provides a build-video playlist, editable CAD identified as revision 8 from July 2026, and a parts list for specialized components.

User-supplied primary video source:

- [Open Source Tadpole Tilting Cargo Trike build playlist](https://www.youtube.com/watch?v=UWFQ6nFzpgE&list=PL3uwHLwN7YKrodkpyXISvayLdFsccHNWB) — playlist ID `PL3uwHLwN7YKrodkpyXISvayLdFsccHNWB`, entry video `UWFQ6nFzpgE`

This trike is a design precedent rather than a component certification. Its relevance includes:

- leaning tadpole steering and suspension geometry;
- packaging around two front wheels and one rear wheel;
- builder-accessible CAD and fabrication decisions;
- practical iteration across multiple revisions; and
- a plausible integration environment for an open mid-drive.

## Preliminary mid-drive architecture reported

The following is a research summary, not a frozen specification:

```text
reused electric motor
        ↓
speed reduction / printed and metal mechanical parts
        ↓
one-way clutch or freewheel function
        ↓
bottom-bracket / crank drivetrain
        ↓
normal bicycle transmission and driven wheel
```

The architectural value of a mid-drive is that motor torque enters the bicycle drivetrain before the final gearing. The vehicle may use its normal gear ratios for climbing and efficient cruising, and the drive can remain centralized rather than adding unsprung hub-motor mass to an articulated or suspended wheel.

For the Adaptive Cycle, a common intermediate shaft could potentially accept:

- foot-pedal torque;
- optional rowing/hand-drive torque;
- compliant electric assistance; and
- selectable reduction into the final wheel drivetrain.

That possibility is conceptual. The published Neves drive should not be assumed to support multiple human inputs, the project’s payload, or the proposed transforming chassis without redesign.

## Potential benefits for this project

- **Repairability:** editable geometry and identifiable parts may allow local repair instead of replacement of a sealed proprietary unit.
- **Design ownership:** gear ratios, interfaces, bearings, clutch behavior, housings, and mounting points can be inspected and changed.
- **Packaging:** a custom central drive may fit the reference vehicle’s chassis and common shaft better than a bicycle-frame-specific commercial unit.
- **Human-power continuity:** a correctly designed clutch/freewheel path can permit pedalling after electrical failure.
- **Iteration:** open CAD makes it possible to analyze loads, substitute materials, and adapt interfaces rather than reverse-engineer a closed housing.
- **Shared ecosystem:** Neves’s tilting tadpole work may provide useful lessons about drive packaging, steering, suspension, and cargo-scale loading.

## Important cautions

### Prototype maturity

The primary page explicitly presents the mid-drive as early work. A published STEP file and BOM establish inspectability, not performance, safety, or road legality. Before considering adoption, the project needs evidence for:

- continuous and peak torque at the crank or output shaft;
- motor speed, full reduction ratio, cadence range, and efficiency map;
- thermal behavior at sustained climbing load;
- gear, shaft, bearing, clutch, housing, and mounting loads;
- backlash, noise, lubrication, sealing, contamination, and service intervals;
- fatigue and impact performance;
- behavior when the motor, controller, clutch, sensor, or reduction stage jams;
- safe isolation and continued pedalling after electrical failure; and
- reproducible manufacture of every safety-critical part.

### Reused angle-grinder motor

A motor designed for a handheld tool may operate at much higher speed and different duty cycle than an e-bike mid-drive. The necessary reduction, cooling, bearings, noise, brushes or commutation, controller behavior, and continuous output need measurement. Reuse is attractive for experimentation but may not be the best final motor architecture.

### Printed structural parts

3D printing is valuable for housings, guards, ducts, fit checks, sacrificial prototypes, and lightly loaded geometry. Parts in the crank, axle, bearing-retention, torque-reaction, or vehicle-mount load paths need explicit material, orientation, temperature, creep, fatigue, and failure analysis. A later CNC axle is a useful design evolution, but every remaining load path must be reviewed rather than assuming that metal bearing surfaces make the complete assembly structural.

### Published licensing

“Open source” should not be inferred solely from free downloads or public CAD. Before copying, modifying, or redistributing files, record the explicit hardware, CAD, documentation, and software licences and confirm that the terms permit this public project’s intended use. The reviewed project pages did not expose licensing details in their visible text.

## The 25 km/h statement

Hackaday reports 25 km/h as the project’s goal. That number alone does not demonstrate German or EU pedelec compliance and does not establish that the prototype reaches the speed under a representative load.

For the reference vehicle, the relevant regulatory design basis includes at least:

- genuine muscle propulsion through qualifying pedals or hand cranks;
- maximum continuous rated auxiliary-motor power no greater than 0.25 kW for the intended ordinary pedelec route;
- assistance that reduces progressively and ends by 25 km/h;
- assistance that stops when the qualifying human input stops under the applicable interpretation;
- a compliant start/push aid if present;
- no hidden throttle, service mode, or alternate configuration that changes the public-road functional envelope; and
- evidence for steering, braking, lighting, structural safety, and the state of the art.

See the project’s [classification matrix](../regulatory/classification.md), [German regulatory research](../regulatory/germany.md), and [EU research](../regulatory/eu.md). A configurable open controller is useful for development, but configuration freedom also increases the need for a frozen road profile, tamper controls, and traceable rated-power/cutoff evidence.

## Evaluation plan

1. Download and archive the current STEP file and BOM with their revision dates and licence information.
2. Inspect the complete power path and identify every torque-bearing, bearing-retention, and vehicle-mount component.
3. Derive motor speed, reduction stages, crank cadence, output torque, and theoretical vehicle speed for representative wheel and gearing choices.
4. Determine whether the reported motor/controller combination can provide a defensible 250 W maximum continuous rated configuration.
5. Model thermal behavior and sustained climbing duty for the reference vehicle’s higher mass.
6. Review freewheel/clutch failure modes, pedal-home drag, and jam containment.
7. Compare the architecture with repairable commercial or VESC-compatible mid-drive alternatives.
8. Review the tilting cargo-trike CAD for packaging and suspension precedents separately from the motor evaluation.
9. Contact Pedro Neves only after assembling focused technical questions that are not answered by the published files.
10. Keep any first build on a bench or access-controlled private test vehicle until structural and control evidence exists.

## Questions to track

- What motor model, winding, nominal voltage, current limit, controller, and commutation method are used in revision 3?
- What are the total reduction ratio, intended crank cadence, measured wheel speed, and test payload?
- Has 25 km/h been demonstrated, calculated, or only selected as a target?
- What continuous output and temperature rise have been measured?
- Which parts are printed in the current revision, with what materials and print specifications?
- Which axle, clutch, gear, bearing, and mount changes occurred between revisions?
- Can the unit accept a torque/cadence sensor and produce a compliant progressive-assistance cutoff?
- What drag remains when the drive is unpowered or failed?
- How is a jammed motor or reduction stage isolated from the pedals?
- What explicit licences govern CAD, BOM, documentation, video material, firmware, and derivative designs?
- Does the trike integration preserve lean, suspension, steering, and ground clearance throughout its range?
- What lessons transfer to the heavy adaptive vehicle, and which are specific to a cargo-cycle prototype?

## Current assessment

**Track and inspect; do not select yet.** The strongest present value is openness and design inspectability, plus the connection to a real tilting tadpole cargo-trike program. The weakest area is evidence maturity: published artifacts show an active prototype project, not a validated 250 W/25 km/h road-ready drive.

This component may ultimately be most useful as:

- a learning reference for an open common-shaft drive;
- a source of adaptable CAD interfaces;
- a collaboration opportunity;
- an early prototype drive after independent load review; or
- a prompt to specify a more mature open motor/controller architecture while retaining the same repairability goals.

## Sources

Canonical project source reviewed 2026-08-29:

- [Pedro Neves / Powercircuits — Open Source Electric Mid-Drive](https://www.powercircuits.nl/home/open-source-electric-mid-drive)
- [Pedro Neves — Open Source Electric Mid-Drive build playlist](https://www.youtube.com/watch?v=ENQmXIPajfI&list=PLKUZZkTf8y0U) (user-supplied; automated page retrieval unavailable)
- [#1 Open Source eBike Mid-Drive — Project Start with Revopoint MetroX 3D Scanner](https://www.youtube.com/watch?v=irtROmmcAvQ) (title and link supplied by user)
- [DIY eBike Mid-Drive](https://www.youtube.com/watch?v=0jco-RKzRSo) (title and link supplied by user)
- [3D Printed eBike Mid-Drive with Helical Gears](https://www.youtube.com/watch?v=ENQmXIPajfI) (title and link supplied by user)

Related primary project:

- [Pedro Neves / Powercircuits — Open Source Tadpole Tilting Cargo Trike](https://www.powercircuits.nl/home/open-source-tadpole-tilting-cargo-trike)
- [Pedro Neves — Open Source Tadpole Tilting Cargo Trike build playlist](https://www.youtube.com/watch?v=UWFQ6nFzpgE&list=PL3uwHLwN7YKrodkpyXISvayLdFsccHNWB) (user-supplied; automated page retrieval unavailable)

Discovery and secondary reporting:

- [Hackaday — Open-Source Mid-Drive E-Bike Motor Has Lots Of Promise, And Hyphens](https://hackaday.com/2026/07/18/open-source-mid-drive-e-bike-motor-has-lots-of-promise-and-hyphens/)
