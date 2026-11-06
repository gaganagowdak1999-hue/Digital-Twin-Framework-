# Backend and API overview

The backend is implemented in Python with FastAPI. API routes are separated by application responsibility. Exact base prefixes are configured by the application, so the table below lists route suffixes and operations rather than inventing a public base URL.

| Module | Method | Route suffix | Purpose |
|---|---|---|---|
| Authentication | POST | `/login` | Authenticate a user and return a token/basic user information |
| Authentication | POST | `/register` | Register a user account |
| Authentication | POST | `/forgot-password` | Password-reset operation exposed by the application |
| Projects | GET | `/` | Retrieve project options |
| Devices | GET | `/latest-values` | Retrieve devices with latest channel values; supports filters |
| Devices | GET | `/channel` | Retrieve available devices and channel options |
| Live data | GET | `/random-live-device` | Retrieve a live device snapshot for UI inspection |
| Live data | GET | `/live-data` | Retrieve time-windowed numeric or non-numeric device data |
| Analytics | GET | `/data` | Query time-series or aggregated numeric channel data |
| Actuators | POST | `/command` | Publish an actuator command through MQTT |
| Actuators | WebSocket | `/ws/live` | Send initial actuator state and live updates to connected clients |

## Analytics capabilities

The analytics route documents support for device/channel filtering, predefined ranges (7 days, 30 days, 6 months, 1 year), custom date ranges, and aggregations such as mean, maximum, minimum, sum, count, and median.

## Backend implementation elements

- **FastAPI** provides request routing and API schema generation.
- **Pydantic models** define request and response shapes.
- **SQLAlchemy** provides ORM/database access.
- **PostgreSQL** stores project, user, device, channel, and measurement records.
- Separate utility modules support authentication, live-data retrieval, analytics, device queries, actuator messaging, and WebSocket broadcasting.

## Security note

The original project archive includes authentication-related code and environment configuration examples. This showcase intentionally does not publish secrets, environment values, database records, or deployable authentication configuration. Review the original password-reset and authentication implementation before describing it as production-grade security.
