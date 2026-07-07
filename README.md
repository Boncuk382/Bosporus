# Bosporus – Embedded-Systems-Portfolio-Projekt

Ein End-to-End-Projekt zur Vertiefung von Embedded Elektronik, Embedded Linux und
Systemintegration – aufgesetzt und dokumentiert wie ein reales Produktentwicklungsprojekt.

> **Zum Namen**: Der Bosporus ist die Meerenge, die zwei Kontinente verbindet – genau wie
> dieses Gateway die Sensor-Hardware-Welt mit der Software-/Visualisierungs-Welt verbindet.

## Ziel des Projekts

Dieses Projekt verbindet drei zentrale Embedded-Disziplinen in einem gemeinsamen System:

- **Embedded Elektronik / Microcontroller**: Ein Sensor-Node liest Umgebungsdaten
  (Temperatur, Luftfeuchtigkeit) aus und sendet sie drahtlos.
- **Embedded Linux**: Ein Gateway auf Basis eines selbst gebauten Linux-Images
  verarbeitet die Daten.
- **Systemintegration & Visualisierung**: Ein Dashboard macht die Daten sichtbar.

Neben dem technischen Aufbau liegt der Fokus bewusst auch auf **Projektmanagement-Artefakten**
(Anforderungen, Architektur, Meilensteinplan, Risikoregister) – als Nachweis, dass technisches
Verständnis und strukturierte Projektsteuerung zusammen gedacht werden.

## Architekturüberblick

```
Sensor-Node  --MQTT-->  Gateway  --Daten-->  Dashboard
(ESP32,                 (Raspberry Pi,        (Grafana /
 FreeRTOS)               Embedded Linux)        Web-UI)
```

Details siehe [docs/architecture.md](docs/architecture.md).

## Verwendete Technologien

| Ebene            | Technologie                              |
|-------------------|-------------------------------------------|
| Sensor-Node       | ESP32, FreeRTOS, PlatformIO, DHT22-Sensor |
| Gateway-OS        | Buildroot (später optional Yocto)         |
| Kommunikation     | MQTT (Mosquitto Broker)                   |
| Datenhaltung      | SQLite / InfluxDB                         |
| Visualisierung    | Grafana                                   |

## Projektstruktur

```
bosporus/
├── README.md
├── docs/
│   ├── architecture.md      # Systemarchitektur im Detail
│   ├── requirements.md       # Funktionale & nicht-funktionale Anforderungen
│   ├── project-plan.md       # Phasen, Meilensteine, Zeitplan
│   └── risk-register.md      # Risiken und Gegenmaßnahmen
├── sensor-node/               # Firmware für den ESP32 (folgt)
├── gateway/                    # Buildroot-Konfiguration, Skripte (folgt)
└── dashboard/                  # Grafana-Konfiguration / Web-UI (folgt)
```

## Status

🔧 In Aufbau – Projekt zur gezielten Aktualisierung von Embedded-Kenntnissen im Rahmen
einer technischen Projektleitungsrolle im Embedded-Umfeld.

## Motivation

Als technische Projektleiterin im Embedded-Umfeld – unter anderem mit eigener
Entwicklungserfahrung, etwa einer C++-Applikation auf einem Embedded-Linux-Board mit
AVR32-Prozessor – ist mir wichtig, technische Zusammenhänge nicht nur zu koordinieren,
sondern aus eigener Praxis zu verstehen: Cross-Compiling, Bootloader/Kernel, Toolchains,
Lieferketten für Bauteile, Testing-Strategien.

Dieses Projekt bringt dieses Verständnis auf den aktuellen Stand der Technik – von
modernen Build-Systemen bis zu heutigen Entwicklungs-Workflows – und dient als
praktischer Nachweis dieser Kompetenz für eine technische Projektleitungsrolle im
Embedded-Umfeld.
