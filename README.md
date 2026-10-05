# TRETMANN Smart Trainer

DIY-Erweiterung eines TRETMANN-Hometrainers mit ESP32 und Bluetooth LE.

## Ziel

Trainingsdaten am Android-Smartphone aufzeichnen und über eine geeignete App nach Health Connect übertragen. Eine Fitbit Charge 6 soll optional die Herzfrequenz liefern. Home Assistant ist kein Bestandteil dieses Projekts.

Geplanter erster Datenweg:

- Hometrainer-Sensor → ESP32 → BLE Cycling Speed and Cadence Service (CSC).
- Charge 6 → Bluetooth-Herzfrequenz → Android-Trainingsapp.
- Android-Trainingsapp → Health Connect → gewünschte Health-/Coaching-Anwendung.

Die tatsächliche Kombination aus Sensoren, App, exportierten Datentypen und Zielanwendung muss im Praxistest geprüft werden. Insbesondere ist noch nicht bestätigt, ob die App Cadence als Zeitreihe nach Health Connect schreibt oder die Zielanwendung diese auswertet.

## Aktueller Stand

**Planung und Sensoruntersuchung; noch keine getestete Firmware.**

Der Originalcomputer ist per Stecker mit dem Unterteil verbunden. Ein passiver Magnetschalter ist eine Arbeitshypothese. Steckergröße, Belegung, Sensortyp und Messspannung sind noch unbekannt.

Der zunächst vorgeschlagene externe Kurbelmagnet bleibt eine Alternative, falls sich der vorhandene Sensor nicht zuverlässig nutzen lässt.

## Dokumentation

- [Sensor untersuchen und Messwerte festhalten](docs/sensor-messungen.md)
- [Architektur und offene Entscheidungen](docs/architektur.md)
- [Projektplan und Abnahmekriterien](docs/projektplan.md)

## Geplante Hardware

| Teil | Status |
|---|---|
| ESP32-C3 mit USB-Versorgung | Kandidat für BLE |
| Vorhandener Sensor im Hometrainer | Noch zu untersuchen |
| Zwischenadapter zum Originalcomputer | Erst nach Bestimmung von Anschluss und Pegeln |
| Reedkontakt und Kurbelmagnet | Alternative zum vorhandenen Sensor |
| Eingangsschaltung/Pegelanpassung | Noch nicht dimensioniert |
| Gehäuse und Befestigung | Nach Sensorentscheidung |

## Entwicklungsgrundsätze

- Bestehenden Sensoranschluss zuerst messen; nicht unmittelbar mit einem GPIO verbinden.
- Erste Version liefert gemessene Trittfrequenz.
- Geschwindigkeit, Distanz, Kalorien und Leistung werden erst ergänzt, wenn ihre Herkunft und Berechnung nachvollziehbar sind.
- Widerstandserfassung und Motorisierung sind spätere Ausbaustufen.
- ERG-Regelung benötigt eine belastbare Leistungsrückmeldung oder kalibrierte Kennlinie; ein motorisierter Regler allein genügt nicht.

## Nächster Schritt

Die Messvorlage in [docs/sensor-messungen.md](docs/sensor-messungen.md) ausfüllen. Danach können Eingangsschaltung, Sensorfaktor und Firmware festgelegt werden.
