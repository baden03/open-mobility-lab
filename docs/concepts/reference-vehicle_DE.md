# Referenzfahrzeug: Adaptive Expedition Trike

[English](reference-vehicle.md) · [Konzepte](README_DE.md) · [Regulatorische Einstufung](../regulatory/classification_DE.md)

**Status:** Zusammengeführtes Konzept aus dem ersten Entwurfsgespräch; Anforderungen und Architektur sind vorläufig  
**Rechtliches Ziel:** Deutsches Fahrrad / EPAC mit 250 W, vorbehaltlich Bestätigung und Validierung  
**Hauptweg:** 12 km je Richtung auf deutschen außerörtlichen Radwegen  
**Referenzpersona:** Ol’ Captain Hinkebein, eine große und schwere Person mit eingeschränkter Kniebeugung und einem ersetzten oder anderweitig problematischen Knie

## 1. Entwicklungsabsicht

Das Referenzfahrzeug ist ein transformierbares, elektrisch unterstütztes Liege-Dreirad in Tadpole-Anordnung. Eine Person, die sich nicht bequem in ein gewöhnliches Liegedreirad absenken kann, soll sich einem Sitz in Stuhlhöhe nähern, würdevoll Platz nehmen und das Fahrzeug um sich herum in eine stabile, effiziente Fahrhaltung transformieren lassen.

Es ist kein Elektromobil mit Alibi-Pedalen. Das Straßenkonzept nutzt echten kontinuierlichen Muskelkraftantrieb und einen rechtlich begrenzten Hilfsmotor. Die Beine sollen bei angenehmer Frequenz und Belastung sinnvoll bewegt werden. Optionaler Handantrieb ergänzt Oberkörperleistung, ohne Arme und Beine an dieselbe Frequenz zu koppeln.

## 2. Zusammengeführte Anforderungen

| Bereich | Vorläufige Anforderung | Herkunft / Sicherheit |
| --- | --- | --- |
| Weg | 24 km Hin- und Rückweg plus definierte Reserve | Ausdrücklicher Bedarf; hoch |
| Infrastruktur | Sicheres Passen und Verhalten auf außerörtlichen Radwegen und üblichen Zufahrten | Ausdrücklicher Bedarf; hoch |
| Unterstützte Geschwindigkeit | Unterstützung endet progressiv spätestens bei 25 km/h | Rechtliches Ziel; hoch |
| Muskelkraft | Echtes, einstellbares Fußtreten bleibt verfügbar und nützlich | Ausdrückliche Präferenz; hoch |
| Zugang | Einstieg ungefähr in Stuhlhöhe, ohne sich in einen Liegesitz absenken zu müssen | Ausdrücklicher Bedarf; hoch |
| Fahrhaltung | Niedrige, gestützte, halb liegende oder liegende Haltung für Stabilität und geringeren Luftwiderstand | Ausdrückliches Konzept; hoch |
| Geometrie | Zwei Vorderräder, ein Hinterrad | Wiederholtes Konzept; mittel bis hoch |
| Transformation | Kurz/hoch/aufrecht beim Zugang; lang/niedrig/geneigt beim Fahren | Ausdrückliches Konzept; hoch |
| Handantrieb | Optionale unabhängige ruderähnliche Eingaben links/rechts ergänzen Muskelkraft | Ausgearbeitete Option; mittel |
| Sicherheit | Mechanische Verriegelungen—nicht der Aktuator—tragen Fahrbelastungen | Ausdrücklicher Grundsatz; hoch |
| Fahrzeugklasse | Behandlung als Fahrrad/EPAC statt L-Fahrzeug oder Krankenfahrstuhl | Ausdrückliche Richtung; mittel, Prüfung offen |

Zahlen in diesem Dokument sind Packaging-Hypothesen, keine freigegebenen Konstruktionsmaße.

## 3. Fahrzeugarchitektur

