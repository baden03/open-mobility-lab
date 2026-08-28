# Firmware

[Deutsch](firmware_DE.md) · [Engineering](README.md)

**Status:** Architecture outline

## Scope

Assistance control, sensor validation, transformation interlocks, user interface, diagnostics, logging, communications, updates, and fault handling.

## Principles

- Requirements and hazards precede implementation.
- State machines and transitions must be explicit, including startup, degraded operation, stopping, charging, and service.
- Commands require plausibility checks; faults should be latched or recoverable according to documented safety reasoning.
- Logs should support diagnosis while collecting the least personal data needed.
- Updates must be authenticated, recoverable, versioned, and compatible with the actual hardware configuration.

## Planned artifacts

Control-state diagrams, timing and interface requirements, hazard mitigations, test vectors, hardware-in-the-loop plan, release process, and configuration manifest. See [electronics](electronics.md) and [transforming chassis](../concepts/transforming-chassis.md).

