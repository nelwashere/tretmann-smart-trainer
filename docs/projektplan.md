# Projektplan

## Meilenstein 1: Sensor verstehen

- [ ] Gerätemodell und Anschluss dokumentieren.
- [ ] Messprotokoll ausfüllen.
- [ ] Nachlauf des Sensors überprüfen.
- [ ] Anschlussvariante und Eingangsschaltung festlegen.

Abnahme: Sensortyp, elektrische Randbedingungen und Verhältnis zur Kurbel sind nachvollziehbar dokumentiert.

## Meilenstein 2: BLE-Cadence

- [ ] Reproduzierbare Firmware-Buildumgebung festlegen.
- [ ] Eingang mit Entprellung auswerten.
- [ ] Kurbelumdrehungen und Ereigniszeit korrekt bilden.
- [ ] CSC-Service und Wiederverbindung implementieren.
- [ ] Stillstand, Anlauf, längere Pause und Zähler-/Zeitüberläufe prüfen.
- [ ] RPM mit gezählten Kurbelumdrehungen über ein bekanntes Zeitintervall vergleichen.

Abnahme: Verlässliche Trittfrequenz in der Android-App, ohne zusätzliche Impulse bei Stillstand und ohne Verlust der Funktion des Originalcomputers.

## Meilenstein 3: Trainingsaufzeichnung

- [ ] Cadence-only-Betrieb der App prüfen.
- [ ] Charge 6 gleichzeitig verbinden.
- [ ] Kurzes Testtraining speichern.
- [ ] Trainingsart, Zeit, Herzfrequenz und Cadence-Export in Health Connect einzeln prüfen.
- [ ] Übernahme in die Zielanwendung kontrollieren.
- [ ] Mögliche doppelte Trainingsaufzeichnungen durch parallele Fitbit-Aufzeichnung untersuchen.

Abnahme: Tatsächlich übertragene Daten sind dokumentiert; fehlende Datentypen sind bekannt.

## Meilenstein 4: Widerstand

- [ ] Reglermechanik dokumentieren.
- [ ] Widerstandsposition erfassen.
- [ ] Motorisierung mit Referenzierung und mechanischen Grenzen planen.
- [ ] FTMS-Widerstandssteuerung umsetzen und App-Unterstützung prüfen.

## Meilenstein 5: Leistung

- [ ] Referenzmessung oder Powermeter auswählen.
- [ ] Falls sinnvoll, Kennlinie am konkreten Gerät erfassen.
- [ ] Genauigkeit und Grenzen dokumentieren.
- [ ] Erst danach Leistung über BLE anbieten und ERG prüfen.