```text
                       FAHRENDE PERSON
               Füße                         Hände
                 │                            │
    einstellbare Fußkurbel       unabhängige Rudergriffe
                 │                            │
          Freilauf / Getriebe          Überholkupplungen
                 └──────────┬─────────────────┘
                            │
                     Zwischenwelle
                            │
                   Getriebe / Antriebsrad
                            ↑
          Hilfsantrieb mit ≤250 W Nenndauerleistung
          progressives Ende spätestens bei 25 km/h

       zwei gelenkte/gebremste Vorderräder ── ein angetriebenes Hinterrad
```

Die Skizze zeigt die Funktion, nicht den ausgewählten Kettenlauf oder das Getriebe. Direkter mechanischer Fußantrieb ist die konservative Basis. Der Motor kann Hinterrad, Kurbel oder Zwischenwelle antreiben, sofern Unterstützungsverhalten und Nenndauerleistung der gewählten Klasse entsprechen.

## 4. Jack-Knife-Fahrgestell

### 4.1 Strukturkonzept

Das Fahrgestell besteht konzeptionell aus einem vorderen und hinteren Strukturmodul, verbunden durch eine geführte Kinematik nahe Hüfte/Sitz. Beim Zusammenziehen nähern sich die Radmodule, während der Sitz steigt und sich aufrichtet. Beim Strecken verlängert sich der Radstand, der Sitz sinkt und neigt sich, und der Abstand zwischen Hüfte und Kurbel wächst.

Ein Viergelenk oder eine ähnliche zwangsläufige Kinematik wird mehreren unabhängigen Sitzschienen vorgezogen, weil ein gesteuerter Freiheitsgrad gemeinsam verändern kann:

- Radstand;
- Sitzhöhe;
- Rückenlehnenwinkel;
- Abstand zwischen Hüfte und Kurbel;
- Durchstiegsraum; und
- eingeklappte beziehungsweise aktive Handbedienung.

### 4.2 Betriebsarten

| Modus | Geometrie | Nutzung | Antriebsrahmen |
| --- | --- | --- | --- |
| **ACCESS** | Kurzer Radstand, Sitz in Stuhlhöhe, aufrechte Lehne, viel Kniefreiraum | Ein-/Ausstieg, Parken, Positionieren | Transformation im Stand; Rangieren nur bei bestätigter Verriegelung und streng begrenztem Schritttempo |
| **URBAN** | Mittlere Länge und Sitzneigung | Geschäfte, enge Infrastruktur, langsames Manövrieren | Verringerte Geschwindigkeit/Beschleunigung bis diese Geometrie eigenständig validiert ist |
| **CRUISE** | Langer Radstand, niedriger Sitz, geneigte Lehne, vordere Kurbel | Außerörtliche Radwege und effizientes Fahren bis 25 km/h Unterstützung | Volle legale Unterstützung erst bei bestätigten Fahrverriegelungen |

Im Gespräch dienten ungefähr 550–650 mm Sitzhöhe in ACCESS, 300–400 mm in CRUISE, etwa 400–600 mm Längsbewegung und ungefähr 1,9–2,1 m ausgefahrene Länge zur Veranschaulichung. Reale Maße folgen aus anthropometrischen Modellen, Stabilitätsanalyse, Wegegeometrie, Transportgrenzen und Strukturentwurf.

### 4.3 Transformationsablauf

**Einstieg:** parken → unabhängige Feststellbremse betätigen → Fahrantrieb sperren → stabilen Zustand prüfen → Transformation entriegeln → ACCESS anfahren → Zugangsverriegelung schließen → Armlehne/Bedienung freigeben → Person setzt um → Stützen einstellen → Bedienelemente schließen → CRUISE anfordern → tragende Verriegelungen schließen → Verriegelungssensoren kreuzprüfen → Antrieb freigeben.

**Ausstieg:** anhalten → Feststellbremse → Fahrantrieb sperren → sichere Transformationsbedingungen prüfen → Antriebsstrang entlasten/kontrollieren → Fahrverriegelungen lösen → in ACCESS transformieren → Zugangsverriegelung schließen → Armlehne/Bedienung freigeben → Person steht auf oder setzt um.

