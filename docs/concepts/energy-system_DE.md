# Energiesystem

[English](energy-system.md) · [Konzepte](README_DE.md)

**Status:** Anforderungsermittlung

## Umfang

Das Energiesystem umfasst menschliche Leistung, Traktionsbatterie, Motor- und Reglerverluste, Nebenverbraucher, Laden, thermisches Verhalten und die Energieanzeige für die fahrende Person.

## Fragen

- Welche Annahmen zu Weg, Steigung, Zuladung, Wetter, Unterstützung und Reserve bestimmen die sinnvolle Kapazität?
- Sollen Batterien entnehmbar, modular oder fest sein, und wer kann sie sicher handhaben?
- Wie werden Zellensicherheit, Gehäuse, Eindringen, Crashlasten, Isolation, Sicherungen und Wartungstrennung behandelt?
- Welche Ladeorte, Steckerstandards, Lagerzustände und Kältegrenzen sind relevant?
- Kann Eigenleistung sinnvoll angezeigt werden, ohne unsichere Anstrengung zu fördern?

## Geplante Ergebnisse

Fahrzyklusmodell, Energiebilanz, thermisches Modell, Ladekonzept, Batterierisikoanalyse und Strategie für Wartung und Lebensende. Elektrische Umsetzung mit [Elektronik](../engineering/electronics_DE.md), Steuerverhalten mit [Firmware](../engineering/firmware_DE.md) und Grenzwerte mit [EU-Forschung](../regulatory/eu_DE.md) verknüpfen.

Der [Open-Source-Mittelmotor von Pedro Neves](open-source-mid-drive-pedro-neves_DE.md) wird als prüfbare Antriebsreferenz verfolgt. Editierbares CAD und reparaturorientierte Architektur sind relevant; Drehmoment, Thermik, strukturelle Lastpfade, Lizenzierung, Unterstützungssteuerung sowie Nachweise für 250 W und 25 km/h müssen jedoch geklärt sein, bevor das System als Bauteilkandidat gelten kann.
