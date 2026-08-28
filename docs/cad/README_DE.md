# CAD-Arbeitsbereich

[English](README.md) · [Dokumentation](../README_DE.md)

**Status:** Konventionsvorschlag; noch keine Modelle versioniert

Künftige CAD-Dateien sollen in einem obersten Verzeichnis `cad/` liegen; diese Seite dokumentiert sie. Wo praktikabel, werden offene Austauschformate neben nativen Quelldateien bereitgestellt.

## Vorgeschlagene Modellstruktur

- `cad/layout/` — Bauräume, Referenzgeometrie und Packaging-Studien.
- `cad/parts/` — eindeutig identifizierte Quellbauteile.
- `cad/assemblies/` — kontrollierte Baugruppen und Konfigurationen.
- `cad/exports/` — STEP-/STL-/DXF-Ausgaben mit Bezug zur Quellrevision.
- `cad/drawings/` — bemaßte Fertigungs- und Prüfzeichnungen.

## Vor Modellierungsbeginn festzulegen

- Koordinatensystem, Einheiten, Ursprung, Benennung, Teilenummern und Revisionsregeln.
- Parameterverantwortung und Schnittstellen zwischen Fahrgestell, Lenkung, Federung, Antrieb, Sitz und Verkleidung.
- Material- und Massedaten, Kaufteilreferenzen, Toleranzen und sicherheitskritische Merkmale.
- Exportnamen mit Quellrevision; erzeugte Dateien dürfen nicht mit bearbeitbaren Masterdateien verwechselt werden.

Jedes freigegebene Modell soll Konfiguration, Reifegrad, Urheberschaft, Datum, Quellrevision, Lizenz und bekannte Grenzen nennen. Analysen und Testbelege werden auf der passenden Konzept- oder Technikseite verknüpft.