Transformation während der Fahrt gehört nicht zum Referenzkonzept. Bewegung in ACCESS oder URBAN ist nur in einer mechanisch verriegelten Konfiguration zulässig.

### 4.4 Lastpfad und Fehlerstrategie

Der Aktuator bewegt; er trägt nicht die normalen Fahrbelastungen. Große Bolzen, Klauen, Keile oder Übertotpunkt-Verriegelungen schaffen in jedem Fahrmodus einen direkten strukturellen Lastpfad. Stromausfall darf einen verriegelten Rahmen nicht entriegeln. Ein einzelner Positionsschalter genügt nicht; plausibel erfasst werden müssen Zielposition und physische Verriegelung.

Zu analysieren sind asymmetrische oder unvollständige Bewegung, unkontrollierte Schwerkraftbewegung, Quetsch-/Scherstellen, Aktuator-Durchlauf, verschmutzte Verriegelung, Pivot-Ermüdung, Bodenkontakt, Einklemmen der Person und Notrettung. Manuelle Bergung darf Helfende nicht unter eine ungestützte Struktur zwingen.

## 5. Fahrwerk und Stabilität

Basis ist die Tadpole-Anordnung: zwei gelenkte und unabhängig gebremste Vorderräder, ein Hinterrad; Batterie und Getriebe liegen tief nahe der Längsmitte. Zu untersuchen sind Kippgrenzen in allen verriegelten Modi, Schwerpunktwanderung, Ackermann, Lenkrollradius, Nachlauf/Selbstzentrierung, Bump-Steer, Bremslenken, Hinterradentlastung, Wendekreis, Bordsteine, Reifenfreigang und Ausfall eines Bremskanals.

Eine variable Vorderspur bleibt Forschungsoption und ist keine Basisfunktion. Eine nur zum Lagern einklappbare Spur mit starrer Fahrverriegelung ist beherrschbarer als kontinuierlich variable Breite. Jeder fahrbare schmale oder breite Zustand ist eine reale Konfiguration für Stabilität, EMV, Steuerungssicherheit und Einstufung—kein „Prüfmodus“ neben einem verschwiegenen Betriebsmodus.

## 6. Sitz und Biomechanik

Die Person nähert sich einem stützenden Sitz, statt über einen Rahmen zu steigen oder in eine tiefe Liegeschale zu sinken. Vorgesehen sind breite Sitzfläche, stützende Lehne, einstellbare Lendenstütze, moderate Seitenführung, wegschwenkbare Armlehnen und Druckverteilung.

Die Fußkurbel ermöglicht sinnvolle Bewegung ohne ungeeigneten Beugewinkel des problematischen Knies. Einstellbar sind Kurbel-Sitz-Abstand, Sitz-/Lehnenwinkel, Pedalposition und Kurbellänge, möglicherweise mit unterschiedlichen wirksamen Radien links/rechts. Unabhängige Kurbeln bleiben Option. Gelenkwege, Leistung und Frequenz werden nicht aus einer Diagnose abgeleitet, sondern zuerst an einem verstellbaren stationären Prüfstand bestimmt.

## 7. Muskel- und Elektroantrieb

### 7.1 Fußantrieb

Das Fußtreten ist die grundlegende qualifizierende Muskelkrafteingabe und Trainingsschnittstelle. Es überträgt nutzbare mechanische Leistung zum Rad; reine Sensorscheinpedale widersprechen dem Entwicklungsziel.

In der konservativen Straßenkonfiguration wird Motorunterstützung durch echtes Fußtreten aktiviert, bis 25 km/h progressiv reduziert und beim Ende des Tretens abgeschaltet. Anfahr-/Schiebehilfe bis 6 km/h kommt nur innerhalb des deutschen Rahmens und nach Gesamtprüfung in Betracht.

### 7.2 Ruderähnlicher Handantrieb

