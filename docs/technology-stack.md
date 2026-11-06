# Technology stack

| Layer | Technologies | Role in the project |
|---|---|---|
| Main frontend | React, TypeScript | Component-based web application |
| UI and routing | Material UI, React Router | UI components and client-side navigation |
| API state and requests | TanStack React Query, Axios | Server-state caching and HTTP requests |
| Visualisation | Recharts | Sensor and analytics charts |
| BIM viewer | Three.js, That Open Components, web-ifc | Browser-side IFC loading and model interaction |
| Backend | Python, FastAPI, Uvicorn | REST API and WebSocket service |
| Data access | SQLAlchemy | ORM and database access |
| Database | PostgreSQL, psycopg2 | Relational persistence |
| Messaging | MQTT, Eclipse Mosquitto, Paho MQTT | Publish/subscribe telemetry and commands |
| IFC processing | IfcOpenShell | Python-side IFC entity/property inspection |
| Actuator UI | React, TypeScript, Vite, WebSocket | Virtual fan/light state visualisation |
| Containerisation / serving | Docker, Docker Compose, Nginx | Service packaging and frontend serving |

Technologies are listed because they appear in the supplied project archive. This list describes the project stack, not necessarily the technologies personally implemented by every team member.
