# Deployment and service orchestration

The source archive contains Dockerfiles and Docker Compose definitions for a multi-service setup. The documented core stack includes a relational database, MQTT broker, MQTT consumer, FastAPI backend, and web frontend. Optional compose definitions support the MQTT producer/simulator and actuator visualiser.

## Containerised service layout

| Service | Role |
|---|---|
| PostgreSQL | Persistent relational storage |
| Mosquitto | MQTT message broker |
| MQTT consumer | Telemetry subscriber and database writer |
| FastAPI backend | REST and WebSocket application interface |
| Main web frontend | Browser dashboard and IFC model viewer |
| MQTT producer | Optional sensor simulation/publishing |
| Actuator visualiser | Optional separate UI for virtual actuators |

The frontend container configuration includes Nginx for serving the built web client. The project also contains environment-validation scripts, reflecting that services expect runtime configuration to be supplied externally.

## Why this showcase does not include deployment files

The public showcase is documentation-only. It excludes Docker Compose files, Dockerfiles, environment templates, broker configuration, shell scripts, and runtime configuration. Those files can expose internal ports, service names, infrastructure assumptions, or security-sensitive defaults. A public deployment guide should be recreated separately with reviewed, safe defaults if a reproducible demo is later required.