Zwei lange Hebel oder Griffe erzeugen eine Hin-und-her-Bewegung für Schultern, Rücken, Arme und Rumpf. Seile, Ketten, Gestänge, Kurvenscheiben oder variable Rollen wandeln den Hub in Drehung. Jede Seite speist über eine Überholkupplung die Zwischenwelle:

```text
linker Zug  ── Freilauf ──┐
rechter Zug ── Freilauf ──┼── Zwischenwelle ── Getriebe
Fußkurbel   ── Freilauf ──┘
```

Der Rückhub treibt weder die andere Hand noch die Füße zurück. Eine Hand kann antreiben, während die andere lenkt; auf übersichtlicher Geraden arbeiten beide. Übersetzung und Kraftverlauf entlasten Hubenden und nutzen den starken mittleren Bereich.

Die Rechtsbegriffe sind nicht einheitlich: §63a StVZO nennt Pedale **oder Handkurbeln**, während §1 Absatz 3 StVG und die EU-EPAC-Ausnahme auf Treten abstellen. Deshalb hängt die Referenzklasse nicht von der Anerkennung der Ruderkinematik ab. Die Füße sichern die konservative Pedelec-Basis; die Hände ergänzen ausschließlich mechanische Muskelkraft. Ob Handbewegung zusätzlich Motorunterstützung auslösen darf, benötigt schriftliche Einstufungsberatung.

### 7.3 Über 25 km/h

25 km/h ist die Unterstützungsgrenze, keine Fahrrad-Höchstgeschwindigkeit. Darüber liefert der Motor keinen Vortrieb; Fuß- und Handkraft dürfen weiterwirken. Es gibt keinen Schalter, der die Motorunterstützung oberhalb der Grenze wiederherstellt.

## 8. Lenkung und Bremsen

Basis ist eine handnah erreichbare Lenkung mit gutem Geradeauslauf und Selbstzentrierung—nicht Fußlenkung. Lenkung und Bremsen müssen sofort verfügbar sein, wenn eine oder beide Hände zuvor angetrieben haben.

Zwei unabhängige Betriebsbremsen sind für Fahrräder vorgeschrieben. Das schwere, niedrige Dreirad benötigt lastgerechte Bremskraftverteilung und Widerstand gegen Bremslenken. Eine Feststellbremse ist für Umstieg und Transformation zwingend. Rekuperation ergänzt die mechanischen Bremsen, ersetzt sie aber nie.

## 9. Energiesystem

Ausgelegt wird auf den definierten 24-km-Rückweg plus Reserve unter festgelegter Personenmasse, Steigung, Oberfläche, Wind, Temperatur, Starts, Reifendruck, Nebenverbrauchern und Batteriealterung. Frühere Gesprächswerte von 1–3 kWh stammten aus unterschiedlichen Rover-Annahmen und sind keine Anforderung. Ein Pedelec-Fahrzyklus bestimmt die Kapazität.

Der Hauptakku liegt tief im Fahrzeug und muss nicht von der Person gehoben werden. Kleine Reichweitenmodule benötigen kodierte Steckverbinder, Isolation, sichere Halterung, Zustandsbestimmung und Rechtsprüfung. Die Beleuchtung muss auch nach Abschaltung der Unterstützung gemäß StVZO versorgt bleiben.

Ein Schwungrad wurde als kleiner Leistungspuffer für einen Brems-/Beschleunigungsvorgang und Transformationsenergie diskutiert. Wegen Berstschutz, Lagerung, Überdrehzahlschutz, Masse, Verlusten und der Behandlung gespeicherter Muskelenergie ist es nicht Teil der Basis. Referenz ist Batterieversorgung mit manueller Rückfallebene.

## 10. Steuerung und Anzeige

Die Steuerung verwaltet Unterstützung, Verriegelungs-Interlocks, Antriebssperre während Transformation, Batterieschutz, Diagnose, Beleuchtung und eine Rückweg-Reichweitenanzeige. Sichtbar sein müssen Fahrmodus, erforderliche Verriegelungen, Feststellbremse, Antriebsfreigabe, Unterstützungszustand, Reserve und Fehler.

