# Electronics

[Deutsch](electronics_DE.md) · [Engineering](README.md)

**Status:** Architecture outline

## Scope

Traction power, low-voltage power, sensors, actuators, lighting, controls, communications, charging, protection, wiring, enclosures, and diagnostics.

## Architecture principles

- Separate safety-critical functions from convenience features.
- Define voltage domains, grounding, isolation, fusing, connectors, and service boundaries.
- Prefer deterministic safe behaviour after broken wires, shorts, water ingress, sensor disagreement, or communication loss.
- Make manual braking and a safe stop independent of nonessential software where feasible.
- Design for electromagnetic compatibility, environmental exposure, repair, and traceability.

## Planned artifacts

Block diagram, power budget, wiring specification, interface control documents, fault tree/FMEA, component derating, environmental requirements, and verification plan. Coordinate with [energy system](../concepts/energy-system.md) and [firmware](firmware.md).

