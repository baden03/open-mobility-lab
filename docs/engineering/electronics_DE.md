# Elektronik

[English](electronics.md) · [Technik](README_DE.md)

**Status:** Architekturskizze

## Umfang

Traktions- und Niederspannungsversorgung, Sensoren, Aktuatoren, Beleuchtung, Bedienelemente, Kommunikation, Laden, Schutz, Verkabelung, Gehäuse und Diagnose.

## Architekturgrundsätze

- Sicherheitskritische Funktionen von Komfortfunktionen trennen.
- Spannungsbereiche, Masseführung, Isolation, Absicherung, Steckverbinder und Wartungsgrenzen definieren.
- Bei Leitungsbruch, Kurzschluss, Wassereintritt, widersprüchlichen Sensoren oder Kommunikationsverlust ein bestimmbares sicheres Verhalten anstreben.
- Mechanisches Bremsen und sicheres Anhalten soweit möglich von nicht notwendiger Software unabhängig machen.
- Elektromagnetische Verträglichkeit, Umwelteinflüsse, Reparatur und Rückverfolgbarkeit berücksichtigen.

## Geplante Artefakte

Blockdiagramm, Leistungsbilanz, Verkabelungsspezifikation, Schnittstellendokumente, Fehlerbaum/FMEA, Bauteil-Derating, Umweltanforderungen und Verifikationsplan. Mit [Energiesystem](../concepts/energy-system_DE.md) und [Firmware](firmware_DE.md) abstimmen.

