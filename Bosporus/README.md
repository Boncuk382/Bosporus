# Bosporus – Embedded Systems Portfolio Project

An end-to-end project to refresh and demonstrate skills in embedded electronics,
embedded Linux, and system integration – set up and documented like a real product
development project.

> **About the name**: The Bosporus is the strait that connects two continents – just
> like this gateway connects the sensor-hardware world with the software/visualization world.

## Project goal

This project ties together three core embedded disciplines in one system:

- **Embedded electronics / microcontroller**: A sensor node reads environmental data
  (temperature, humidity) and transmits it wirelessly.
- **Embedded Linux**: A gateway based on a self-built Linux image processes the data.
- **System integration & visualization**: A dashboard makes the data visible.

Alongside the technical build, the focus is deliberately also on **project management
artifacts** (requirements, architecture, milestone plan, risk register) – as evidence
that technical understanding and structured project control go hand in hand.

## Architecture overview

```
Sensor node  --MQTT-->  Gateway  --Data-->  Dashboard
(ESP32,                 (Raspberry Pi,       (Grafana /
 FreeRTOS)               Embedded Linux)       Web UI)
```

Details in [docs/architecture.md](docs/architecture.md).

## Technologies used

| Layer            | Technology                                |
|-------------------|-------------------------------------------|
| Sensor node       | ESP32, FreeRTOS, PlatformIO, DHT22 sensor |
| Gateway OS        | Buildroot (optionally Yocto later)        |
| Communication     | MQTT (Mosquitto broker)                   |
| Data storage      | SQLite / InfluxDB                         |
| Visualization     | Grafana                                   |

## Project structure

```
bosporus/
├── README.md
├── docs/
│   ├── architecture.md      # Detailed system architecture
│   ├── requirements.md      # Functional & non-functional requirements
│   ├── project-plan.md      # Phases, milestones, timeline
│   ├── progress-log.md      # Dated build log with photos/screenshots
│   ├── risk-register.md     # Risks and mitigations
│   ├── glossary.md          # Abbreviations and terms used
│   └── images/              # Photos and screenshots from the build
├── sensor-node/              # Firmware for the ESP32 (to follow)
├── gateway/                   # Buildroot configuration, scripts (to follow)
└── dashboard/                 # Grafana configuration / web UI (to follow)
```

## Status

🔧 In progress – project for the targeted refresh of embedded knowledge as part of a
technical project leadership role in the embedded space.

## Motivation

As a technical project lead in the embedded space – including hands-on development
experience of my own, such as a C++ application on an embedded Linux board with an
AVR32 processor – it matters to me not just to coordinate technical work, but to
understand it from practical experience: cross-compiling, bootloader/kernel, toolchains,
component supply chains, testing strategies.

This project brings that understanding up to the current state of the art – from modern
build systems to today's development workflows – and serves as practical evidence of
this competence for a technical project leadership role in the embedded space.
