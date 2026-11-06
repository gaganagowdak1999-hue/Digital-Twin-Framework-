# Engineering patterns and considerations

## 1. Separate transport from persistence

MQTT decouples telemetry publishers from the consumer that validates/parses messages and writes measurements to PostgreSQL. This reduces direct coupling between sensor producers and the web application.

## 2. Use REST for queries and WebSockets for pushed state

The API uses HTTP endpoints for project/device lookup, historical readings, and analytics. A WebSocket route is used for live actuator-state updates, which suits server-pushed changes better than repeated polling.

## 3. Keep BIM semantics alongside operational data

IFC provides building-element context, while device/channel metadata and time-series measurements provide operational context. Combining the two allows users to inspect a model element and view related sensor information.

## 4. Distinguish numeric and categorical telemetry

The ingestion code stores numeric values separately from non-numeric values. This supports numeric aggregation while retaining categorical states, although it also means consumers must account for two measurement paths.

## 5. Areas to strengthen for production use

The following are engineering recommendations, not claims that these features are implemented:

- Validate topic and payload schemas before persistence.
- Define a consistent timezone policy (prefer UTC) for measurement timestamps.
- Add idempotency or duplicate-message handling.
- Add retry/dead-letter handling for transient database or broker failures.
- Replace or bound the in-memory channel cache and define invalidation behaviour.
- Add authentication/authorisation to broker topics and WebSocket connections.
- Add observability: structured logs, metrics, tracing, and service health checks.
- Add automated integration tests for MQTT-to-database and IFC-to-device mapping paths.
