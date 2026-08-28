# Regulatory research: European Union

[Deutsch](eu_DE.md) · [Classification matrix](classification.md) · [Germany](germany.md) · [Reference vehicle](../concepts/reference-vehicle.md)

**Status:** Primary-source review dated 2026-08-28 — not legal advice; re-verify before relying on it

## Purpose

Map relevant EU vehicle categories, exclusions, type-approval rules, product-safety obligations, and standards before applying national operating rules.

## Questions to answer

- Which configurations fall inside or outside EU type-approval frameworks?
- How are cycles designed for pedal assistance, hand propulsion, multiple wheels, or disability use treated?
- Which machinery, battery, electromagnetic compatibility, radio, and general product-safety obligations may apply?
- Which harmonised or voluntary standards offer useful safety methods even when not mandatory?
- What manufacturer responsibilities arise for a public open design, kit, prototype, or finished vehicle?

## Evidence rules

Prefer EUR-Lex, European Commission material, and official standards catalogues. Record document identifiers, consolidated versions, effective dates, scope, exclusions, and access dates. National implementation and road-use rules belong in country pages such as [Germany](germany.md).

## Open items

- Obtain written classification advice for the frozen three-wheel transforming configuration.
- Create a standards register with applicability and revision dates.
- Review product-liability implications before publishing build-ready designs.

## Current conclusion for the reference vehicle

The intended 250 W pedal-assist configuration is designed to remain outside EU L-category vehicle type approval through Article 2(2)(h) of Regulation (EU) 168/2013. It should use real foot pedals, make the electric system auxiliary to pedalling, limit maximum continuous rated power to 250 W, stop assistance when foot pedalling stops, and progressively reduce and finally stop assistance before 25 km/h.

The three-wheel layout is not itself disqualifying. The exclusion says “pedal cycles” without a two-wheel restriction, and the Regulation separately recognises three- and four-wheel powered cycles in L1e-A. Nevertheless, this unusually heavy, transforming recumbent needs written confirmation rather than relying on an unstated assumption.

## 1. Regulation (EU) 168/2013: vehicle type approval

### Vehicles outside its scope

