# Projektplan – Bosporus

## Phasenübersicht

| Phase | Titel                          | Inhalt                                                                 | Ergebnis / Meilenstein                        |
|-------|----------------------------------|------------------------------------------------------------------------|-----------------------------------------------|
| 0     | Vorbereitung                     | Hardware bestellen, Entwicklungsumgebung einrichten                    | PlatformIO + Toolchain lauffähig               |
| 1     | Sensor-Node                      | ESP32 programmieren, Sensor auslesen, MQTT-Verbindung aufbauen         | Sensor sendet Messwerte per MQTT               |
| 2     | Embedded-Linux-Gateway           | Buildroot-Image konfigurieren und bauen, auf Raspberry Pi aufspielen    | Eigenes Linux-Image bootet auf dem Pi          |
| 3     | Integration                      | MQTT-Broker + Verarbeitungsskript + Datenbank auf dem Gateway einrichten | Messwerte werden persistent gespeichert        |
| 4     | Visualisierung                   | Grafana/Dashboard anbinden                                              | Live-Verlauf der Messwerte sichtbar            |
| 5     | Dokumentation & Portfolio        | Doku finalisieren, GitHub-Repo aufräumen, ggf. kurzen Erfahrungsbericht schreiben | Präsentierbares Projekt für Bewerbungen        |

## Beispielhafter Zeitrahmen (anpassbar an verfügbare Zeit)

- **Wochen 1–2**: Phase 0 + 1 (Sensor-Node)
- **Wochen 3–5**: Phase 2 (Embedded Linux – erfahrungsgemäß der zeitintensivste Teil)
- **Woche 6**: Phase 3 (Integration)
- **Woche 7**: Phase 4 (Dashboard)
- **Woche 8**: Phase 5 (Doku & Feinschliff)

## Definition of Done je Phase

Eine Phase gilt als abgeschlossen, wenn:
1. die Funktion nachweislich läuft (kurze Demo/Screenshot/Log),
2. die zugehörige Konfiguration/der Code im Repo versioniert ist,
3. die Doku (README oder betroffenes docs/-File) aktualisiert wurde.
