# Project plan – Bosporus

## Phase overview

| Phase | Title                          | Content                                                                | Milestone                                     | Status | Date |
|-------|----------------------------------|--------------------------------------------------------------------------|-------------------------------------------------|--------|------|
| 0     | Preparation                     | Order hardware, set up development environment                          | PlatformIO + toolchain working                 | ✅ Done | *(add date)* |
| 1     | Sensor node                     | Program the ESP32, read the sensor, set up MQTT connection              | Sensor sends readings                          | ✅ Done (Serial; MQTT publish still open) | *(add date)* |
| 2     | Embedded Linux gateway          | Configure and build the Buildroot image, flash it onto the Raspberry Pi | Custom Linux image boots on the Pi             | ⏳ Not started | — |
| 3     | Integration                     | Set up MQTT broker + processing script + database on the gateway         | Readings are stored persistently                | ⏳ Not started | — |
| 4     | Visualization                   | Connect Grafana/dashboard                                                | Live history of readings visible                | ⏳ Not started | — |
| 5     | Documentation & portfolio       | Finalize docs, clean up GitHub repo, optionally write a short write-up   | Presentable project for job applications         | 🔄 Ongoing | — |

*(Replace the "add date" placeholders with the actual dates you did the work — that's
useful context for anyone reading the repo, and honestly satisfying to fill in.)*

## Example timeframe (adjust to your available time)

- **Weeks 1–2**: Phase 0 + 1 (sensor node)
- **Weeks 3–5**: Phase 2 (embedded Linux – typically the most time-consuming part)
- **Week 6**: Phase 3 (integration)
- **Week 7**: Phase 4 (dashboard)
- **Week 8**: Phase 5 (docs & polish)

## Definition of done per phase

A phase counts as complete when:
1. the functionality demonstrably works (a short demo/screenshot/log),
2. the related configuration/code is version-controlled in the repo,
3. the documentation (README or the relevant docs/ file) has been updated.
