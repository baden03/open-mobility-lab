# Energy system

[Deutsch](energy-system_DE.md) · [Concepts](README.md)

**Status:** Requirements discovery

## Scope

The energy system includes rider power, traction battery, motor and controller losses, auxiliary loads, charging, thermal behaviour, and energy information presented to the rider.

## Questions

- What journey, gradient, payload, weather, assistance, and reserve assumptions define useful capacity?
- Should batteries be removable, modular, or fixed, and who can safely handle them?
- How are cell safety, containment, ingress, crash loads, isolation, fusing, and service disconnects addressed?
- What charging locations, connector standards, storage states, and cold-weather limits matter?
- Can rider effort be shown meaningfully without encouraging unsafe exertion?

## Planned outputs

Duty-cycle model, energy budget, thermal model, charging concept, battery risk analysis, and end-of-life/service strategy. Link electrical implementation to [electronics](../engineering/electronics.md), control behaviour to [firmware](../engineering/firmware.md), and limits to [EU research](../regulatory/eu.md).

The [Pedro Neves open-source mid-drive](open-source-mid-drive-pedro-neves.md) is tracked as an inspectable drivetrain precedent. Its editable CAD and repair-oriented architecture are relevant, but its torque, thermal performance, structural load paths, licensing, assistance controls, and 250 W/25 km/h evidence must be established before it can become a candidate component.
