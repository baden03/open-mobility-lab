# CAD workspace

[Deutsch](README_DE.md) · [Documentation](../README.md)

**Status:** Convention proposal; no models committed

Future CAD files should live in a top-level `cad/` directory, while this page documents them. Use open exchange formats alongside native sources where practical.

## Proposed model structure

- `cad/layout/` — envelopes, reference geometry, and packaging studies.
- `cad/parts/` — uniquely identified source parts.
- `cad/assemblies/` — controlled assemblies and configurations.
- `cad/exports/` — STEP/STL/DXF outputs tied to a source revision.
- `cad/drawings/` — dimensioned manufacturing and inspection drawings.

## Rules to establish before modelling

- Coordinate system, units, origin, naming, part numbering, and revision policy.
- Parameter ownership and interfaces between chassis, steering, suspension, propulsion, seat, and bodywork.
- Material and mass metadata, purchased-part references, tolerances, and safety-critical characteristics.
- Export naming that records source revision; generated files must never be mistaken for editable masters.

Every released model should identify configuration, maturity, author, date, source revision, license, and known limitations. Link analyses and test evidence from the relevant concept or engineering page.

