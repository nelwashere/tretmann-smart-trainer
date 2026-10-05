# Vorhandenen Sensor untersuchen

## Ausgangslage

Der Originalcomputer ist über einen Stecker mit dem Unterteil verbunden. Ein zweipoliger Anschluss und ein passiver Reedkontakt werden vermutet, sind aber nicht bestätigt.

## 1. Durchgang am Unterteil

1. Stecker vom Originalcomputer abziehen.
2. Am Kabel zum Unterteil zwischen den beiden Kontakten Widerstand/Durchgang messen, sofern der Anschluss tatsächlich zweipolig ist.
3. Pedale langsam drehen und die wechselnden Werte beobachten.
4. Bei mehreren Kontakten zuerst Anschluss und Belegung klären.

Wechselt die Messung zwischen offenem Stromkreis und wenigen Ohm, passt das zu einem passiven Schaltkontakt. Bleibt sie unverändert, ist der Sensortyp damit nicht geklärt; mögliche Gründe sind Sensorstellung, zu kurze Impulse oder ein anderer Sensortyp.

## 2. Impulse pro Kurbelumdrehung

- Ausgangsstellung an Kurbel und Rahmen markieren.
- Langsam zehn vollständige Kurbelumdrehungen ausführen.
- Impulse zählen und durch zehn teilen.
- Messung wiederholen.
- Zusätzlich beobachten, ob nach dem Anhalten der Kurbel noch Impulse kommen.

Ein Sensor am nachlaufenden Schwungrad liefert nicht zwangsläufig unmittelbar die Kurbelbewegung. Das Verhalten muss vor der Nutzung als Cadence-Sensor überprüft werden. Akustische Durchgangsprüfer können kurze Impulse übersehen.

## 3. Spannung am Originalcomputer

- Sensor bleibt abgezogen.
- Originalcomputer einschalten bzw. aufwecken.
- Gleichspannung am Sensoranschluss messen und Polarität notieren.
- Messung auch während Schlaf-/Aufwachzuständen beobachten.

Am eingeschalteten Computer keine Widerstands- oder Durchgangsmessung durchführen. Eine Anzeige von 0 V beweist keine passive Schaltung: Der Computer könnte schlafen oder den Anschluss gepulst abfragen. Ein Multimeter kann kurze Spannungspulse übersehen.

## Messprotokoll

| Messung | Ergebnis |
|---|---|
| Gerätemodell/Typenschild | offen |
| Steckerart, Durchmesser, Kontaktanzahl | offen |
| Widerstand bei offenem Kontakt | offen |
| Widerstand bei geschlossenem Kontakt | offen |
| Impulse bei 10 Kurbelumdrehungen, Versuch 1 | offen |
| Impulse bei 10 Kurbelumdrehungen, Versuch 2 | offen |
| Impulse nach Kurbelstillstand | offen |
| Computerspannung im Wachzustand | offen |
| Computerspannung im Schlafzustand | offen |
| Polarität der Kontakte | offen |

## Entscheidung nach der Messung

**ESP32 als Ersatz für den Computer:** Bei bestätigtem potentialfreiem Schaltkontakt kann ein eigener 3,3-V-Eingang mit geeignetem Pull-up und Entprellung geplant werden.

**ESP32 parallel zum Computer:** Ein Zwischenadapter und eine zur gemessenen Schaltung passende Eingangsstufe sind erforderlich. Pegel, Bezugspotential, Belastung und Verhalten bei ausgeschaltetem ESP32 müssen geklärt werden. Ein zusätzlicher interner GPIO-Pull-up wird nicht ungeprüft parallel zugeschaltet.

**Ungeeigneter/unklarer Sensor:** Separaten Magneten und Reed-/Hall-Sensor direkt an der Kurbel verwenden.
