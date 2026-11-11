# Building Digital Twin – Technical Showcase

A public-facing technical showcase of a collaborative university project that connects a building information model (BIM/IFC) with IoT sensor data, analytics, and virtual actuator visualisation through a web platform.

> **Project context:** Collaborative academic project. This repository is a documentation and showcase companion, not the original application repository. It intentionally contains no application source code, building model, credentials, environment files, database dump, or deployment configuration.

## Explore the project

| File | What it explains |
|---|---|
| [System architecture](docs/system-architecture.md) | Components, responsibilities, and service boundaries |
| [Data flow](docs/data-flow.md) | Sensor telemetry from MQTT to persistence and dashboard |
| [Backend and API](docs/backend-api.md) | FastAPI service modules and documented endpoint operations |
| [BIM / IFC integration](docs/bim-ifc-integration.md) | IFC sensor metadata extraction and browser model interaction |
| [Frontend](docs/frontend.md) | Web dashboard, charts, model viewer, and actuator UI |
| [Data model](docs/data-model.md) | Conceptual entities and numeric/non-numeric measurements |
| [Deployment overview](docs/deployment.md) | Containerised service layout (descriptive only) |
| [Technology stack](docs/technology-stack.md) | Technologies grouped by architectural layer |
| [Engineering decisions](docs/engineering-decisions.md) | Integration patterns and design trade-offs |

## Visual overview

![System architecture](images/system-architecture.jpg)

Additional editable diagrams are available in [`diagrams/`](diagram/).

## Sanitised examples

The [`examples/`](examples/) directory contains illustrative MQTT topic and payload examples. They are generic examples, not real building telemetry or credentials.

## Scope and attribution

The original implementation is maintained in a university GitLab repository that may require institutional access. This public repository documents the system at an architectural level and does not redistribute that implementation. The platform was developed collaboratively; this repository does not claim sole authorship. Personal contribution details should be added only by the project contributor and should describe work they actually completed.

The architecture image is included from the supplied project archive. Publish it only if project/university rules permit sharing it. No IFC model, sensor export, environment file, deployment secrets, or original source files are included.
