# Firmware

[English](firmware.md) · [Technik](README_DE.md)

**Status:** Architekturskizze

## Umfang

Unterstützungsregelung, Sensorprüfung, Transformationsverriegelungen, Bedienoberfläche, Diagnose, Protokollierung, Kommunikation, Aktualisierungen und Fehlerbehandlung.

## Grundsätze

- Anforderungen und Gefahren werden vor der Implementierung beschrieben.
- Zustände und Übergänge müssen ausdrücklich definiert sein, einschließlich Start, eingeschränktem Betrieb, Anhalten, Laden und Wartung.
- Befehle benötigen Plausibilitätsprüfungen; Fehler werden entsprechend dokumentierter Sicherheitsüberlegungen gespeichert oder rücksetzbar behandelt.
- Protokolle sollen Diagnose ermöglichen und nur die nötigen personenbezogenen Daten erfassen.
- Aktualisierungen müssen authentifiziert, wiederherstellbar, versioniert und mit der tatsächlichen Hardwarekonfiguration kompatibel sein.

## Geplante Artefakte

Zustandsdiagramme, Zeit- und Schnittstellenanforderungen, Gefahrenminderungen, Testvektoren, Hardware-in-the-Loop-Plan, Freigabeprozess und Konfigurationsmanifest. Siehe [Elektronik](electronics_DE.md) und [transformierbares Fahrgestell](../concepts/transforming-chassis_DE.md).

