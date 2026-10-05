# Architektur

## Erste Ausbaustufe: Trittfrequenz

Der ESP32 stellt einen BLE Cycling Speed and Cadence Service bereit. Der Originalcomputer soll nach Möglichkeit weiter nutzbar bleiben.

Geplante CSC-Daten:

| Größe | Bedeutung |
|---|---|
| Kumulierte Kurbelumdrehungen | Vollständige Kurbelumdrehungen, kein ungeprüfter Rohimpulszähler |
| Zeitpunkt der letzten Kurbelumdrehung | Ereigniszeit des Sensors |
| CSC Feature | Unterstützung von Kurbelumdrehungsdaten |

Bei mehreren Impulsen pro Kurbelumdrehung muss die Firmware diese korrekt in Kurbelumdrehungen umsetzen. Ein nicht ganzzahliger Faktor erfordert eine gesonderte Auswertung; Rohimpulse dürfen nicht als Kurbelumdrehungen angekündigt werden.

Zeitbasis, Zählerüberläufe, Entprellung und Wiederverbindung werden bei der Implementierung gegen die Bluetooth-Spezifikation geprüft. Das frühere Firmware-Grundgerüst aus dem Gespräch ist noch kein getesteter Projektstand und wird deshalb nicht als fertige Firmware übernommen.

## Android und Health Connect

OpenCycling ist der bisherige App-Kandidat. Vor Festlegung prüfen:

1. Betrieb mit ausschließlich Cadence-Sensor, ohne Power-/FTMS-Trainer.
2. Gleichzeitige Verbindung zur Charge 6 als Herzfrequenzquelle.
3. Aufzeichnung eines Indoor-Cycling-Trainings.
4. Tatsächlich nach Health Connect exportierte Datentypen und Zeitreihen.
5. Sichtbarkeit des Trainings in der gewünschten Zielanwendung.

Ein angebotener Health-Connect-Sync ist keine Zusage, dass sämtliche angezeigten Sensorwerte exportiert werden. Die Verarbeitung für Coaching bleibt eine gesonderte Frage.

## Widerstand und FTMS

Spätere Schritte:

- Mechanik des Widerstandsreglers untersuchen.
- Position zuverlässig erfassen.
- Stellmotor, Referenzierung und Grenzen bestimmen.
- BLE FTMS mit den tatsächlich unterstützten Funktionen implementieren.
- App-Kompatibilität für Widerstandskommandos prüfen.

Widerstandssteuerung und ERG-Leistungsregelung sind getrennte Funktionen. ERG soll erst nach Leistungsmessung oder nachgewiesener Kalibrierung umgesetzt werden.

## Offene Entscheidungen

- Genauer Sensortyp und elektrischer Anschluss.
- Sensorposition und Verhältnis zur Kurbel.
- Paralleler Abgriff oder unabhängiger Kurbelkontakt.
- Konkretes ESP32-Board und Eingangsschaltung.
- App-Kompatibilität und Health-Connect-Export.
- Mechanische Ausführung der Widerstandsautomatik.
