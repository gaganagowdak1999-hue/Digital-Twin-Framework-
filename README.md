# Digital Twin Framework for Building Operations

A collaborative university project exploring a digital-twin platform that connects building information models (BIM), IoT sensor data, backend services, and a web-based interface.

> **Project context:** Collaborative academic project at Bauhaus-Universität Weimar. This repository is a public-facing project overview, not the original university source-code repository. It intentionally contains only the project description and an architecture illustration.

## Overview

The platform is organised around a web frontend, a Python backend, a PostgreSQL database, and MQTT-based messaging. The project repository also contains an IFC parsing component and an actuator visualisation component.

The intended workflow is to ingest sensor messages through MQTT, process and persist the data in the backend/database layer, and make data available to the web application. The frontend includes dashboard and analytics views, alongside BIM-related functionality in the broader project.

## System architecture

![System architecture](images/system-architecture.jpg)

*Architecture illustration included in the supplied project archive. It represents the documented system structure; individual modules and integrations may have different implementation status.*

## Technology stack

| Area | Technologies evidenced in the project source |
|---|---|
| Frontend | React, TypeScript, Material UI, React Query, Three.js, web-ifc |
| Backend | Python, FastAPI, SQLAlchemy |
| Data storage | PostgreSQL |
| Messaging | MQTT, Eclipse Mosquitto, Paho MQTT |
| BIM / IFC | IFC parsing and web-based IFC tooling |
| Deployment | Docker, Docker Compose, Nginx |

## Main components

- **Web frontend:** React-based user interface with dashboard and analytics-related pages, plus BIM/IFC-related frontend dependencies.
- **Backend API:** FastAPI service for application endpoints and database access.
- **Sensor data pipeline:** MQTT broker, producer/simulator, and consumer components for message-based sensor-data flow.
- **Database:** PostgreSQL persistence for project data.
- **IFC processing:** Python utilities for parsing IFC model information and preparing project data.
- **Actuator visualisation:** A separate React-based visualiser for virtual actuator states.
- **Containerisation:** Dockerfiles and Docker Compose configuration for running the platform components.

## My contribution

This was a collaborative university project. Add only the modules, implementation tasks, and decisions you personally worked on before publishing this section. Do not imply sole authorship of the complete platform.

Suggested format:

- **Implemented:** [specific feature/module you personally implemented]
- **Contributed to:** [specific integration, testing, modelling, or documentation task]
- **Tools used directly:** [technologies you personally used]

## Scope and access

The original source code is hosted in a university GitLab repository and may require university authentication. This public showcase is provided to make the project context and high-level architecture understandable without access to that repository. It does not redistribute the original source code, IFC building model, environment files, credentials, or deployment configuration.

## Notes

- This overview describes the collaborative project based on the supplied repository documentation and source structure.
- The architecture image is included as a technical illustration, not as a claim that every depicted connection is fully operational or real-time.
- Add application screenshots only if you have permission to share them publicly and they do not expose confidential building, sensor, or university information.
