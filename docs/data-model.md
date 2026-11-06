# Conceptual data model

The supplied SQLAlchemy models and API schemas indicate a relational model built around projects, users, devices, channels, channel types, and time-stamped measurements.

## Core concepts

| Concept | Role |
|---|---|
| Project | Groups a building/project's devices and related data |
| User | Represents an application account |
| Device | Represents a sensor/device associated with a project |
| Channel | Represents a measurable or state-bearing property exposed by a device |
| Channel type | Describes the kind of value represented by a channel, such as temperature |
| Numeric measurement | Stores numeric channel values with timestamps |
| Non-numeric measurement | Stores categorical/text channel values with timestamps |
| Version / device-type metadata | Supports device and model metadata in the application schema |

## Measurement handling

The MQTT consumer resolves a device/channel pair to a channel ID. It then routes parsed values into separate persistence structures:

- Numeric values are converted to `float` and inserted into the numeric measurement table.
- Non-numeric values are converted to strings and inserted into the non-numeric measurement table.
- Each measurement is associated with a channel and timestamp.

## Simplified relationship view

`Project → Device → Channel → Measurement`

A `Channel` is associated with channel-type metadata. A `Measurement` is stored in either the numeric or non-numeric value structure. This is a conceptual overview, not a complete ER diagram or a substitute for the original database schema.
