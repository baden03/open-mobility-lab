# Open-Source-Antriebsreferenz: Pedro-Neves-Mittelmotor

[English](open-source-mid-drive-pedro-neves.md) · [Konzepte](README_DE.md) · [Energiesystem](energy-system_DE.md) · [Referenzfahrzeug](reference-vehicle_DE.md)

**Status:** Verfolgter früher Prototyp und Konstruktionspräzedenzfall; kein ausgewähltes Bauteil

**Geprüft:** 2026-08-29

**Zentrale Projektseite:** [Pedro Neves / Powercircuits — Open Source Electric Mid-Drive](https://www.powercircuits.nl/home/open-source-electric-mid-drive)

Diese Seite verfolgt einen frühen Open-Source-Mittelmotor mit Schwerpunkt auf Reparierbarkeit, editierbarem CAD, zugänglicher Fertigung und einem berichteten Entwicklungsziel von 25 km/h. Ein verwandtes offenes Neige-Lastendreirad desselben Entwicklers liefert zusätzlich einen Architekturpräzedenzfall. Powercircuits und die dort bereitgestellten Downloads sind die Primärquellen; der vom Nutzer eingebrachte [Hackaday-Artikel](https://hackaday.com/2026/07/18/open-source-mid-drive-e-bike-motor-has-lots-of-promise-and-hyphens/) bleibt als sekundärer Fundhinweis erhalten.

Verwandte Projektdokumentation: [doppelter Muskelkraftantrieb](dual-human-propulsion_DE.md) · [Tadpole-Anordnung](tadpole-layout_DE.md) · [Elektronik](../engineering/electronics_DE.md) · [Einstufung](../regulatory/classification_DE.md) · [Deutschland](../regulatory/germany_DE.md) · [EU](../regulatory/eu_DE.md)

## Warum das Projekt verfolgt wird

Der Adaptive Cycle benötigt einen Antrieb, der verständlich, reparierbar, konfigurierbar und mit echtem Muskelkraftantrieb vereinbar ist. Viele kommerzielle Mittelmotoren verbinden Mechanik, Firmware, Sensorik, Diagnose, Akku und Ersatzteilversorgung in einem schwer veränderbaren proprietären System.

Pedro Neves verfolgt den entgegengesetzten Ansatz: editierbare mechanische Dateien und Stückliste veröffentlichen, soweit sinnvoll zugängliche Fertigungsverfahren nutzen, einen rein mechanischen Heimfahrpfad erhalten und anderen den Entwurf zur Prüfung und Weiterentwicklung öffnen.

Sein [Open-Source-Tadpole-Neige-Lastendreirad](https://www.powercircuits.nl/home/open-source-tadpole-tilting-cargo-trike) macht den Motor für dieses Projekt besonders interessant. Der Entwickler besitzt praktische Erfahrung mit Einbau, Lenkung und Fahrwerk in einem neigenden dreirädrigen Lastenrad. Das ersetzt jedoch keine Validierung für unser erheblich schwereres adaptives Fahrzeug.

## Primärprojekte

### Open Source Electric Mid-Drive

Zentrale Projekt- und Downloadseite: [Powercircuits — Open Source Electric Mid-Drive](https://www.powercircuits.nl/home/open-source-electric-mid-drive)

Diese Powercircuits-Seite ist gegenüber dem Hackaday-Artikel die maßgebliche Quelle für den aktuellen öffentlichen Stand. Sie stellt oder verlinkt editierbares CAD, eine Stückliste und die Videoserie. Revisionsprüfungen beginnen dort, weil Sekundärartikel ältere Entwicklungsstände beschreiben können.

Bei der Prüfung am 2026-08-29 bezeichnet die Projektseite die Entwicklung ausdrücklich als Beginn eines Weges und veröffentlicht:

- die editierbare Baugruppe `Drive_Unit_R3.step`, bezeichnet als CAD-Revision 3 vom August 2026;
- eine Stückliste der Revision 2; und
- eine verlinkte Videoserie zum Bau.

Vom Nutzer gelieferte primäre Videoquelle:

- [Videoserie zum Open Source Electric Mid-Drive](https://www.youtube.com/watch?v=ENQmXIPajfI&list=PLKUZZkTf8y0U) — Playlist-ID `PLKUZZkTf8y0U`, Einstiegsvideo `ENQmXIPajfI`

Vom Nutzer benannte Einzelvideos:

1. [#1 Open Source eBike Mid-Drive — Project Start with Revopoint MetroX 3D Scanner](https://www.youtube.com/watch?v=irtROmmcAvQ) — Video-ID `irtROmmcAvQ`
2. [DIY eBike Mid-Drive](https://www.youtube.com/watch?v=0jco-RKzRSo) — Video-ID `0jco-RKzRSo`
3. [3D Printed eBike Mid-Drive with Helical Gears](https://www.youtube.com/watch?v=ENQmXIPajfI) — Video-ID `ENQmXIPajfI`

Diese Reihenfolge folgt der aus den gelieferten Titeln erkennbaren Projekterzählung, nicht einer unabhängig geprüften Veröffentlichungsreihenfolge. Der Revopoint-MetroX-Scanner gehört zum Entwicklungs- und Reverse-Engineering-Ablauf. Daraus folgt nicht, dass der fertige Mittelmotor oder der Adaptive Cycle im Betrieb einen 3D-Scanner benötigt.

Die Videos sind gemeinsam mit CAD und Stückliste zu prüfen. Sie können Konstruktionsabsicht, Montage, Tests, Fehler und Revisionsänderungen zeigen, die auf der kompakten Projektseite fehlen. Eine Videodemonstration belegt nur die gezeigte Konfiguration und ersetzt keine Zeichnung, Messung oder Prüfung.

Der [Hackaday-Fundartikel](https://hackaday.com/2026/07/18/open-source-mid-drive-e-bike-motor-has-lots-of-promise-and-hyphens/) berichtet von einem Motor aus einem Akku-Winkelschleifer, umfangreichen 3D-Druckteilen mit metallischen Lagerflächen, einem Klemmrollenfreilauf für das Weitertreten ohne Motor und einer später CNC-gefertigten Achse als Ersatz für den ersten Druckprototyp. Er nennt außerdem 25 km/h als Ziel.

Vor technischer Nutzung sind diese Angaben anhand des aktuellen CAD, der Stückliste und der Bauvideos zu bestätigen. Die Primärseite veröffentlicht bislang keine validierte Leistungsspezifikation, Bestimmung der Nenndauerleistung, Dauerhaltbarkeitsprüfung, Steuerlogik, thermischen Daten oder Konformitätsnachweise.

### Open Source Tadpole Tilting Cargo Trike

Primärseite: [Powercircuits — Open Source Tadpole Tilting Cargo Trike](https://www.powercircuits.nl/home/open-source-tadpole-tilting-cargo-trike)

Die Seite beschreibt einen vollständig gebauten und fahrbaren offenen Entwurf, der noch Verbesserungen benötigt. Bei der Prüfung am 2026-08-29 stellt sie eine Bauvideoserie, editierbares CAD der Revision 8 vom Juli 2026 und eine Teileliste für spezielle Komponenten bereit.

Vom Nutzer gelieferte primäre Videoquelle:

- [Videoserie zum Open Source Tadpole Tilting Cargo Trike](https://www.youtube.com/watch?v=UWFQ6nFzpgE&list=PL3uwHLwN7YKrodkpyXISvayLdFsccHNWB) — Playlist-ID `PL3uwHLwN7YKrodkpyXISvayLdFsccHNWB`, Einstiegsvideo `UWFQ6nFzpgE`

Das Dreirad ist ein Konstruktionspräzedenzfall, keine Bauteilzertifizierung. Relevant sind:

- Neigetechnik, Lenkung und Federung einer Tadpole-Anordnung;
- Einbau bei zwei Vorder- und einem Hinterrad;
- zugängliche CAD- und Fertigungsentscheidungen;
- praktische Iteration über mehrere Revisionen; und
- eine plausible Einbauumgebung für einen offenen Mittelmotor.

## Vorläufig berichtete Antriebsarchitektur

Die folgende Darstellung ist eine Forschungszusammenfassung, keine eingefrorene Spezifikation:

```text
wiederverwendeter Elektromotor
        ↓
Untersetzung / gedruckte und metallische Bauteile
        ↓
Freilauf- oder Klemmrollenfunktion
        ↓
Tretlager- / Kurbelantrieb
        ↓
gewöhnliche Fahrradschaltung und Antriebsrad
```

Bei einem Mittelmotor gelangt das Motordrehmoment vor der Endübersetzung in den Fahrradantrieb. Die normalen Gänge können für Steigung und Reise genutzt werden; ein zentraler Antrieb vermeidet zusätzliche ungefederte Masse an einem beweglichen Rad.

Beim Adaptive Cycle könnte eine gemeinsame Zwischenwelle möglicherweise aufnehmen:

- Drehmoment der Fußpedale;
- optionales Drehmoment des Ruder-/Handantriebs;
- regelkonforme elektrische Unterstützung; und
- eine wählbare Untersetzung zum Antriebsrad.

Dies ist ein Konzept. Ohne Anpassung darf nicht angenommen werden, dass der veröffentlichte Neves-Antrieb mehrere Muskeleingänge, unsere Nutzlast oder das transformierbare Fahrgestell unterstützt.

## Mögliche Vorteile

- **Reparierbarkeit:** Editierbare Geometrie und identifizierbare Teile können lokale Reparaturen ermöglichen.
- **Entwurfshoheit:** Übersetzungen, Schnittstellen, Lager, Kupplung, Gehäuse und Befestigungen lassen sich prüfen und ändern.
- **Einbau:** Ein angepasster Zentralantrieb könnte besser zu Fahrgestell und Zwischenwelle passen als ein rahmenspezifischer Kaufmotor.
- **Muskelkraft bleibt verfügbar:** Ein richtig ausgelegter Freilauf kann das Weitertreten nach elektrischem Ausfall ermöglichen.
- **Iteration:** Offenes CAD erlaubt Lastanalyse, Materialwechsel und neue Schnittstellen ohne erneutes Reverse Engineering.
- **Gemeinsamer Erfahrungsschatz:** Das Neigedreirad kann Erkenntnisse zu Einbau, Lenkung, Federung und Lasten liefern.

## Wichtige Vorbehalte

### Reife des Prototyps

STEP-Datei und Stückliste schaffen Prüfbarkeit, aber keine Leistung, Sicherheit oder Straßenzulässigkeit. Vor einer Auswahl werden mindestens benötigt:

- Dauer- und Spitzendrehmoment an Kurbel oder Ausgang;
- Motordrehzahl, Gesamtuntersetzung, Trittfrequenzbereich und Wirkungsgrad;
- thermisches Verhalten bei dauerhafter Steigung;
- Lasten von Zahnrädern, Wellen, Lagern, Freilauf, Gehäuse und Befestigung;
- Spiel, Geräusch, Schmierung, Abdichtung, Verschmutzung und Wartungsintervalle;
- Ermüdungs- und Stoßverhalten;
- Verhalten bei blockiertem Motor, Regler, Freilauf, Sensor oder Getriebe;
- sichere Trennung und Weitertreten nach elektrischem Ausfall; und
- reproduzierbare Fertigung aller sicherheitskritischen Teile.

### Wiederverwendeter Winkelschleifermotor

Ein Handwerkzeugmotor kann mit deutlich höherer Drehzahl und anderem Lastprofil arbeiten als ein Fahrradmittelmotor. Untersetzung, Kühlung, Lager, Geräusch, Kommutierung, Regler und Dauerleistung müssen gemessen werden. Wiederverwendung ist für Versuche attraktiv, muss aber nicht die beste Endarchitektur sein.

### Gedruckte tragende Teile

3D-Druck eignet sich für Gehäuse, Schutzteile, Kanäle, Passproben, Opferteile und gering belastete Geometrie. Teile in Kurbel-, Achs-, Lagerhalte-, Drehmomentstütz- oder Fahrzeuglastpfaden benötigen konkrete Nachweise zu Material, Orientierung, Temperatur, Kriechen, Ermüdung und Ausfall. Eine CNC-Achse ist eine sinnvolle Entwicklung, validiert aber nicht automatisch alle übrigen Lastpfade.

### Lizenzierung

„Open Source“ darf nicht allein aus frei zugänglichen Downloads oder öffentlichem CAD abgeleitet werden. Vor Kopie, Änderung oder Weiterverteilung sind ausdrückliche Lizenzen für Hardware, CAD, Dokumentation und Software festzuhalten. Die geprüften Projektseiten zeigten in ihrem sichtbaren Text keine Lizenzbedingungen.

## Aussage zu 25 km/h

Hackaday berichtet 25 km/h als Projektziel. Diese Zahl belegt weder, dass der Prototyp sie unter repräsentativer Last erreicht, noch deutsche oder europäische Pedelec-Konformität.

Für das Referenzfahrzeug umfasst die regulatorische Entwurfsbasis mindestens:

- echten Muskelantrieb über geeignete Pedale oder Handkurbeln;
- höchstens 0,25 kW Nenndauerleistung des Hilfsmotors für den angestrebten Pedelec-Weg;
- progressive Reduktion und Ende der Unterstützung bis 25 km/h;
- Ende der Unterstützung beim Ende der maßgeblichen Muskeleingabe;
- regelkonforme Anfahr-/Schiebehilfe, falls vorhanden;
- keine versteckte Gasgriff-, Service- oder Alternativkonfiguration mit anderem Straßenverhalten; und
- Belege für Lenkung, Bremsen, Beleuchtung, Struktur und Stand der Technik.

Siehe [Einstufungsmatrix](../regulatory/classification_DE.md), [Deutschland](../regulatory/germany_DE.md) und [EU](../regulatory/eu_DE.md). Ein frei konfigurierbarer Regler ist für Entwicklung nützlich, erhöht aber den Bedarf an eingefrorenem Straßenprofil, Manipulationsschutz und nachvollziehbarem Nachweis von Nenndauerleistung und Abschaltung.

## Prüfplan

1. Aktuelle STEP-Datei und Stückliste mit Revision, Datum und Lizenz archivieren.
2. Gesamten Leistungspfad und alle drehmomenttragenden, lagerhaltenden und fahrzeugseitigen Teile bestimmen.
3. Motordrehzahl, Untersetzungen, Kurbelkadenz, Ausgangsdrehmoment und theoretische Fahrgeschwindigkeit ableiten.
4. Prüfen, ob Motor und Regler eine belastbare Konfiguration mit 250 W Nenndauerleistung ermöglichen.
5. Thermik und Dauersteigung für die höhere Masse des Referenzfahrzeugs untersuchen.
6. Freilauf-Fehlerbilder, Heimfahrwiderstand und Blockiereinschluss bewerten.
7. Mit reparierbaren kommerziellen oder VESC-kompatiblen Mittelmotoren vergleichen.
8. CAD des Neigedreirads getrennt auf Einbau- und Fahrwerkspräzedenzfälle prüfen.
9. Pedro Neves erst mit technischen Fragen kontaktieren, die nicht durch veröffentlichte Dateien beantwortet werden.
10. Einen ersten Aufbau nur auf Prüfstand oder zugangskontrolliertem Privatgelände betreiben.

## Offene Fragen

- Welcher Motor, welche Wicklung, Nennspannung, Stromgrenze, Steuerung und Kommutierung werden in Revision 3 verwendet?
- Wie lauten Gesamtuntersetzung, Sollkadenz, gemessene Fahrgeschwindigkeit und Prüfzuladung?
- Sind 25 km/h gemessen, berechnet oder nur als Ziel gewählt?
- Welche Dauerleistung und Temperaturerhöhung wurden gemessen?
- Welche Teile werden aktuell mit welchen Werkstoffen und Druckparametern gefertigt?
- Welche Änderungen an Achse, Freilauf, Zahnrädern, Lagern und Befestigung gab es zwischen den Revisionen?
- Kann das System Drehmoment-/Trittfrequenzsensorik und eine regelkonforme progressive Abschaltung aufnehmen?
- Welcher Widerstand bleibt ohne Strom oder bei Ausfall?
- Wie lässt sich ein blockierter Motor oder Untersetzungsstrang von den Pedalen trennen?
- Welche ausdrücklichen Lizenzen gelten für CAD, Stückliste, Dokumentation, Videos, Firmware und Ableitungen?
- Bleiben Neigung, Federung, Lenkung und Bodenfreiheit bei Einbau in das Dreirad erhalten?
- Welche Erkenntnisse übertragen sich auf das schwere adaptive Fahrzeug und welche nur auf den Lastenradprototyp?

## Aktuelle Bewertung

**Verfolgen und prüfen; noch nicht auswählen.** Die stärkste Eigenschaft ist die offene Prüfbarkeit des Entwurfs und die Verbindung zu einem realen Neige-Lastendreiradprogramm. Die größte Schwäche ist die Belegreife: Die veröffentlichten Artefakte zeigen ein aktives Prototypenprojekt, keinen validierten straßenfertigen 250-W-/25-km/h-Antrieb.

Mögliche spätere Rollen:

- Lernreferenz für einen offenen gemeinsamen Zwischenwellenantrieb;
- Quelle anpassbarer CAD-Schnittstellen;
- Kooperationsmöglichkeit;
- früher Versuchsantrieb nach unabhängiger Lastprüfung; oder
- Anstoß für eine reifere offene Motor-/Reglerarchitektur mit denselben Reparaturzielen.

## Quellen

Zentrale Projektquellen, geprüft am 2026-08-29:

- [Pedro Neves / Powercircuits — Open Source Electric Mid-Drive](https://www.powercircuits.nl/home/open-source-electric-mid-drive)
- [Videoserie zum Open Source Electric Mid-Drive](https://www.youtube.com/watch?v=ENQmXIPajfI&list=PLKUZZkTf8y0U) (vom Nutzer geliefert; automatischer Seitenabruf nicht möglich)
- [#1 Open Source eBike Mid-Drive — Project Start with Revopoint MetroX 3D Scanner](https://www.youtube.com/watch?v=irtROmmcAvQ) (Titel und Link vom Nutzer geliefert)
- [DIY eBike Mid-Drive](https://www.youtube.com/watch?v=0jco-RKzRSo) (Titel und Link vom Nutzer geliefert)
- [3D Printed eBike Mid-Drive with Helical Gears](https://www.youtube.com/watch?v=ENQmXIPajfI) (Titel und Link vom Nutzer geliefert)

Verwandtes Primärprojekt:

- [Pedro Neves / Powercircuits — Open Source Tadpole Tilting Cargo Trike](https://www.powercircuits.nl/home/open-source-tadpole-tilting-cargo-trike)
- [Videoserie zum Open Source Tadpole Tilting Cargo Trike](https://www.youtube.com/watch?v=UWFQ6nFzpgE&list=PL3uwHLwN7YKrodkpyXISvayLdFsccHNWB) (vom Nutzer geliefert; automatischer Seitenabruf nicht möglich)

Sekundärer Fundhinweis:

- [Hackaday — Open-Source Mid-Drive E-Bike Motor Has Lots Of Promise, And Hyphens](https://hackaday.com/2026/07/18/open-source-mid-drive-e-bike-motor-has-lots-of-promise-and-hyphens/)