Sensorwiderspruch, unterbrochene Transformation, Kommunikationsausfall, Unterspannung und unbeabsichtigter Befehl sind eigene Zustände. Mechanisches Bremsen und strukturelle Verriegelung bleiben nach Softwareausfall erhalten.

## 11. Regulatorische Architektur

Die beabsichtigte Straßenkonfiguration hat:

- mindestens zwei Räder (drei in der Referenz);
- echten Muskelantrieb über Fußpedale;
- einen elektromotorischen Hilfsantrieb mit höchstens 0,25 kW Nenndauerleistung;
- progressive Reduktion und Ende der Unterstützung spätestens bei 25 km/h;
- Ende der Unterstützung beim Ende des Fußtretens;
- optional deutsche Anfahr-/Schiebehilfe bis höchstens 6 km/h;
- keinen Gasgriff für normale Fahrt und keine Tempo-Überbrückung;
- fahrradkonforme Lenkung, zwei unabhängige Bremsen, Glocke, Beleuchtung und Rückstrahler.

Siehe [Einstufung](../regulatory/classification_DE.md), [Deutschland](../regulatory/germany_DE.md) und [EU](../regulatory/eu_DE.md). Vor öffentlichen Tests wird eine eingefrorene Konfiguration eingestuft.

## 12. Ausdrücklich nicht Teil der Basis

- drei Nabenmotoren mit je 300–500 W / elektronischer 3WD;
- motorisierter Krankenfahrstuhl mit 15 km/h;
- vom Benutzer abschaltbare Geschwindigkeitsbegrenzung;
- Fußlenkung mit reinem Handkurbelantrieb;
- variable Spurweite während der Fahrt;
- Pedal-by-wire ohne mechanischen Muskelkraftpfad zum Rad;
- Schwungrad als wesentlicher Fahrenergiespeicher;
- Exoskelett zur Fortsetzung motorischer Hilfe über 25 km/h;
- [Adaptives Fahrwerk](adaptive-running-gear_DE.md) als spätere Hindernis- und Crawl-Option in Urban-Geometrie (Pilot/Ausleger, Krücken/Kurvenscheiben und B2-W-inspirierte Artikulation bleiben zu verfolgende Alternativen).

Diese Varianten sind eigene Fahrzeugkonfigurationen und Rechtsklassen, keine versteckten Modi eines genehmigten Fahrzeugs.

## 13. Validierungsmeilensteine

1. **Bedarf:** beobachtete Anforderungen an Umstieg, Haltung, Frequenz, Kraft, Weg, Lagerung und Unterstützung.
2. **Einstufung:** schriftliche Prüfung der eingefrorenen Konfiguration, besonders Transformation und Handantrieb.
3. **Prüfstand:** sichere Ergebnisse für Biomechanik und Ruderantrieb.
4. **Analyse:** Struktur, Ermüdung, Stabilität, Lenkung, Bremsen, Energie, Thermik, Elektrik und Fehler.
5. **Verriegelung:** Prüfbelastung, Dauerlauf, Verschmutzung, Teilverriegelung, Stromausfall und manuelle Bergung.
6. **Rollprototyp:** kontrollierte Privatgelände-Tests mit stufenweise steigender Geschwindigkeit und Last.
7. **Straße:** Bauvorschriften erfüllt, Einstufung dokumentiert, Gefahren geschlossen/akzeptiert, Fachprüfung abgeschlossen.

## 14. Offene Entscheidungen

- Genaue ACCESS-, URBAN- und CRUISE-Maße und Nutzen von URBAN.
- Feste oder nur zur Lagerung einklappbare Vorderspur.
- Hinterradnabe, Mittelmotor oder Zwischenwellenmotor.
- Kette, Riemen, Getriebe, CVT und unabhängige Frequenzen.
- Lenkung für Ein- und Zweihandbetrieb.
- Batteriekapazität, Spannung, Chemie, Entnahme und Laden.
- Verriegelungstopologie und Notbergung.
- Handantrieb im ersten Straßenprototyp oder erst nach Fußantriebsvalidierung.