[Article 2(2)](https://eur-lex.europa.eu/legal-content/EN/ALL/?uri=CELEX:02013R0168-20190220) excludes, among others:

- vehicles with maximum design speed no greater than 6 km/h;
- vehicles exclusively intended for use by physically handicapped persons;
- vehicles primarily intended for off-road use and designed for unpaved surfaces; and
- pedal cycles with pedal assistance using an auxiliary electric motor of no more than **250 W maximum continuous rated power**, whose output stops when the cyclist stops pedalling and otherwise progressively reduces and finally stops before **25 km/h**.

“Excluded from this Regulation” does not mean exempt from national road law or other EU product legislation. Germany decides how an excluded bicycle or mobility aid may be built and operated on German public roads.

### L1e-A powered cycle

Annex I defines L1e-A for cycles designed to pedal where auxiliary propulsion primarily aids pedalling, cuts off at no more than 25 km/h, and has maximum continuous rated/net power no more than **1,000 W**. A powered three- or four-wheel cycle meeting those criteria is technically equivalent to a two-wheel L1e-A vehicle. Unlike the 250 W EPAC exclusion, L1e-A is inside the type-approval framework.

This route could accommodate more power, but it introduces type approval and national motor-vehicle operating consequences. It is not a convenient “strong pedelec” version of the reference bicycle.

### L1e-B and L2e

L1e-B covers other two-wheel L1e vehicles not classed as L1e-A. A three-wheel motor vehicle may instead fall in L2e. Annex I sets L2e’s general envelope at no more than 45 km/h, no more than 4 kW continuous rated/net power, no more than 270 kg mass in running order, and no more than two seats, with passenger and utility subcategories.

A three-wheel machine that exceeds the EPAC exclusion must not automatically be called an “S-pedelec”; wheel count and approved technical category matter. The approval authority determines the route from the completed configuration.

### Mobility-aid exclusion

Article 2(2)(b) excludes vehicles **exclusively intended** for use by physically handicapped persons. That purpose limitation is substantive. The excluded vehicle is then governed by national approval and traffic law; in Germany, the narrow motorized-mobility-chair definition is described in [Germany](germany.md). A broadly marketed adaptive cycle should not claim this exclusion merely because a disabled rider may use it.

## 2. The hand-drive wording issue

The EU Article 2(2)(h) exclusion speaks of **pedal cycles**, assistance to pedalling, and stopping when the cyclist stops pedalling. German StVZO §63a expressly includes hand cranks, but EU wording does not expressly describe a handcycle or a reciprocating rowing-to-crank linkage.

For the reference vehicle:

- foot pedals remain genuine and mechanically useful;
- motor assistance is triggered by foot pedalling;
- the rowing/hand-crank mechanism adds human mechanical torque independently;
- no motor assistance is claimed solely because a hand lever moves; and
- human arm/leg power may continue above 25 km/h after electric output is zero.

This is a conservative design position, not a binding authority interpretation.

## 3. Type approval is not the same as CE/product compliance

Staying outside Regulation 168/2013 removes the L-category whole-vehicle type-approval route; it does not end manufacturer obligations when a product is placed on the EU market or put into service. Applicability depends on who builds it, whether it is supplied commercially, its components, and the date.

### Machinery legislation

Electrically power-assisted cycles have historically been assessed under [Directive 2006/42/EC](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32006L0042). [Regulation (EU) 2023/1230](https://eur-lex.europa.eu/eli/reg/2023/1230/en) replaces it and, after corrigenda, applies from **20 January 2027**. The project must select the regime applicable on the actual placing-on-market/putting-into-service date, rather than combining requirements casually.

Both regimes center on risk assessment, essential health and safety requirements, technical documentation, conformity assessment, instructions, declaration of conformity, and CE marking where applicable. The powered transformation adds machinery hazards—crushing, shearing, unexpected movement, control failure, loss of energy, and safe access—that an ordinary fixed-frame EPAC assessment may not cover adequately.

### General Product Safety Regulation

[Regulation (EU) 2023/988](https://eur-lex.europa.eu/eli/reg/2023/988/oj/eng) applies from 13 December 2024. For consumer products within its relevant scope, manufacturers must ensure safety, carry out an internal risk analysis, create and retain technical documentation, identify the product and responsible economic operator, provide safety information, and manage corrective action. A person who substantially modifies a product may be treated as its manufacturer.

The GPSR complements rather than duplicates specific harmonisation law: applicability must be mapped risk by risk. A one-off private build and a kit or finished vehicle supplied to others do not create the same economic-operator position.

### Electromagnetic compatibility and radio

[Directive 2014/30/EU](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32014L0030) applies to relevant apparatus liable to create or suffer electromagnetic disturbance. It requires EMC assessment, technical documentation, conformity procedure, declaration, and CE marking when applicable. The jack-knife lock sensors, motor controller, battery system, lighting, and wiring must be assessed in all representative configurations.

If Wi-Fi, Bluetooth, cellular, GNSS transmitters, or another intentional radio function is integrated and supplied as part of the product, [Radio Equipment Directive 2014/53/EU](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32014L0053) may replace or supplement parts of the EMC route.

### Batteries

[Regulation (EU) 2023/1542](https://eur-lex.europa.eu/eli/reg/2023/1542/2025-07-31) applies to batteries, including batteries incorporated into products. It includes sustainability, safety, labelling, information, conformity, CE, removability/replaceability, waste, and economic-operator obligations with staged application dates. The final pack category—likely a light-means-of-transport battery if the vehicle is a wheeled device powered by an electric motor—must be confirmed against Article 3 definitions and the actual pack.

Buying CE-marked cells, a battery, motor, or radio does not automatically make the completed vehicle compliant. Integration, wiring, charging, thermal environment, mechanical protection, and combined-system hazards remain the vehicle/product manufacturer’s responsibility where that role applies.

## 4. Standards and the state of the art

Standards are normally voluntary unless law or approval makes them mandatory, but they can provide test methods and evidence of state of the art.

- **EN 15194:2017+A1:2023** — electrically power-assisted cycles (EPAC). Verify the exact current national adoption and scope for a heavy three-wheel recumbent.
- **EN ISO 4210 series** — bicycle safety requirements and tests; applicability to the chosen cycle type and loads must be checked.
- **EN 50604-1** — secondary lithium batteries for light electric vehicle applications; check current edition and pack scope.
- Relevant EMC, radio, ingress, functional-safety, connector, wiring, lighting, and battery transport standards must be selected by the compliance plan.

The European Commission’s [harmonised-standards portal](https://single-market-economy.ec.europa.eu/single-market/goods/european-standards/harmonised-standards_en) explains that only references published in the Official Journal create the relevant presumption of conformity. The current machinery list must be checked on the project’s declaration date.

EN 15194 has a significant limitation. [Commission Implementing Decision (EU) 2023/69](https://eur-lex.europa.eu/eli/dec_impl/2023/69/oj/eng) records that EN 15194:2017 does **not** create a presumption of conformity for specified Machinery Directive requirements involving extreme temperatures, fire, explosion, and vibration. Therefore “tested to EN 15194” is not a complete battery/fire/vibration safety case.

An especially heavy adaptive trike may lie outside load assumptions used for ordinary city/trekking cycles. Component certificates do not replace vehicle-level structural load cases, fatigue tests, braking tests, and stability validation at the declared rider and luggage mass.

## 5. Open-source and one-off builds

Publishing concepts and source files is not identical to placing a finished product on the market. Supplying a kit, selling a finished trike, branding a substantially modified base vehicle, or putting machinery into service can create manufacturer or other economic-operator duties. The repository should therefore distinguish:

- research notes and non-build-ready concepts;
- private experimental prototypes;
- released plans or software;
- component kits;
- commissioned one-off vehicles; and
- series products.

Each release must state configuration, intended use, maturity, limitations, applicable law, and who assumes which compliance role. An open licence is not a safety approval or a waiver of mandatory law.

## 6. EU compliance work package for this project

1. Freeze the complete road configuration and intended use.
2. Obtain a written decision on the 168/2013 Article 2(2)(h) exclusion for the three-wheel transforming design.
3. Create an applicability matrix for Machinery Directive versus Machinery Regulation, GPSR, EMC, RED, Battery Regulation, and national bicycle rules.
4. Purchase and assess the current standards; record edition and scope.
5. Build a single hazard log covering fixed riding modes and transformation.
6. Create technical documentation: drawings, calculations, software configuration, test reports, supplier evidence, risk assessment, instructions, maintenance, and traceability.
7. Complete the legally applicable conformity and declaration steps before any product is placed on the market or put into service.
8. Recheck consolidated EU texts and harmonised-standard lists at the release date.

## Primary-source register

All sources accessed 2026-08-28:

- [Regulation (EU) 168/2013 — consolidated text](https://eur-lex.europa.eu/legal-content/EN/ALL/?uri=CELEX:02013R0168-20190220)
- [Machinery Directive 2006/42/EC](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32006L0042)
- [Machinery Regulation (EU) 2023/1230](https://eur-lex.europa.eu/eli/reg/2023/1230/en)
- [General Product Safety Regulation (EU) 2023/988](https://eur-lex.europa.eu/eli/reg/2023/988/oj/eng)
- [EMC Directive 2014/30/EU](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32014L0030)
- [Radio Equipment Directive 2014/53/EU](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32014L0053)
- [Battery Regulation (EU) 2023/1542 — consolidated 2025-07-31](https://eur-lex.europa.eu/eli/reg/2023/1542/2025-07-31)
- [Commission harmonised-standards portal](https://single-market-economy.ec.europa.eu/single-market/goods/european-standards/harmonised-standards_en)
- [Commission Implementing Decision (EU) 2023/69 — EN 15194 limitation](https://eur-lex.europa.eu/eli/dec_impl/2023/69/oj/eng)
