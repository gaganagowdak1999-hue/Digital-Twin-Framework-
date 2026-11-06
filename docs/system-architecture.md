# System architecture

## Overview

The platform is composed of independently deployable services. The React web client presents building and operational information; a FastAPI backend exposes application and analytics operations; PostgreSQL stores application entities and measurements; MQTT carries telemetry; and a dedicated actuator visualiser displays actuator state.

## Component responsibilities

| Component | Responsibility | Main technologies evidenced in project |
|---|---|---|
| Web frontend | Dashboard, sensor views, analytics, settings, IFC viewer | React, TypeScript, Material UI, React Query, Three.js / That Open Components, web-ifc |
| API backend | Authentication, project/device queries, live data, analytics, actuator commands | Python, FastAPI, SQLAlchemy |
| Relational database | Project/user/device/channel metadata and measurements | PostgreSQL |
| MQTT broker | Topic-based message routing between publishers and subscribers | Eclipse Mosquitto, MQTT |
| MQTT consumer | Parse telemetry messages, resolve channels, persist values | Python, Paho MQTT, SQLAlchemy |
| MQTT producer / simulator | Publish simulated sensor readings for development/testing | Python, Paho MQTT |
| IFC parser | Inspect IFC sensor entities and selected property-set metadata | IfcOpenShell |
| Actuator visualiser | Show virtual fan/light state and receive live updates | React, TypeScript, WebSocket |

## Logical component diagram

See [`../diagrams/system-context.mmd`](../diagrams/system-context.mmd) for the Mermaid source.

## Communication patterns

- **HTTP/REST:** The browser calls FastAPI endpoints for projects, devices, sensor history, analytics, and actuator commands.
- **MQTT publish/subscribe:** Producers publish sensor messages; the consumer subscribes, parses the topic/payload, and persists readings.
- **WebSocket:** The actuator visualiser receives an initial state and subsequent live actuator updates.
- **SQL:** Backend and consumer services use SQLAlchemy to interact with PostgreSQL.

## Architectural boundary

This document describes the structure visible in the supplied source archive. It does not assert that every service was deployed in production or that every integration was continuously operational.
