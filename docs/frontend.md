# Frontend application

## Main web client

The main browser application is built with React and TypeScript. Its source structure includes dashboard layout, route protection, authentication/theme contexts, sensor and analytics pages, settings, actuator views, and an IFC viewer.

| Frontend capability | Implementation elements visible in the source |
|---|---|
| Navigation and page layout | React components and React Router |
| Authentication state | Authentication context and protected routes |
| Server-state fetching | TanStack React Query and Axios |
| Dashboard and device views | Dashboard and sensor route components |
| Analytics charts | Recharts and date-range controls |
| IFC model inspection | That Open Components, web-ifc, Three.js |
| UI components | Material UI |

## Actuator visualiser

A separate React + TypeScript client visualises virtual actuators. The source includes fan and light components and a WebSocket connection to the backend's live actuator route. The client processes an initial state snapshot and subsequent state updates.

## Extension/plugin structure

The main frontend includes a plugin-system area with plugin context, registration, type definitions, and a chart-switcher plugin. This indicates an extension point for UI functionality rather than a single monolithic page implementation.

## Note

This repository documents the frontend architecture; it does not include the original frontend source or bundled model assets.
