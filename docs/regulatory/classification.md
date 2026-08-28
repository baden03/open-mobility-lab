# Vehicle classification matrix

[Deutsch](classification_DE.md) · [Germany](germany.md) · [European Union](eu.md) · [Reference vehicle](../concepts/reference-vehicle.md)

**Status:** Working legal map, reviewed 2026-08-28 — not legal advice  
**Method:** Current consolidated primary legislation is linked below. Operational consequences still require confirmation for the frozen build configuration.

## Why classification comes first

Wheel count, genuine human drive, motor rated power, assistance logic, design speed, intended user, seat, dimensions, mass, and every available operating mode can change the category. A software switch, folded “inspection” position, or removable battery does not safely make an out-of-envelope configuration disappear.

## Relevant routes

| Candidate | Defining envelope | Approval path | German road consequence | Fit for reference concept |
| --- | --- | --- | --- | --- |
| **Unassisted bicycle** | At least two wheels; muscle power through pedals or hand cranks under §63a(1) StVZO | No vehicle type approval; must satisfy StVZO/state of art | Bicycle rules | Technically possible, but misses assistance goal |
| **250 W pedelec / EPAC** | Genuine muscle propulsion; auxiliary motor ≤0.25 kW continuous rated; assistance progressively reduces and ends by 25 km/h and when qualifying input stops | Excluded from EU L-category type approval; treated as bicycle in Germany | No driving licence, registration, or motor insurance plate; bicycle construction and road rules | **Target route** |
| **L1e-A powered cycle** | Designed to pedal; auxiliary propulsion primarily aids pedalling; cutoff ≤25 km/h; ≤1 kW; 3/4-wheel equivalents possible | EU L-category type approval | Not an ordinary bicycle; approval and national operating rules apply | Poor fit: complexity without required benefit |
| **L1e-B / L2e** | Two-wheel moped route (L1e-B) or three-wheel moped route (L2e), generally ≤45 km/h and ≤4 kW for L2e | EU L-category type approval | Licence/insurance/helmet/access rules may apply; ordinary cycle-path use is not the baseline | Alternative faster motor vehicle, not the reference |
| **Motorized mobility chair** | Single seat; designed for physically disabled users; electric; ≤300 kg empty incl. battery; ≤500 kg gross; ≤15 km/h; ≤110 cm wide | Registration-exempt but approved type or individual approval required | Licence-exempt; normally insurance plate above 6 km/h; pedestrian areas only at walking speed; slow-vehicle plate and documents required | Separate Mobility Rover concept, not the 25 km/h cycle-path solution |
| **eKFV small electric vehicle** | >6–20 km/h; no seat unless self-balancing; handlebar; ≤500 W; ≤700 mm wide; ≤2,000 mm long; ≤55 kg | German eKFV approval route | Defined cycle-infrastructure rules and insurance | Does not fit seated transforming trike |
| **Closed-site prototype** | Not operated in public traffic; access-controlled test area | Road approval may not be needed for the test itself | Product, liability, occupational, and site rules can still apply | Correct early prototype environment |

## Reference-vehicle decision

The conservative reference build uses foot pedals as genuine human propulsion and as the trigger for motor assistance. It keeps the motor at or below 0.25 kW maximum continuous rated power and ends assistance when foot pedalling stops and progressively by 25 km/h. Three wheels do not conflict with Germany’s “at least two wheels” bicycle definition. Regulation (EU) 168/2013 excludes compliant pedal-assist cycles from its type-approval scope without stating a two-wheel limit in the exclusion.

The hand system adds mechanical human power only. This avoids relying on a rowing linkage to resolve the difference between §63a StVZO (“pedals or hand cranks”), §1(3) StVG (stops when pedalling stops), and the EU exclusion (“cyclist stops pedalling”). Written advice is required before allowing hand motion alone to trigger electric assistance.

## Configuration-control questions

Before classification review, freeze and document:

- every drivable chassis/track configuration and its dimensions;
- motor count, maximum continuous rated power, peak control limits, and measurement method;
- the exact torque/cadence logic and cutoff curve;
- throttle, start/push aid, cruise, reverse, service, and recovery modes;
- mechanical power paths from feet and hands to the wheel;
- maximum design speed under motor power;
- battery modules included during use;
- seat, restraints, bodywork, cargo, and intended user statement; and
- firmware identity, tamper controls, and failure behaviour.

## Primary sources

- [Germany: StVZO §63a — bicycle definition and 250 W assistance](https://www.gesetze-im-internet.de/stvzo_2012/__63a.html)
- [Germany: StVG §1(3) — pedelec is not a motor vehicle](https://www.gesetze-im-internet.de/stvg/__1.html)
- [Germany: FZV §§2–4 — categories, approval and registration exemptions](https://www.gesetze-im-internet.de/fzv_2023/BJNR0C70B0023.html)
- [Germany: FeV §4 — licence exemptions](https://www.gesetze-im-internet.de/fev_2010/__4.html)
- [Germany: eKFV §1 — small electric vehicle limits](https://www.gesetze-im-internet.de/ekfv/__1.html)
- [EU: Regulation 168/2013, Article 2 and Annex I](https://eur-lex.europa.eu/legal-content/EN/ALL/?uri=CELEX:02013R0168-20190220)

