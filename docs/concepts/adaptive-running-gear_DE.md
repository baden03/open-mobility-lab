# Adaptives Fahrwerk

[English](adaptive-running-gear.md) · [Konzepte](README_DE.md)

**Status:** Exploratives Konzept für eine spätere Option; nicht Teil der ersten Straßenkonfiguration und kein validierter Entwurf

Zur Fahrgestellgeometrie siehe das [transformierbare Fahrgestell](transforming-chassis_DE.md) und das [Referenzfahrzeug](reference-vehicle_DE.md#4-jack-knife-fahrgestell). Adaptive Running Gear (**Adaptives Fahrwerk**) ist eine spätere Option, keine Basisfunktion des ersten Straßenprototyps.

## Arbeitsentscheidungen

Gesprächsentscheidungen vom 2026-08-28. Sie beschreiben, wie dieses Konzept zu behandeln ist; sie sind keine validierten Anforderungen.

| Thema | Arbeitsentscheidung |
| --- | --- |
| Rolle | Spätere Option am Referenzfahrzeug, nicht Teil des ersten Straßenprototyps |
| Wirtsgeometrie | Nutzt die [Urban](reference-vehicle_DE.md#42-betriebsarten)-Geometrie (kompakter oder mittlerer Radstand, erhöhte Bodenfreiheit). **Crawl** ist ein eigener Laufwerk-Modus, kein Ersatz für Urban, Access oder Cruise |
| Architekturen | Drei Familien bleiben **zu verfolgende Alternativen**, kein ausgewähltes System: (1) hindernisausgelöste Pilotrolle und Ausleger, (2) von der fahrenden Person bediente oder kurvengesteuerte Krücken, (3) B2-W-inspirierte Mehrachs-Artikulation als Vergleichslehre |
| Crawl-Bedienung | Herkömmliches Lenken, Bremsen und Rudern laufen nicht gleichzeitig mit der Krückenarbeit. Ein Halt-/Festhalteverfahren im Crawl-Modus bleibt eine offene Konstruktionsfrage |
| Fahrende Person | Die [Referenzpersona](reference-vehicle_DE.md) hat starke Oberkörperkapazität. Die Krückenführung ist analog zu Skistöcken. Treten im Crawl-Tempo darf die maximale Unterstützung innerhalb der bestehenden 250-W-EPAC-Hülle nutzen, keinen Modus mit höherer Leistung und keinen Gasgriff |
| Erste Untersuchung | Eine kurze Folge von **zwei Stufen**, mit ausreichender Auftritts- oder Podesttiefe, annähernd rechtwinkliger Anfahrt, sehr niedriger Geschwindigkeit und einer Fläche, die die Last des ausgebrachten Rades tragen kann. Isolierte Steigungen oder Absätze um **180–220 mm** bleiben ein gesprächsabgeleiteter Höhenbereich, keine anerkannte Anforderung |

Packaging, Tadpole-Stützanordnung, Masse- und Energiebudget sowie Einstufungsfragen bleiben offen, bis das Thema vertieft aufgenommen wird.

## Vision

> Die fahrende Person soll sich nicht um das Gelände kümmern müssen. Das Fahrzeug soll Fahrwerk, Federung und Geometrie still anpassen, sodass Bordsteine, Wegstufen, unebene Flächen und Trailhindernisse Routine statt Barrieren werden.

**Adaptives Fahrwerk** erweitert das Vorhaben von einem anpassungsfähigen Straßenrad hin zu einem persönlichen Geländefahrzeug, ohne es in einen herkömmlichen Treppen-Krankenfahrstuhl oder ein geländegängiges Kraftfahrzeug zu verwandeln. Wird es als spätere Option verfolgt, soll das vorgesehene System gelegentliche, begrenzte Hindernisse entlang sonst befahrbarer Wege bewältigen und dabei Würde, Komfort und Kontrolle der fahrenden Person sowie eine plausible Fahrrad- oder Pedelec-Konstruktionsgrundlage erhalten. Das Vision-Zitat oben ist aspirativ; das Betriebsmodell bleibt, dass die fahrende Person anhält, das Manöver beurteilt und einen Laufwerk-Modus wählt.

## Entwurfsziele

- Isolierte Bordsteine, flache Trail- oder Wegstufen, diskontinuierliche Neigungswechsel, Entwässerungskanten, Wurzeln, Spurrillen und unebene Übergänge bewältigen.
- Besetztes Fahrgestell und Sitz während Auf- und Abstieg in einer kontrollierten Nick- und Wankhülle halten.
- Last übertragen, bevor ein Hauptrad eine Kante überquert, statt das Fahrzeug fallen, nicken oder auf Impuls angewiesen zu lassen.
- Das wirksame Stützpolygon nur bei Bedarf vergrößern und danach in eine kompakte Straßenkonfiguration einziehen.
- Jeden Hindernismechanismus positiv verstauen und physisch sperren, bis die fahrende Person die jeweils benötigte Funktion wählt.
- Nur die vorderen, hinteren, linken oder rechten Stützelemente ausbringen, die für die aktuelle Aufstiegs-, Abstiegs- oder Stabilisierungsphase nötig sind.
- Mit dem transformierbaren Fahrgestell und der Federung integrieren, statt ein fremdes Klettergerät anzusetzen.
- Die nützliche Hindernisfähigkeit mit möglichst wenigen Gelenken, Aktuatoren, Sensoren und Steuerzuständen erreichen.
- Passive, hindernisausgelöste Gestängegeometrie untersuchen, bevor motorische Aktuierung oder elektronische Sensorik hinzukommt.
- Deterministische Mikrocontroller und einfache lokale Messgrößen nutzen, nicht Lidar, Kameras, 3-D-Rekonstruktion oder allgemeine autonome Navigation.
- Herkömmliches Lenken, Bremsen und Antreiben in Access, Urban-Fahrt und Cruise erhalten. Crawl ist ein eigener Modus, in dem diese Aufgaben nicht gleichzeitig mit der Krückenarbeit laufen.
- Bei Stromausfall, Sensorwiderspruch oder unvollständiger Ausbringung mechanisch stabile Zustände als Standard vorsehen.
- Masse, Breite, Energieverbrauch, Wartung und visuelle Komplexität im Verhältnis zu den tatsächlich anvisierten Hindernissen halten.

## Problemstellung

Ein langstreckentaugliches adaptives Rad kann kurze Hindernisse treffen, die für eine gehende Person gering, für ein niedriges, langes, schweres Dreirad mit Besetzung aber schwerwiegend sind:

- ein Bordstein oder eine erhöhte Wegbegrenzung;
- eine oder zwei Landschafts-, Trail- oder Wegstufen statt einer durchgehenden Treppe;
- ein abrupter Übergang zwischen Rampe und ebener Fläche;
- eine vertikale Diskontinuität an einer Brücke, Entwässerungsrinne oder beschädigtem Weg;
- Wurzeln, Steine, Erosion, Schlaglöcher, Querneigung oder unabhängig unterschiedliche Radhöhen; und
- ein Abstieg, bei dem das zuerst fallende Vorderrad einen unzulässigen Nickstoß erzeugen würde.

Gewöhnliche Federung kann den Reifenkontakt über kleine Unebenheiten halten, aber sie kann eine vertikale Kante nicht unbedingt überbrücken oder das Stützpolygon steuern, während ein Hauptrad keine geeignete Aufstandsfläche hat. Längerer Federweg allein kann den Schwerpunkt anheben, das Fahrverhalten beeinträchtigen und trotzdem keinen kontrollierten Zwischenstützpunkt liefern.

Dieses Konzept ist bewusst enger als „eine Treppe steigen“. Das Ziel der ersten Untersuchung ist eine kurze Folge von **zwei Stufen**, mit ausreichender Auftritts- oder Podesttiefe, annähernd rechtwinkliger Anfahrt, sehr niedriger Hindernis-Modus-Geschwindigkeit und einer Fläche, die die Last des ausgebrachten Rades tragen kann. Isolierte Steigungen oder Absätze um **180–220 mm** sind ein gesprächsabgeleiteter Höhenbereich, keine anerkannte Anforderung.

## Definition

**Adaptives Fahrwerk** ist die abgestimmte Menge ausfahrbarer Stützräder, Gelenkarme, struktureller Drehpunkte, Aktuatoren, Verriegelungen, Sensoren und Steuerlogik, die vorübergehend ändert, wie das Fahrzeug vom Boden getragen wird.

Der Begriff soll das System unterscheiden von:

- den primären Straßenrädern und ihrer normalen Federung;
- einem unabhängigen Hilfsantrieb;
- passiven Kippschutzrollen, die lediglich einen Sturz auffangen;
- Auslegern fester Breite; und
- einem allgemeinen Treppensteigmechanismus.

Das Fahrwerk kann heben, senken, abstützen, nivellieren, überbrücken oder Last übertragen. Seine bestimmende Funktion ist die Verwaltung von Kontaktgeometrie und Stabilität während eines begrenzten Hindernisereignisses.

Die folgenden drei Architekturfamilien sind zu verfolgende Alternativen. Keine ist ausgewählt. Ein späterer Entwurfsschritt kann eine behalten, Elemente kombinieren oder alle verwerfen.

## Ausfahrbare Gelenk-Stützräder

Diese Familie ist **Alternative 1**: ein hängendes oder greifendes Stützrad an einem Gelenkarm, einschließlich der unten beschriebenen rein mechanischen, hindernisausgelösten Pilotrolle.

Das Basiskonzept nutzt kleine Räder an gelenkigen Strukturarmen. Je nach endgültiger Architektur könnten ein vorderes Paar, ein hinteres Paar oder unabhängig gesteuerte Links-/Rechts-Einheiten während gewöhnlicher Fahrt innerhalb der Fahrgestellhülle verstaut werden.

Im ausgebrachten Zustand könnte ein Stützrad:

- nach vorn greifen und Kontakt auf einer oberen Fläche herstellen, bevor ein Hauptrad steigt;
- nach unten greifen und einen kontrollierten Abstieg stützen, bevor ein Hauptrad eine Kante überquert;
- das Stützpolygon bei Querneigung oder Radabhebung verbreitern oder verlängern;
- einen kontrollierten Anteil der Fahrzeugmasse tragen, während ein anderes Rad entlastet ist; und
- als vorübergehendes „Landegestell“ dienen, während das Fahrgestell zwischen Ebenen schwenkt oder verschiebt.

Kandidatenmechanismen sind nachlaufende oder vorlaufende Lenker, Mehrlenkerarme, Teleskoplenker, Dreharme oder kompakte Gestänge, die Drehung und Auszug kombinieren. Die Radarme sollen den Lastpfad in strukturelle Fahrgestellknoten führen, nicht in Karosseriebleche oder schwach belastete Federungsträger.

Zu untersuchen ist, ob jedes Stützrad frei nachlaufen, eingeschränkt lenken, mit der Hauptradspur fluchten, eine Bremse, einen Freilauf oder nur eine frei rollende Nabe braucht. Ein Tri-Star-Radstern bleibt Vergleichskonzept, aber Gelenkarme erscheinen für dieses Fahrzeug geeigneter, weil Platzierung, Lastanteil und Beitrag zur Fahrgestellnivellierung unabhängig steuerbar sind.

## Selektive Ausbringung und Richtungsmodi

**Adaptives Fahrwerk** soll während gewöhnlicher Fahrt nicht freiliegen und nicht jedes Stützelement bei jedem Hindernis ausbringen. **Vollständig eingefahren, verriegelt und mechanisch gesperrt ist der Grundzustand.** Die fahrende Person schaltet eine bestimmte Hindernisfunktion erst nach Anhalten und Beurteilung des Manövers bewusst scharf.

Die Bedienung soll Richtungsmodi enthalten, keine getrennten Vorder-/Hinterbefehle. Die Wahl einer Richtung schaltet das vollständige Vorder-und-Hinter-System scharf; der Mechanismus sequenziert seine inneren Phasen mit dem Fortschreiten des Fahrzeugs:

| Modus | Freigegebenes System | Gesperrte Mechanismen | Vorgesehene Funktion |
| --- | --- | --- | --- |
| **ASCEND** | Vollständiges Aufstiegssystem: vordere Pilot-/Hubphase, automatisch gefolgt von hinterer Stabilisierung/Hub | Alle Abstiegsfühler und Abstiegs-Freigabepfade | Das ganze Fahrzeug über mechanisch geordnete Vorder- und Hinterphasen nach oben tragen |
| **DESCEND** | Vollständiges Abstiegssystem: vorn kontrolliertes Absenken, automatisch gefolgt von hinten kontrolliertem Absenken | Alle Aufstiegspiloten und Aufstiegs-Freigabepfade | Das ganze Fahrzeug über mechanisch geordnete Vorder- und Hinterphasen nach unten tragen |
| **CRUTCH / CRAWL** | Unabhängig handbediente Krückenarme oder mechanisch synchronisierte Kurvenräder | Aufstiegs-/Abstiegstrigger, die der Zyklus nicht nutzt; alle Cruise-Freigaben | Ruhiger, bewusster Fortschritt über ein kurzes, sonst unpassierbares Stück |
| **LEVEL / STABILIZE** | Nur die gewählte Seiten- oder Achsstütze | Alle Hub-/Stufentrigger, die für die Nivellierung nicht nötig sind | Eine begrenzte Querneigung, Radabhebung, Park- oder Zugangsstabilität behandeln |
| **STOWED / CRUISE** | Keine | Jeder Pilot, Fühler, Stützarm und Freigabetrigger | Gewöhnliches Fahren, Transport und Lagerung |

Vorn und hinten bleiben Konstruktionsphasen, keine Wahl, die die fahrende Person steuern muss. Sie wählt **ASCEND** einmal; Kontakt, Radposition, Fahrgestellweg, Federungsstellung oder eine Phasenverriegelung führt den Mechanismus vom vorderen Hub zur hinteren Stabilisierung. **DESCEND** wirkt gleich, in umgekehrter Geländereihenfolge. Die fahrende Person darf anhalten oder abbrechen, soll aber nicht entscheiden müssen, wann die Achse wechselt.

Die Modusnamen beschreiben Systemfunktionen, nicht unbedingt getrennte Hardware. Ein Arm kann Auf- und Abstieg bedienen, wenn ein mechanischer Wähler Trigger, Richtung, Verriegelung oder Kurvenbahn ändert. Umgekehrt können Sicherheit oder Packaging getrennte einfache Mechanismen rechtfertigen statt eines hoch konfigurierbaren Gestänges.

### Freigabe und Sperrung

Eine rein mechanische Ausführung könnte einen geschützten Wahlhebel, eine genutete Welle, eine verschiebbare Kurvenplatte, eine Klauenkupplung oder eine seilbetätigte Riegelbank nutzen. Die Wahl von **ASCEND** würde die aufwärts gerichtete Hindernis-Pilotrolle und den geordneten hinteren Folgemechanismus verbinden und gleichzeitig das vollständige Abstiegssystem physisch trennen oder verriegeln. Die Wahl von **DESCEND** würde das Umgekehrte tun. Die Sequenz vorn nach hinten liefe automatisch über Radposition, Fahrgestellweg, Federungszustand oder mechanische Phasenriegel.

Eine elektronisch überwachte Variante soll dasselbe physikalische Prinzip erhalten: Software darf die Auswahl überwachen, aber nicht gewählte Mechanismen bleiben mechanisch verriegelt oder hydraulisch/elektrisch isoliert. Ein einzelner Leitungsfehler oder Softwarezustand darf Auf- und Abstiegsfahrwerk nicht gemeinsam ausbringen.

### Ausbringregeln

- Die Auswahl erfolgt nur im Stand oder unter einer eng begrenzten Crawl-Schwelle bei betätigten Bremsen.
- Der gewählte Richtungsmodus schaltet das vollständige Manöver scharf, gibt aber nur den für die aktuelle Phase nötigen Mechanismus frei.
- Die hintere Phase bleibt verriegelt, bis der erforderliche Vorderradzustand mechanisch oder unabhängig bestätigt ist.
- Unabhängige Links-/Rechts-Ausbringung ist nur zulässig, wo asymmetrische Stütze ausdrücklich validiert wurde; sonst bleiben die Seiten querverkoppelt.
- Abschluss oder Abbruch eines Manövers führt jeden Wähler, Trigger und jede Stütze in einen positiv bestätigten Verstauzustand zurück.
- Cruise-Vortrieb bleibt gesperrt, bis alle Hindernismechanismen verstaut und gehalten sind, ausgenommen das begrenzte Crawl-Tempo-Treten und die legale EPAC-Unterstützung, die in `CRUTCH / CRAWL` zulässig sind.
- Manuelle Bergung muss ein teilweise abgeschlossenes Manöver halten, umkehren oder absenken können, ohne versehentlich die Richtung zu wechseln oder eine Phase zu überspringen.

## Rein mechanischer Kandidat: hindernisausgelöste Pilotrolle

Ein vielversprechender Mechanismus mit minimaler Komplexität ist eine kleine **hängende Pilotrolle** oder ein Hindernisfolger vor den Hauptvorderrädern. Während gewöhnlicher Fahrt ist sie eingefahren oder mechanisch vom Hubgestänge getrennt. Erst nach Wahl von **ASCEND** nimmt sie als erste Phase des vollständigen Aufstiegssystems ihre aktive Hängeposition ein. Trifft das Rad auf die vertikale Stirn eines Bordsteins oder einer Wegstufe, drückt das Hindernis die Pilotrolle relativ zum vorrückenden Fahrgestell nach hinten. Ein Umlenkhebel, Viergelenk, eine Kurvenscheibe, ein Seil, eine Kette oder eine Schubstange wandelt diese Relativbewegung in die Ausbringung eines größeren lasttragenden Auslegerrads.

Die genaue Gestängerichtung ist noch zu entwickeln; die vorgesehene mechanische Logik ist:

```text
NORMAL APPROACH

             Pilotrolle
                 o
                /
     vorn O---/---------------- Fahrgestell
             Ausleger verstaut


PILOT CONTACTS STEP

                       obere Fläche
                   ───────────────────
                 o │
     vorn O-----\│   Pilot wird nach hinten gedrückt
                  │
──────────────────┘ untere Fläche
                    ↘ Gestänge dreht Ausleger


LOAD-TRANSFER POSITION

                       obere Fläche
                   ───────o───────────  ausgebrachte Stütze
                         /
     vorn O------------/------------- Fahrgestell steigt/rückt vor
──────────────────┘ untere Fläche
```

Die Pilotrolle ist der Sensor, das Gestänge der Regler, und die Übertotpunkt-Geometrie oder der Riegel das Schloss. Elektronischer Sensor, Mikrocontroller oder motorischer Aktuator sind nicht zwingend erforderlich.

### Vorläufige Aufstiegsfolge

1. Das Fahrzeug nähert sich langsam und annähernd rechtwinklig dem Hindernis.
2. Die leicht belastete Pilotrolle berührt die vertikale Stirn vor den Hauptvorderrädern.
3. Anhaltende Vorwärtskraft bewegt den Pilotlenker relativ zum Fahrgestell nach hinten oder oben.
4. Die Eingangsbewegung dreht den Auslegerarm über die Kante und hinunter zur oberen Fläche.
5. Der Ausleger erreicht eine lasttragende Stellung und schließt einen Übertotpunkt, eine Ratsche, eine Sperrklinke oder einen positiven mechanischen Riegel.
6. Anhaltende Kraft über den normalen Antriebsstrang belastet den Ausleger. Das Gestänge lenkt einen Teil dieser Kraft in Fahrgestellhub und Entlastung der Vorderachse um.
7. Die Hauptvorderräder rollen über den verringerten wirksamen Höhenunterschied, statt die volle Stufenstirn unter voller Last zu treffen.
8. Sobald die Haupträder die obere Fläche erreichen, löst Federungs- oder Gestängeweg eine kontrollierte Freigabe-, Rücksetz- oder Verstaufolge aus.

Der Mechanismus erzeugt keine Energie und keinen unabhängigen Vortrieb. Die fahrende Person und der normale Pedelec-Antrieb leisten weiterhin die Arbeit, die Fahrzeugmasse anzuheben. Die mechanische Übersetzung tauscht Weg gegen Kraft; sie kann Spitzenreifenkraft und erforderlichen Kraftschluss senken, erhöht aber Gestängeweg, innere Last oder die benötigte Vorwärtskraft bzw. -strecke.

### Zu untersuchende mechanische Elemente

- ein gefederter oder schwerkraftrückstellender Pilotarm, der gewöhnlichen Boden folgt, ohne nennenswerte Fahrzeuglast zu tragen;
- eine einstellbare Eingangshöhe, damit harmlose Oberflächentextur keine Ausbringung auslöst;
- ein Kurven- oder Mehrlenkerverhältnis mit hoher Übersetzung nahe der ersten Lastübertragung;
- ein Dämpfungszylinder, Rotationsdämpfer, Elastomer oder Reibelement gegen stoßgetriebene Schnellausbringung;
- ein Übertotpunktlenker oder positiver Riegel, damit die Stütze unter Last nicht zusammenbricht;
- ein Drehmomentbegrenzer, Sollbruchstift oder nachgiebiges Element für Hindernisse außerhalb der Auslegungshülle;
- ein Freilauf oder eine Ratsche gegen Rückrollen in der Hubphase;
- eine bewusste Rücksetzbedingung, nachdem die Hauptvorderräder sicher auf der oberen Ebene stehen; und
- eine manuelle Freigabe- und Bergungsbedienung, erreichbar ohne Griff in eine Quetschzone.

### Umfang und Grenzen

Dieser erste Mechanismus ist **nur Aufstiegshilfe am Vorderrad**. Er leistet für sich nicht:

- die Stützung des Hinterrads im späteren Teil eines Aufstiegs;
- die Erkennung einer nahenden Abwärtskante;
- die Steuerung eines Abstiegs;
- die Korrektur einer schrägen Anfahrt oder großer Links-/Rechts-Höhenunterschiede; oder
- die Entscheidung, ob die obere Fläche tief, tragfähig oder frei genug ist, das Stützrad aufzunehmen.

Er kann sich auch unbeabsichtigt an Pollern, Wurzeln, Geröll, Wänden, Füßen von Passanten oder Gegenständen auslösen, die dem Zielhindernis ähneln. Die Pilotgeometrie muss kleine Stöße und gewöhnliche Rauheit ablehnen, und die fahrende Person braucht eine Möglichkeit, das System außerhalb des gewählten Laufwerk-Modus zu deaktivieren oder mechanisch zu sichern.

### Verwandte rein mechanische Mechanismen

Dieselbe Entwurfsphilosophie kann andere Phasen stützen, aber jede braucht ihre eigene Triggergeometrie:

- **Aufstiegsstabilisierung am Hinterrad:** Vorderradposition, Fahrgestellverschiebung oder ein nachlaufender Folger könnten eine hintere Stütze mechanisch erst freigeben, nachdem die Vorderachse auf der oberen Ebene steht. Das hintere Fahrwerk würde abstützen und das Hinterrad beim Steigen entlasten.
- **Abstiegsvorbereitung:** Ein vorderer Fallfühler könnte über eine Kante fallen und einen Stützarm freigeben, der die untere Fläche erreicht, bevor das Hauptrad überquert. Das ist sicherheitskritischer als der Aufstieg, weil die Erkennung zu spät kommen kann, wenn der Fühler nicht weit genug vorausragt.
- **Abstiegsstabilisierung am Hinterrad:** Ein mechanisch sequenzierter Nachlaufarm könnte lasttragend bleiben, bis das Hinterrad die untere Ebene erreicht, und so einen plötzlichen hinteren Fall oder Nickwechsel verhindern.
- **Links-/Rechts-Ausgleich:** Gepaarte Mechanismen könnten für symmetrische Ausbringung mechanisch querverkoppelt sein oder über einen Ausgleichsbalken begrenzte Differenzbewegung zulassen. Vollständig unabhängige passive Seiten könnten gefährliche Verwindung erzeugen, wenn nur eine auslöst.

Diese Mechanismen sollten bewertet werden, bevor angenommen wird, dass jedes Stützrad einen Aktuator braucht. Ein Hybrid kann am Ende am einfachsten sein: passive hindernisausgelöste Ausbringung und mechanische Verriegelung, mit einem kleinen motorischen oder manuellen Mechanismus nur für Rücksetzen, Verstauen oder kontrollierte Freigabe.

## Ausfahrbare „Krücken“-Konzepte

Diese Familie ist **Alternative 2**: von der fahrenden Person bediente Krücken oder synchronisierte Kurvenräder. **Crawl** ist ein eigener Laufwerk-Modus. Herkömmliches Lenken, Bremsen und Rudern werden nicht gleichzeitig mit der Krückenarbeit genutzt. Die Krücken werden analog zu Skistöcken geführt. Treten darf im Crawl-Tempo mit maximaler Unterstützung innerhalb der bestehenden 250-W-EPAC-Hülle fortgesetzt werden.

Das einfachste Krückenkonzept steuert die fahrende Person unabhängig mit den Händen. Eine stärker synchronisierte Alternative nutzt ausfahrbare **exzentrische Kurvenräder** oder drehende Arme mit Rollenende. In beiden Fällen setzen die vorübergehenden Krücken wiederholt auf, nehmen Last auf, heben oder verschieben das Fahrgestell durch einen kleinen kontrollierten Bogen, entlasten und kehren für den nächsten Zyklus zurück.

Die entstehende Bewegung liegt näher am Gehen mit Krücken als am gewöhnlichen Rollen:

```text
1. AUFSETZEN            2. HEBEN / VORSCHUB        3. ÜBERTRAGEN

       Fahrgestell             Fahrgestell              Fahrgestell
    O-----------O           O-----------O            O-----------O
        \   /                    |   /                    \   |
         o o                     o  o                      o  o
       Krücken              Kurvenscheibe unter Last  Last wechselt Seite/Phase
```

Mögliche Ausführungen sind:

- ein rundes Rad auf exzentrischer Achse mit vorhersehbarem Hub-Senk-Zyklus;
- ein geformtes Kurvenrad, dessen wirksamer Radius über eine Umdrehung wechselt;
- ein Dreharm mit kleiner frei laufender Rolle am Ende;
- gepaarte Kurvenscheiben, 180 Grad phasenversetzt, sodass eine lasttragend bleibt, während die andere zurücksetzt; oder
- vordere und hintere Kurvenpaare, über Welle, Kette, Zahnriemen oder indiziertes Gestänge gekoppelt, um die Phasenlage zu halten.

Die Geometrie soll eine **langsame, ruhige, quasistatische** Fahrgestellbahn anstreben, keinen hüpfenden oder ruckenden Gang. Mehrere kleinere Kurvenlappen, nachgiebige Reifen, Dämpfer, Federungskoordination oder überlappende Stützphasen können die vertikale Beschleunigung senken und verhindern, dass die fahrende Person jede Stützübertragung spürt.

### Von der fahrenden Person bediente Krückenvariante

Die einfachste Version kann auf synchronisierte Nockenwellen und automatischen Takt ganz verzichten. Ein linker und ein rechter Krückenarm könnten jeweils in einem kleinen Rad oder einer Rolle enden und mechanisch mit einem Handhebel neben der fahrenden Person verbunden sein. Sie bringt jede Seite aus, setzt auf, schwenkt, belastet, entlastet und holt zurück, ähnlich wie eine Person echte Krücken koordiniert.

In dieser Version:

- **steuern die Hände Stützplatzierung und Schwenken**;
- **können Arme und Oberkörper über Hebelübersetzung Hub- oder Stützkraft beitragen**;
- **treten die Füße weiter**, um Vorwärtsbewegung im Crawl-Tempo zu liefern;
- darf der normale Pedelec-Antrieb in diesem Crawl-Tempo maximale Unterstützung innerhalb der bestehenden 250-W-EPAC-Hülle liefern; und
- braucht keine Krücke einen eigenen Traktionsmotor, Geländerechner oder automatischen Gangregler.

Ein möglicher Crawl-Rhythmus ist:

1. Anhalten oder auf das validierte Crawl-Tempo reduzieren und `CRUTCH / CRAWL` wählen.
2. Die linke Krücke über ihren Handhebel lösen und senken; bestätigen, dass die Rolle aufgesetzt und Schwenk- oder Lastriegel geschlossen sind.
3. Eine kurze Strecke treten und dabei die linke Krücke zum Abstützen, Heben oder Steuern der Fahrgestelllage nutzen.
4. Die rechte Krücke aufsetzen, bevor die linke das Ende ihres sicheren Stützbogens erreicht.
5. Die Stütze allmählich auf die rechte Seite übertragen, die linke entlasten und umsetzen und so abwechselnd fortfahren, solange nötig.
6. Sobald alle Primärräder hinter dem schwierigen Stück zuverlässigen Kontakt haben, beide Krücken entlasten, falten und positiv verriegeln, bevor der Crawl-Modus verlassen wird.

Die beiden Seiten sollen unabhängig bedienbar sein, damit die fahrende Person auf unterschiedliche Links-/Rechts-Bodenhöhen reagieren kann. Unabhängigkeit heißt nicht unbeschränkte Bewegung: jeder Arm braucht stabile Aufsetzstellungen, Wegbegrenzungen, Überlastschutz und eine Sicherung gegen plötzliches Einknicken oder unkontrolliertes Schwingen.

### Mensch-Maschine-Schnittstelle

Kandidatenbedienungen sind lange direkte Hebel, kompakte Hebel über Seile oder Schubstangen, Ratschengriffe oder abnehmbare Krückengriffe, die neben dem Sitz andocken. Die Hebelgeometrie könnte nahe dem lasttragenden Hubabschnitt hohe Übersetzung und im entlasteten Rücklauf schnelleren Weg bieten.

Die fahrende Person soll:

- Bodenkontakt und steigende Krückenlast über die Bedienung spüren, nicht nur über eine Anzeige;
- eine aufgesetzte Krücke verriegeln oder halten können, ohne die volle Fahrzeuglast dauernd mit Armkraft zu tragen;
- eine Seite bedienen, während die andere sicher aufgesetzt bleibt;
- Last bewusst lösen, ohne Schnappen, Fallen oder Griffschlag;
- die Folge abbrechen und das Fahrzeug mechanisch gestützt hinterlassen können; und
- beide Griffe und Arme außerhalb der Hüllen für Lenkung, Treten, Umstieg und Straßenbodenfreiheit verstauen.

Lenken und Bremsen bleiben erforderliche Fahrzeugfunktionen, laufen aber nicht gleichzeitig mit der Krückenarbeit. Crawl ersetzt den Cruise-Bediensatz: die Hände führen die Krücken analog zu Skistöcken, die Füße treten im Crawl-Tempo, herkömmliches Lenken und Rudern entfallen. Ein eigenes Halt-, Festhalte- und Abbruchverfahren im Crawl-Modus bleibt nötig; diese Seite macht „kein Bremsen“ nicht zur Anforderung. Kandidaten für Halt/Festhalten sind eine vor dem Crawl bereits betätigte Feststellbremse, ein fußerreichbares Halten oder eine andere Bedienung, die nicht beide Hände von den Krücken zurückholt.

### Warum manuelle Bedienung vorteilhaft sein kann

- Die fahrende Person wählt Platzierung und Zeitpunkt direkt, statt unvollkommener Geländeerkennung zu vertrauen, analog zum Setzen von Skistöcken.
- Jede Seite kann unabhängig auf die tatsächliche Fläche reagieren.
- Der Mechanismus kann überwiegend aus Hebeln, Drehpunkten, Seilen, Riegeln, Federn und kleinen Rollen bestehen.
- Das Fehlerverhalten ist sichtbar und tastbar.
- Menschliche Armeingabe ist leicht von einem verborgenen autonomen Traktionssystem zu unterscheiden.
- Die Entwicklung kann mit einem statischen Prüfstand beginnen, bevor automatische Funktionen hinzukommen.

Der Kompromiss ist körperliche und kognitive Belastung. Krückenkräfte, Griffweg, Koordination, Reichweite, Griffkraft, Schulterlast, Ermüdung und die Fähigkeit, gleichzeitig zu treten, müssen gemessen, nicht angenommen werden. Der Mechanismus soll Kraft verstärken und halten; er soll nicht erwarten, dass die Arme das volle besetzte Fahrzeug dauernd tragen.

### Vorgesehene Nutzung

`CRUTCH / CRAWL` ist eine besondere Bergungs- und Geländefunktion für ein kurzes Stück, das sonst unpassierbar wäre, etwa tiefe Spurrillen, versetzte Steine, einen gebrochenen Wegübergang, ein schmales Erosionsstück oder eine Folge kleiner Diskontinuitäten, die nicht als ein ASCEND- oder DESCEND-Ereignis behandelbar sind.

Es ist nicht:

- ein normaler Federungsmodus;
- ein Hochgeschwindigkeits-Geländesystem;
- für gewöhnliche Straßen- oder Radwegfahrt vorgesehen;
- ein Ersatz für Streckenurteil; oder
- die Erlaubnis, Treppen, lose Hänge oder Gelände außerhalb einer validierten Hülle zu versuchen.

Das Fahrzeug muss vor der Ausbringung anhalten. Ein geschützter Moduswähler gibt dann das Krückenfahrwerk mechanisch frei und erzwingt gleichzeitig eine sehr niedrige Übersetzung oder Crawl-Temposchwelle. Treten in diesem Crawl-Tempo darf maximale Unterstützung innerhalb der bestehenden 250-W-EPAC-Hülle nutzen; das ist kein Gasgriff, kein zweites Traktionssystem und keine höhere Leistungsklasse. Die Rückkehr zu Cruise erfordert vollständiges Einziehen, positive Halterung und Bestätigung, dass jede manuelle Krücke und jeder Kurvenmechanismus vom Antriebsstrang und von der Bedienungshülle getrennt sind.

### Energie- und Vortriebsgrenze

Sowohl manuelle Krücken als auch ein Kurvenmechanismus brauchen Arbeit, um das besetzte Fahrzeug zu heben und zu versetzen. In der manuellen Version setzen und schwenken die Arme die Stützen, während die Füße das Fahrzeug vorwärts treten. In einer Kurvenversion kann der Taktmechanismus mechanisch über eine sehr niedrige Untersetzung, Kupplung und Drehmomentbegrenzer an den normalen Muskelkraftantrieb gekoppelt sein. Die Eingabe der fahrenden Person—und nur die rechtlich zulässige Pedelec-Unterstützung, wo sie gilt—liefert die Energie.

Die Kurvenscheiben können beim Drehen gegen den Boden Längsreaktionskräfte erzeugen; ihre funktionale Wirkung braucht daher sorgfältige Einstufung. Ein separat angetriebener Kurvenantrieb, der das Fahrzeug ohne qualifizierende Muskeleingabe vorwärts gehen lässt, könnte unabhängig davon, ob die Kontaktelemente Krücken, Stützen oder Fahrwerk heißen, zu einem eigenständigen Vortriebssystem werden. Beurteilt werden muss, was der Entwurf tut, nicht wie er heißt.

### Ausbringung und Phasenlage

- Krückenelemente bleiben in Access und Cruise innerhalb der Straßenhülle gefaltet und mechanisch getrennt.
- Ausbringung darf nur im Stand, gebremst und in der passenden Fahrgestellgeometrie mit hoher Bodenfreiheit erfolgen.
- Während eines Zyklus sollen mindestens drei stabile Bodenkontakte—oder ein gleichwertig nachgewiesenes Stützpolygon—erhalten bleiben.
- Links-/Rechts- und Vorder-/Hinter-Kurvenphasen müssen gleichzeitigen Stützverlust verhindern und Fahrgestellverwindung begrenzen.
- Ein mechanischer Index, ein Malteserkreuz, eine genutete Welle oder ein positiver Taktantrieb soll die Phasenlage nach Stoß oder teilweiser Umkehr erhalten.
- Das System muss nach Verlust von Eingabe, Strom oder Steuersignal in einer statisch tragfähigen Phase stehen bleiben.
- Rückwärts oder Rückzug braucht eine bewusste Folge; bloßes Zurückdrehen der Kurvenscheibe kann einen Riegel lösen oder eine instabile Phase betreten.
- Einziehen soll nur aus einer definierten Grundphase möglich sein, in der jedes Hauptrad als lastfähig bestätigt ist.

### Wesentliche Risiken

- oszillierende Lasten auf die fahrende Person, Bewegungsübelkeit, Druckspitzen oder Rückhaltlasten;
- sehr hohe Kontaktspannung an kleiner Krückenrolle oder Kurvenlappen;
- Rutschen, wenn ein aufgesetztes Element vertikale und horizontale Reaktionskraft erzeugt;
- Phasenverlust oder Spiel zwischen mechanisch gekoppelten Einheiten;
- Einklemmen von Steinen, Wurzeln, Kleidung oder Körperteilen in der Drehhülle;
- strukturelle Ermüdung durch wiederholte Hubzyklen;
- der Mechanismus wird zum Stabhochsprung-Drehpunkt, wenn er unerwartet hakt;
- kein herkömmliches Lenken, während die Krücken nennenswerte Last tragen, daher muss die Crawl-Bahn vor dem Eintritt ausgerichtet sein; und
- unklare rechtliche Behandlung, wenn Kurvendrehung Netto-Vorwärtsfahrt beiträgt.

Das Konzept sollte zunächst als quasistatisches Gestänge modelliert und mit Ballast auf einem festgehaltenen Prüfstand getestet werden. Glätte, Stützpolygon, Kontaktkräfte und sichere Haltephase zählen mehr als erreichbares Crawl-Tempo.

## Hindernisüberwindungsfolge

Die folgenden Folgen beschreiben die erforderlichen Fahrzeugzustände, nicht eine verpflichtende Aktuatorarchitektur. Ein passives Gestänge kann mehrere Schritte mechanisch verbinden; eine unterstützte Version kann sie unter Mikrocontroller-Aufsicht ausführen. Beides sind Hypothesen für Simulation und energiearme Prototypentests.

### Aufstieg

1. Ein Hindernis erkennen oder festlegen und in validiertem Anfahrabstand anhalten.
2. Niedrige Geschwindigkeit, zulässigen Lenkwinkel, Flächengeometrie, verfügbaren Freigang, Aktuatorzustand und ausreichende Kraftschluss-/Bremsreserve bestätigen.
3. Von Cruise zur Urban-Geometrie transformieren: übermäßigen Radstand bei Bedarf verkürzen, Bodenfreiheit erhöhen, die fahrende Person in die validierte Haltung bringen und den Sitz nivellieren.
4. Die vorderen Stützräder auf die obere Fläche oder einen anderen nachgewiesenen lasttragenden Kontaktpunkt ausbringen.
5. Kontakt und mechanische Verriegelung nachweisen, bevor wesentliche Last übertragen wird.
6. Einen Teil der Vorderlast in das ausgebrachte Fahrwerk verlagern, das Nickmoment senken und das Hauptrad soweit nötig entlasten.
7. Mit dem normalen Muskel-/Pedelec-Antrieb vorrücken, während die Stützräder rollen und stabilisieren; die Stützarme koordinieren die Höhe, treiben das Fahrzeug aber nicht selbstständig vorwärts.
8. Die Hauptvorderräder auf die obere Ebene bringen und ihre kontrollierte Federungslast wiederherstellen.
9. Falls der hintere Übergang es erfordert, hintere Stützräder ausbringen oder umsetzen, bevor das Hinterrad die Kante überquert.
10. Das Hinterrad auf die obere Ebene bringen, stabilen Hauptradkontakt prüfen, das Stützfahrwerk entlasten und einziehen, dann je nach Lage in Access oder Cruise zurückkehren.

### Abstieg

1. Vor der Kante anhalten und Absatz, Landefläche, Ausrichtung, Freigang und Bremsreserve prüfen.
2. Nach Urban transformieren und den gewählten Laufwerk-Modus scharfschalten. Die erforderliche Geometrie mit hoher Bodenfreiheit, kompakter Länge und nivelliertem Sitz herstellen.
3. Das vordere Fahrwerk auf die untere Fläche ausfahren und lasttragenden Kontakt und Verriegelung nachweisen.
4. Last allmählich auf die Stützräder übertragen, bevor ein Hauptvorderrad die obere Ebene verlässt.
5. Unter kontrolliertem Bremsen vorrollen und das Fahrgestell so senken, dass die Hauptvorderräder die untere Ebene ohne freien Fall erreichen.
6. Die Last der Hauptvorderräder wiederherstellen, dann den hinteren Teil mit dem hinteren Fahrwerk stützen und senken, falls die Geometrie es verlangt.
7. Bestätigen, dass alle Primärräder belastet und stabil sind, bevor das Fahrwerk eingezogen wird.

Absteigen ist als primärer Sicherheitsfall zu behandeln, weil Schwerkraft, Bremsen und Vorwärtsnicken zusammenwirken können, auch wenn wenig Vortrieb nötig ist.

## Einbindung in das transformierbare Fahrgestell

**Adaptives Fahrwerk** fügt keine dritte Fahrgestellfamilie hinzu. Das [Referenzfahrzeug](reference-vehicle_DE.md#42-betriebsarten) behält Access, Urban und Cruise. Wird diese spätere Option verfolgt, nutzen die Laufwerk-Funktionen die **Urban**-Geometrie (kompakter oder mittlerer Radstand, erhöhte Bodenfreiheit, Sitz in sicherer Lage gehalten). **Crawl** ist ein Laufwerk-Modus in dieser Geometrie, kein Ersatz für Urban.

| Fahrgestellmodus | Richtgeometrie | Fahrwerkzustand | Zweck |
| --- | --- | --- | --- |
| **Access** | Kurz, hoch, aufrecht, offener Umstiegspfad | Eingezogen, oder ein getrennt validierter Parkstabilisator, falls diese Funktion Hardware teilt | Ein-/Ausstieg, Beladen, Parken und Zugang für Unterstützende |
| **Urban** | Kompakter oder mittlerer Radstand, erhöhte Bodenfreiheit | Wirtsgeometrie für spätere Laufwerk-Modi; verstaut, bis ein Laufwerk-Modus scharfgeschaltet ist | Heute Langsammanöver; später Wirt für begrenzte Hindernisarbeit |
| **Cruise** | Lang, niedrig, geneigt, aerodynamisch effizient | Vollständig eingezogen und positiv gehalten | Gewöhnliche Straßen- und Radwegfahrt |

| Laufwerk-Modus (spätere Option) | Freigegeben aus | Vorgesehene Funktion |
| --- | --- | --- |
| **STOWED / CRUISE** | Jeder verriegelte Fahrgestellmodus | Gewöhnliches Fahren; jeder Pilot, Fühler, Stützarm und Freigabetrigger gesperrt |
| **ASCEND** | Urban | Vollständiges Aufstiegssystem; Abstiegsfahrwerk gesperrt |
| **DESCEND** | Urban | Vollständiges Abstiegssystem; Aufstiegstrigger gesperrt |
| **CRUTCH / CRAWL** | Urban | Eigener Langsammodus: Krücken oder Kurvenzyklus; herkömmliches Lenken, Bremsen und Rudern nicht gleichzeitig; Crawl-Tempo-Treten mit maximaler legaler EPAC-Unterstützung |
| **LEVEL / STABILIZE** | Urban, oder Access, falls eine gemeinsame Parkstabilisierung später validiert wird | Gewählte Seiten- oder Achsstütze ohne Aufstiegs- oder Abstiegsfolge |

Übergänge müssen sequenziert sein. Die Fahrwerkausbringung darf nicht aus einer unverträglichen Cruise-Geometrie beginnen, Auf- und Abstiegsfunktionen müssen gegenseitig gesperrt bleiben, und das Fahrzeug darf nicht in Cruise beschleunigen, bis jede Stütze eingezogen oder in einem getrennt validierten Zustand ist. Diese Sequenzierung kann über mechanische Wähler und Riegel, eine einfache Steuerung oder beides erfolgen; sie darf nicht von mehrdeutiger Deutung eines generischen Hindernis-Modus durch die fahrende Person abhängen.

## Verhältnis zur Federung

Das Fahrwerk ergänzt die [primäre Federung](../engineering/suspension_DE.md), ersetzt sie nicht.

- Die **Federung** verwaltet kontinuierliche Oberflächenvariation, Reifenkontakt, Komfort, Dämpfung, Wankverhalten und Fahrverhalten.
- **Adaptives Fahrwerk** schafft vorübergehende Kontaktpunkte und Stützgeometrie, wenn gewöhnlicher Radfederweg die Diskontinuität nicht sicher überspannen kann.

Im Hindernis-Modus sind Federungsstellung und Radlast nützliche Steuereingänge. Das System darf Feder-/Dämpfereinstellungen, Querverbindung, Fahrhöhe oder Wankverhalten vorübergehend ändern, aber die Federung darf den Fahrwerkaktuator nicht bekämpfen oder gespeicherte Energie während der Lastübertragung unerwartet freisetzen.

Wesentliche Integrationsrisiken sind Fahrgestell-Aufbocken, Radabhebung, Bump-Steer, plötzliche Wankzentrumsbewegung, Federungsanschlag oben oder unten, hohe lokale Reifenlasten, Lastteilung der Aktuatoren und instabile Regelkreise, in denen aktive Federung und Gelenkstützen beide den Aufbau nivellieren wollen.

## Lastübertragung gegenüber Vortrieb

Das vorgesehene Prinzip ist:

> Die Gelenkstützen verwalten Last und Stabilität; sie bilden kein unabhängiges Vortriebssystem.

Das Stützsystem darf elektrische Energie zum Ausbringen, Einziehen, Heben, Senken, Verriegeln, Nivellieren oder Regeln der Kontaktkraft verbrauchen. Ein Stützrad darf rollen, während der primäre Antriebsstrang das Fahrzeug vorschiebt. Das unterscheidet sich funktional vom Aufbringen von Radmoment, das unabhängige Netto-Vorwärtsfahrt erzeugt.

Vorwärtsbewegung soll dem normalen mechanischen Muskelkraftantrieb und, wo zulässig, seiner rechtskonformen Pedelec-Unterstützung zurechenbar bleiben. Das Fahrwerk soll keinen verborgenen Gasgriff, Kriechantrieb oder zweites Traktionssystem liefern. Jede Bremse oder Rückrollsicherung an einem Stützrad soll als Sicherheitsfunktion ausgelegt sein, nicht um das Fahrzeug vorwärts zu ratschen.

Diese Unterscheidung ist ein Entwurf- und Dokumentationsziel, keine geklärte rechtliche Schlussfolgerung. Behörden können das vollständige Fahrzeug und die funktionale Wirkung motorischer Aktuatoren beurteilen, nicht nur die vergebenen Namen. Jeder Modus muss in die Einstufungsprüfung einbezogen werden; siehe die [Einstufungsmatrix](../regulatory/classification_DE.md), die [deutsche Forschung](../regulatory/germany_DE.md) und den [EU-Kontext](../regulatory/eu_DE.md).

## Sensorik und Steuerung mit minimaler Komplexität

Die Entwurfshierarchie ist:

1. **Mechanische Geometrie:** Folger, Kurvenscheiben, Lenker, Federn, Dämpfer, Riegel, Festanschläge und Übertotpunkt-Verriegelungen nutzen, damit die sichere Aktion aus Hinderniskontakt und Fahrgestellbewegung entsteht.
2. **Mechanische Verriegelungen und Bedienung:** Moduswähler, manuelle Freigaben, Bremsen-Interlocks und sichtbare Zustandsanzeige hinzufügen, ohne Rechnung zu verlangen.
3. **Einfache elektronische Aufsicht, wo gerechtfertigt:** Mikrocontroller und skalare Sensoren nur für Tatsachen oder Folgen nutzen, die mechanisch nicht hinreichend sicher und zuverlässig zu machen sind.
4. **Komplexe Wahrnehmung:** Lidar, Computer Vision, 3-D-Kartierung und autonome Geländeplanung bleiben außerhalb der Basis.

Falls Elektronik nötig ist, bleibt die Basis eine **begrenzte elektromechanische Folge**, kein autonomer Geländeroboter. Die fahrende Person hält an, richtet das Fahrzeug aus, fordert den gewählten Laufwerk-Modus an und bleibt dafür verantwortlich, das Manöver anzunehmen. Ein kleines Mikrocontrollersystem prüft einfache Messgrößen, erzwingt Interlocks und führt den Mechanismus durch bekannte Zustände.

Die bevorzugte Elektronikarchitektur, falls genutzt, ist ein sicherheitsorientierter Aufsichts-Mikrocontroller, mit zusätzlichen kleinen lokalen Mikrocontrollern nur, wenn Verkabelung oder Aktuatorsteuerung sie rechtfertigen. Sie soll weder GPU noch allgemeines Betriebssystem, Netzwerkverbindung, Cloud-Verarbeitung, simultane Lokalisierung und Kartierung oder ein fortlaufend rekonstruiertes 3-D-Modell brauchen.

### Kandidatensensoren

- Radimpuls, Lenkwinkelbereich, Bremszustand und Null-/Niedriggeschwindigkeitsbestätigung;
- ein einfacher Inertialsensor für Nick- und Wanklage des Fahrgestells;
- Endschalter, Hall-Sensoren oder kostengünstige Encoder für Aktuator- und Federungsstellung;
- Aktuatorstrom zur Ableitung von Blockade, Überlast und Kontakt;
- kurzreichweitige Ultraschall-/Sonar- oder Time-of-Flight-Sensoren nach vorn und unten zur Schätzung von Kantenabstand, Steigungs-/Absatzhöhe und Landefreigang;
- einfache Kontaktschalter oder Lastschwellensensoren an Stützrädern, wo Motorstrom als Beleg nicht ausreicht;
- positive Bestätigung der mechanischen Verriegelung; und
- Anwesenheit der fahrenden Person, Rückhalt, Zugangsöffnung, Not-Halt und Modusbefehle, wo erforderlich.

Der Sensorsatz soll weiter reduziert werden, wenn mechanische Geometrie einen Zustand selbstverständlich macht. Zum Beispiel können ein Festanschlag plus unabhängig erfasste Verriegelung sicherer und einfacher sein als fortlaufende Gelenkwinkelschätzung. Redundante Sensorik soll nur für sicherheitskritische Tatsachen hinzukommen, nicht um ein reicheres Geländemodell zu bauen.

### Automatisierungsstufen

1. **Manueller Befehl mit harten Interlocks:** die fahrende Person fordert jede Phase an; die Steuerung lässt nur sichere Aktionen zu.
2. **Unterstützte Folge:** die fahrende Person autorisiert den gewählten Laufwerk-Modus, und das System führt eine überwachte Ausbringfolge mit Pause-/Abbruchbedienung aus.
3. **Begrenzte automatische Positionierung:** nach Autorisierung stoppen einfache Abstands- und Kontaktmessungen jeden Arm an der erforderlichen Stellung und prüfen, dass der nächste Lastübertragungsschritt zulässig ist.

Die Basis erkennt allgemeines Gelände nicht automatisch und bringt während Cruise nicht aus. Automatisches Verhalten darf die fahrende Person nie überraschen, indem es Spur, Radstand, Höhe oder Stützkräfte ändert. Bei widersprüchlichen, abgelaufenen oder außerhalb der validierten Hülle liegenden Abstandsmessungen hält die Steuerung an und fordert manuelle Bergung an, statt die Szene zu interpretieren.

## Technik-Vorbild: Unitree B2-W

Diese Familie ist **Alternative 3**, als vergleichende Architekturehre geführt, nicht als nachzubauender Kandidat. Der [Unitree B2-W](https://www.unitree.com/b2-w/) ist ein nützliches Technik-Vorbild für **Adaptives Fahrwerk**. Er ist **kein** direktes Fahrzeugkonzept, kein regulatorisches Vorbild und kein Beleg, dass dieselben Manöver mit einer fahrenden Person sicher sind. Er ist ein vollständig maschinengetriebener industrieller Vierbeiner-Roboter, dessen vier angetriebene Räder an den Enden mehrgelenkiger Beine sitzen. Dennoch zeigt er, wie rollende Räder, Gelenkglieder, Wahrnehmung und schnelle Lastumverteilung auf einer mobilen Plattform kombiniert werden können.

Unitree beschreibt den B2-W so, dass Wahrnehmung und Bewegungssteuerung zusammenwirken, um das Gleichgewicht über Treppen, Hänge, Barrieren, Gras, Stein und Schotter zu halten. Die Produktangaben führen grobflächige Stabilität auf schnelle, koordinierte Reaktionen über mehrere Beingelenke zurück. Veröffentlichte Zahlen umfassen etwa 85 kg Gesamtmasse, 225 mm Raddurchmesser, 120 kg Standnutzlast, über 40 kg Gehnutzlast, Dauerfahrt über 20–25 cm Treppen, Vorwärtsauf- oder -abstieg einer 40-cm-Stufe und Hänge über 45 Grad. Unitree weist darauf hin, dass Fähigkeiten nach Konfiguration und Anwendung variieren und einige Funktionen menschliche Bedienung oder Weiterentwicklung brauchen. Diese Herstellerangaben sind Beispiele der behaupteten Plattformhülle, keine Entwurfsziele dieses Vorhabens.

Die zugehörige B2-Plattformdokumentation nennt konfigurierbares 3-D-Lidar, Tiefenkameras, optische Kameras und erhebliche Bordrechnung, während Unitrees B2/B2-W-Anwendungsdokumentation Laserkartierung und autonome Navigation beschreibt. Diese Systeme helfen, die breite Autonomie des Roboters zu erklären, liegen aber bewusst **außerhalb des Basisumfangs** von **Adaptives Fahrwerk**. Dieses Vorhaben nimmt Anregung aus der Artikulations- und Lastverwaltungsarchitektur, nicht aus dem B2-W-Sensorstapel.

### Was das Beispiel zeigt

- **Ein Rad muss nicht an einer festen Fahrgestellkoordinate sitzen.** Ein mehrgelenkiger Träger kann Radhöhe, Längs- und Querplatzierung sowie Kontaktkraft steuern, während das Rad weiterrollt.
- **Rollwirkungsgrad und Hindernisartikulation können zusammenbestehen.** Räder leisten effiziente Dauerfahrt; Gelenke leisten diskretes Gelände und Aufbauhaltung.
- **Die nützliche Steuergröße ist nicht nur die Gelenkstellung.** Koordinierte Steuerung muss Nick- und Wanklage, Radkontakt, Lastverteilung, Geländegeometrie, Geschwindigkeit und den nächsten vorgesehenen Kontaktpunkt berücksichtigen.
- **Vier unabhängig artikulierte Kontaktpunkte können das Stützpolygon umformen.** Ein Rad kann steigen, greifen, entlasten oder umsetzen, während die übrigen Kontakte den Aufbau stabilisieren.
- **Geländefähigkeit entsteht aus dem Gesamtsystem.** Geometrie, einfache Messungen, mechanische Artikulation, kontrollierte Sequenzierung und Fehlerbehandlung wirken zusammen; ein gelenkiger Ausleger allein schafft keine vergleichbare Fähigkeit.

### Übertragung auf das Adaptive-Fahrwerk-Konzept

| B2-W-Merkmal | Relevante Lehre | Bewusste Projektgrenze |
| --- | --- | --- |
| Vier radendige Gelenkbeine | Jeder Bodenkontakt kann unabhängig platziert und belastet werden | Mit einer kleineren Zahl ausfahrbarer Stützarme beginnen; unnötige Freiheitsgrade vermeiden |
| Angetriebene Räder an jedem Bein | Ein Rad kann weiterrollen, während sein Träger die Geometrie ändert | Der rechtliche Hauptantrieb liefert Vorwärtsbewegung; Stützräder werden kein unabhängiges Traktionssystem |
| Dynamische Aufbaustabilisierung | Artikulation koordinieren, um Nicken, Wanken, Bodenfreiheit und Kontaktkraft zu steuern | Bewegungen des besetzten Fahrzeugs müssen langsamer, begrenzt, vorhersehbar und mechanisch gesichert sein |
| Wahrnehmung an Bewegungssteuerung gekoppelt | Gemessener Freigang, Höhe, Lage und Kontakt können die nächste Aktion steuern | Sonar/Time-of-Flight, Stellung, Strom, Kontakt und Neigung nutzen, nicht Lidar oder 3-D-Szenenrekonstruktion |
| Hochbandbreitige motorische Gelenke | Schnelle Lastumverteilung ermöglicht schwierige Geländemanöver | Quasistatische Lastübertragung und positive Verriegelungen gegenüber dauernder Abhängigkeit von Aktuatormoment bevorzugen |
| Rad-Bein-Geometrie | Roll- und Schrittverhalten können eine Strukturarchitektur teilen | Auf eine kurze Zweistufenfolge und begrenzte Weghindernisse auslegen, nicht auf allgemeine Vierbeinerlokomotion oder Treppensteigen |

### Wesentliche Unterschiede

Die Räder des B2-W sind aktive Vortriebsgeräte, und seine Beine tragen dauernd einen unbesetzten Roboter. **Adaptives Fahrwerk** ist für ein besetztes Fahrrad gedacht, dessen Stützarme vor allem stabilisieren und Last übertragen. Das Vorhaben kann daher ein Roboterbein nicht einfach skalieren oder sein Regelverhalten kopieren.

Ein besetztes Fahrzeug muss Verletzungstoleranz, Komfort, Rückhalt, Notausstieg, Nähe zur Öffentlichkeit, redundantes Bremsen, mechanische Verriegelung, beherrschbares Stromausfallverhalten und einen deutlich weniger nachgiebigen Rechtsrahmen berücksichtigen. Dynamische Bergungsmanöver, die für einen Roboter akzeptabel sind—Springen, schnelle Aufbau-Beschleunigung, Radschlupf, momentan instabile Zustände oder Auffangen durch Sich-selbst-Fangen—können für eine Plattform mit fahrender Person unzulässig sein.

Die wertvollste B2-W-Lehre ist daher architektonisch, nicht wörtlich:

> Eine vierrädrige Plattform kann Radposition und Radlast als adaptive Größen behandeln, nicht als feste Eigenschaften des Fahrgestells.

Für dieses Vorhaben soll diese Idee in langsame, ausfallsichere Hindernisüberwindung übersetzt werden: die fahrende Person erkennt die Diskontinuität und richtet sich darauf aus; einfache Sensoren prüfen Höhe, Freigang, Lage und Kontakt; die Steuerung verriegelt das Gelenkfahrwerk, überträgt Last, erlaubt Vorschub über den normalen Antriebsstrang und stellt die Straßenkonfiguration wieder her.

### Fragen aus dem B2-W-Beispiel

- Könnte Vierrad-Artikulation getrennte Rollen von „Hauptrad“ und „Ausleger“ ersetzen, oder würde das den Straßenbetrieb zu schwer und komplex machen?
- Wie viele aktiv gesteuerte Freiheitsgrade sind mindestens nötig, um den Großteil des nützlichen Nivellier- und Kontaktplatzierungsverhaltens zu erreichen?
- Können quasistatische Steuerung und mechanische Verriegelungen die nötige Fähigkeit ohne roboterartige Aktuatorbandbreite und Energieverbrauch liefern?
- Welche Mindest-Zustandsgrößen—Aufbaulage, Aktuatorstellung/-strom, Stützkontakt, Radbewegung und eindimensionaler Abstand/Höhe—sind für einen ersten sicheren Prototyp wesentlich?
- Können feste Sensorplatzierung und bekannte Gestängegeometrie die Hindernismessung auf wenige Abstände statt einer Geländekarte reduzieren?
- Wie soll ein besetztes Fahrzeug entscheiden, dass ein Hindernis außerhalb seiner Hülle liegt, und einen sicheren Rückzug anbieten statt dynamischer Bergung zu versuchen?
- Kann das transformierbare Fahrgestell den Großteil der groben Höhen- und Radstandsänderung liefern und dem Fahrwerk nur die endgültige Kontaktplatzierung überlassen?

### Quellenhinweis

Herstellerangaben geprüft am 2026-08-28: [Unitree-B2-W-Produktseite](https://www.unitree.com/b2-w/), [Unitree-B2-Plattform und Sensorkonfigurationen](https://www.unitree.com/b2/) und [Unitree-Explore-Anwendungsdokumentation](https://www.unitree.com/app/b2/). Hersteller-Leistungsangaben brauchen unabhängige Prüfung, bevor sie als Konstruktionsbeleg dienen.

## Sicherheitssysteme und mechanische Verriegelung

- Positive mechanische Verriegelungen in jedem lasttragenden ausgebrachten Zustand; Aktuator-Haltemoment allein genügt nicht.
- Positive Verstauriegel und Triggersperren, die verhindern, dass Pilot, Fühler oder Stütze aktiv werden, bis ihr Richtungsmodus bewusst gewählt ist.
- Gegenseitiger Ausschluss von Auf- und Abstiegsmechanismen, vorzugsweise mechanisch ebenso wie logisch erzwungen.
- Eine physische Crawl-Untersetzung oder Geschwindigkeitsbegrenzung, die normale Fahrgeschwindigkeit unmöglich macht, sobald Kurven-/Krückenfahrwerk ausgebracht ist.
- Phasenerhaltende Bremsen oder Riegel, die den Krückenmechanismus statisch stabil lassen, wenn die Bewegung unerwartet stoppt.
- Lasthalteverriegelungen an jeder manuellen Krücke, sodass die fahrende Person das besetzte Fahrzeug nie dauernd allein mit Handkraft tragen muss.
- Unabhängige Freigabesteuerung, die das Entlasten einer Krücke verhindert, bevor die Gegenseite oder die Primärräder die Übertragung sicher aufnehmen können.
- Unabhängige Bestätigung von Stellung und Riegeleingriff, vorzugsweise mit unterschiedlichen Erfassungsprinzipien.
- Bremsen- und Geschwindigkeits-Interlocks vor der Ausbringung sowie Beschleunigungssperre, während der Mechanismus in einem unsicheren Zwischenzustand ist.
- Rückrollsicherung und kontrolliertes Absenken für Aufstieg, Abstieg und Stromausfall.
- Eine definierte sichere Reaktion auf asymmetrische Ausbringung, Kontaktverlust, Überlast, Sensorwiderspruch, Aktuatorstillstand oder strukturelle Durchbiegung.
- Manuelle Bergung oder Absenkung, die ohne Helfende in einer Quetschzone ausführbar ist.
- Redundante Stütze oder ein Auffangmechanismus, sodass ein Ausfall nicht sofort zum Überschlag oder unkontrollierten Fall führt.
- Schutz vor Quetschen, Scheren, Einschluss, heißen Oberflächen und Bodenstreifen um Arme, Drehpunkte und Verstautaschen.
- Klare Modusanzeige und Rückmeldung, ob das Fahrzeug sicher fahren, halten, transformieren oder verlassen werden darf.
- Strukturelle Lastgrenzen und Verweigerungslogik, wenn Hindernisgeometrie, Nutzlast, Querneigung, Kraftschluss oder Landequalität die validierte Hülle überschreiten.
- Physische Halterung, die verhindert, dass ein verstauter Arm nach Riegel-, Leitungs- oder Softwarefehler bei Cruise-Geschwindigkeit ausfährt.

Das System braucht Fehlerbaum und Gefahrenanalyse für das vollständige Manöver, nicht nur für die Aktuatorhardware. Ein mechanisch verriegeltes, aber schlecht platziertes Rad kann trotzdem einen gefährlichen Drehpunkt erzeugen.

## Weitere Konzepte innerhalb der Einfachheitsgrenze

### Einfache Hindernismessung

Mehrere feste Ultraschall- oder Time-of-Flight-Messungen könnten den Abstand zu einer Kante schätzen, Steigungs- oder Absatzhöhe annähern und bestätigen, dass eine Landefläche existiert. Eine kleine Sensorleiste oder ein mechanisch geschwenkter einachsiger Abstandssensor kann in Betracht kommen, wenn feste Sensoren wichtige tote Winkel lassen. Ziel ist eine kleine Menge konservativer skalarer Messungen, kein Bild, keine Punktwolke und kein 3-D-Geländemodell.

### Bestätigte Vorausbringung

Nachdem die fahrende Person anhält und den gewählten Laufwerk-Modus autorisiert, könnten Abstandssensoren bestätigen, dass das Fahrzeug im zulässigen Anfahrfenster liegt, und die Stützen vorpositionieren. Das System soll während Cruise nicht vorausschauend ausbringen und nicht auf Streckenhistorie vertrauen, um ein Hindernis für sicher zu erklären.

### Adaptiver Radstand

Das transformierbare Fahrgestell könnte den Radstand verkürzen, um Durchbruchrisiko und erforderlichen Armreichweite zu senken, und nach dem Hindernis wieder verlängern. Radstandsänderung darf die fahrende Person nicht destabilisieren und keinen unbeabsichtigten Vortrieb erzeugen.

### Aktive Nivellierung

Koordinierte Stützarm- und Federungssteuerung könnte die Sitzlage über Querneigung und versetzte Radhöhen halten. Komfortnivellierung muss Reifenkontakt, Strukturgrenzen und Kippstabilität untergeordnet bleiben.

### Weitere Möglichkeiten

- Unabhängig ausfahrbare Links-/Rechts-Stützen für Querneigung und Einradhindernisse.
- Austauschbare Rad- oder Fußmodule für weichen Boden, Schnee oder empfindliche Innenflächen.
- Ein passiver oder federunterstützter Notausbringzustand, der nicht von voller elektrischer Leistung abhängt.
- Optionale verdrahtete Service-Telemetrie zum Aufzeichnen von Abständen, Zeiten, Strömen, Stellungen und Fehlerzuständen während Tests, ohne Konnektivität zum Betrieb zu machen.

## Offene Konstruktionsfragen

### Funktionshülle

- Ziel der ersten Untersuchung (Gesprächsentscheidung, 2026-08-28): eine kurze Folge von zwei Stufen. Maximale Steigung, Absatz, Lücke, Auftrittstiefe, Kantenradius, Querneigung und Anfahrwinkel jenseits dieses Bereichs bleiben offen.
- Welche Flächen sind zu schwach, glatt, lose oder unregelmäßig für einen sicheren Stützradkontakt?
- Welchen Nutzlast- und Schwerpunktbereich muss der Mechanismus beherrschen?

### Architektur

Keine der drei Architekturfamilien ist ausgewählt; sie bleiben zu verfolgende Alternativen.

- Wie viele Stützräder sind nötig, und wo sollen ihre Drehpunkte anbinden?
- Sollen vordere und hintere Einheiten gepaart, vollständig unabhängig, teleskopierend oder mehrlenkerig sein?
- Kann eine hängende Pilotrolle eine Zielstufe von Rauheit, Geröll, einer Wand oder einer Person ohne elektronische Klassifikation unterscheiden?
- Welcher Gestängeweg setzt den Ausleger auf die obere Fläche, bevor Last aufgenommen wird, und bleibt verstaut kompakt?
- Kann ein passiver Mechanismus ausreichenden Hub ohne übermäßige Vorwärtskraft, Weg, Stoßlast oder Klemmrisiko erreichen?
- Welches rein mechanische Ereignis soll vordere und hintere Stützmechanismen in der richtigen Reihenfolge verriegeln, freigeben und zurücksetzen?
- Welcher Wähler kann Aufstiegs-, Abstiegs- und Stabilisierungsfunktionen unabhängig scharfschalten und zugleich garantieren, dass alle anderen Trigger physisch getrennt bleiben?
- Kann ein Stützarm entgegengesetzte Richtungen bedienen, ohne ein kompliziertes, mehrdeutiges oder ausfallanfälliges Umkehrgestänge zu erzeugen?
- Welche Phasen brauchen getrennte Hardware, und welche können Arm, Rad, Drehpunkt oder Riegel sicher teilen?
- Können Kurven-/Krückenräder Hardware mit Auf-/Abstiegsstützen teilen, oder sollen ihre Wiederholzykluslasten und ihr Takt mechanisch getrennt bleiben?
- Welche Handhebelkraft und welcher Weg lassen die fahrende Person jede Krücke setzen und belasten, während sie weiter angenehm tritt? Die Referenzpersona hat starke Oberkörperkapazität; Krücken sind analog zu Skistöcken, aber Kraft, Weg und Ermüdung brauchen trotzdem Messung.
- Crawl verlangt kein gleichzeitiges Lenken, Bremsen und Rudern. Welches eigene Halt-, Festhalte-, Abbruch- und Rückzugsverfahren im Crawl-Modus hält das Fahrzeug steuerbar, ohne beide Hände von den Krücken zurückzuholen?
- Welches Kurvenprofil und welche Phasenbeziehung erzeugen die glatteste Fahrgestellbahn bei sicherem Stützpolygon?
- Kann der Krückenzyklus in jedem Winkel sicher stoppen, oder muss ein mechanischer Index ihn in eine von mehreren stabilen Raststellungen zwingen?
- Wie kann kontrollierter Rückzug funktionieren, während Krückenelemente einen wesentlichen Lastanteil tragen?
- Ist ein querverkoppelter Links-/Rechts-Mechanismus sicherer als unabhängige Folger, wenn die Anfahrt nicht perfekt rechtwinklig ist?
- Kann ein Mechanismus Zugangsstabilisierung, Parken und Hindernisüberwindung ohne unsichere Kompromisse bedienen?
- Wie werden ungefederte Masse, Verstauvolumen, Luftwiderstand, Schlamm, Wasser, Steine, Eis und Korrosion beherrscht?

### Dynamik und Regelung

- Welche Lastübertragungsbahn minimiert Nicken, Wanken, Radschlupf, Aktuatorkraft und Unbehagen der fahrenden Person?
- Wie werden Federungs- und Fahrwerkregler daran gehindert, einander zu bekämpfen?
- Was geschieht, wenn ein Stützrad nach Lastaufnahme den Kontakt verliert?
- Welche Hindernis-Modus-Geschwindigkeit und Bremsstrategie bleiben bei Auf- und Abstieg beherrschbar?
- Wie setzt das Fahrzeug aus einem abgebrochenen Manöver sicher zurück oder zieht sich zurück?

### Strukturen und Aktuierung

- Welche Spitzen- und Ermüdungslasten treten an Armdrehpunkten, Riegeln und Fahrgestellschnittstellen auf?
- Können elektromechanische Aktuatoren die erforderlichen Kraft-, Weg-, Lastspiel-, Rücktreib- und Dichtungsziele erfüllen?
- Ist hydraulische Aktuierung gerechtfertigt, oder würden Leckage, Wartung und Fehlerverhalten ihre Leistungsdichte überwiegen?
- Können schwerkraftunterstützte Bewegung und Ausgleich die Aktuatorgröße senken, ohne das Fail-safe-Verhalten zu gefährden?

### Human Factors und Zugänglichkeit

- Wie viel Bestätigung und Aufmerksamkeit der fahrenden Person soll ein Manöver verlangen?
- Kann die fahrende Person bequem zurückgehalten bleiben und trotzdem einen Notausstieg ausführen?
- Welche Rückmeldung ist für Fahrende mit unterschiedlichen sensorischen, kognitiven oder motorischen Fähigkeiten verständlich?
- Kann eine helfende Person das Fahrzeug ohne außergewöhnliche Kraft oder Exposition gegenüber Quetschzonen bergen?

### Regulierung und Validierung

- Wie werden deutsche und EU-Behörden motorische Hub-, Nivellier- und Stützfunktionen an einem Fahrrad oder EPAC einstufen?
- Welches funktionale Verhalten würde einen Stützmechanismus als Vortrieb behandeln lassen?
- Muss jeder ausfahrbare Breiten- und Radzahlzustand Fahrrad-Ausrüstungs- und Infrastrukturanforderungen erfüllen?
- Welche Maschinen-, funktionalen Sicherheits-, Fahrzeug-, Fahrrad-, Krankenfahrstuhl- oder Hebezeugnormen liefern nützliche Prüfverfahren, auch wenn sie nicht unmittelbar verpflichtend sind?
- Welche Teststufung auf Privatgelände ist vor einem besetzten Hindernisversuch erforderlich?

## Vorgeschlagenes Belegprogramm

1. Eine Zweistufen-Hindernishülle definieren und vollständige quasistatische Freikörper- und Kippanalyse abschließen.
2. Ein kinematisches Modell mit Fahrgestelltransformation, Federungsweg, Armreichweite und Kollisionsfreigängen bauen.
3. Auf- und Abstieg mit realistischen Schwerpunkt- und Reifenkontaktannahmen simulieren.
4. Ein vollmaßstäbliches Stützmodul gegen eine starre Vorrichtung mit Prüflasten und mechanischen Verriegelungsfehlerfällen testen.
5. Ein instrumentiertes Ballastfahrzeug vor einem besetzten Prototyp nutzen.
6. Manuelle Sequenzierung bei sehr geringer Energie auf kontrolliertem Prüfstand und zugangskontrolliertem Gelände validieren.
7. Begrenzte unterstützte Positionierung erst hinzufügen, nachdem mechanische Folge und Abbruchverhalten nachgewiesen sind; Lidar, Computer Vision und autonome Geländekartierung außerhalb der Basis halten.
8. Vor öffentlichen Straßentests eine schriftliche Einstufungsmeinung für die eingefrorene Konfiguration einholen.

## Verwandte Dokumente

- [Transformierbares Fahrgestell](transforming-chassis_DE.md)
- [Referenzfahrzeug](reference-vehicle_DE.md)
- [Zugänglichkeit](accessibility_DE.md)
- [Federung](../engineering/suspension_DE.md)
- [Variable Spurweite](variable-track_DE.md)
- [Einstufungsmatrix der Fahrzeuge](../regulatory/classification_DE.md)
- [Regulatorische Forschung: Deutschland](../regulatory/germany_DE.md)
- [Regulatorische Forschung: Europäische Union](../regulatory/eu_DE.md)
