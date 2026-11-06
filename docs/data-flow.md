# Sensor data flow

## Telemetry ingestion

The MQTT consumer implements the following processing sequence:

1. A sensor or simulator publishes a message to an MQTT topic.
2. The consumer receives the message from the broker subscription.
3. The consumer splits the topic and reads the device name and channel type from the final topic segments.
4. It resolves the matching channel identifier using device and channel metadata. A small in-memory cache avoids repeating the same lookup.
5. The payload is parsed as a Unix timestamp in milliseconds and a value.
6. Numeric values are converted to floating-point values; non-numeric values are retained as strings.
7. The reading is inserted into the corresponding numeric or non-numeric measurement table.
8. The API exposes latest values, historical readings, and analytics to the frontend.

## Message convention

The consumer code documents this topic convention:

`[prefix/]project/object/device/channel_type`

The payload convention is:

`<unix_timestamp_ms>, <value>`

A generic, fabricated example is provided in [`../examples/mqtt-message-examples.md`](../examples/mqtt-message-examples.md). Do not use it as a real endpoint or production topic without checking the deployment configuration.

## Data-flow diagram

See [`../diagrams/telemetry-data-flow.mmd`](../diagrams/telemetry-data-flow.mmd).

## Error handling visible in the consumer

The message handler logs and skips malformed topic structures, unknown device/channel combinations, and parsing/storage failures. This is a pragmatic ingestion strategy for a prototype; a production system would normally add explicit dead-letter handling, retry policy, schema validation, idempotency, and operational metrics.
