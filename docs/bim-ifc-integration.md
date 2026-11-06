# BIM / IFC integration

## Purpose

The project connects building information represented in IFC with operational IoT data. IFC provides the semantic/spatial context; device and channel records represent telemetry sources; the web viewer provides a visual way to inspect model elements and related properties.

## Server-side IFC inspection

The Python parser uses **IfcOpenShell** to inspect entities of type `IfcSensor`. The supplied parser searches property sets for selected metadata, including sensor marker/name, sensor identifier, version, and sensor-type information. It also inspects the sensor's type relationships and property sets where available.

The parser utilities are intended to support extraction and preparation of sensor-related information for the platform's data model. The original IFC file and sensor export are not included in this public showcase.

## Browser-side IFC viewing

The web client includes an IFC viewer based on **That Open Components**, **web-ifc**, and **Three.js**. The visible viewer implementation supports:

- Loading an IFC model in the browser.
- Selecting/highlighting model elements.
- Inspecting selected element properties, including IFC class, GlobalId, and name.
- Reading IFC relationships/property information for display.
- Showing sensor-related chart views (temperature, humidity, pressure) where the corresponding data mapping and readings are available.

## Integration concept

1. Parse IFC sensor entities and selected property-set metadata.
2. Maintain device/channel metadata in the application data model.
3. Associate selected model elements with relevant sensor/device context.
4. Retrieve measurements through backend APIs.
5. Present model context and time-series values together in the user interface.

The exact mapping rules depend on the source model and application configuration; this showcase does not publish building-specific identifiers or IFC assets.
