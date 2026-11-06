# Illustrative MQTT message examples

These examples are synthetic and use fictional device names and values. The consumer source parses the final two topic segments as the device name and channel type, and expects a comma-separated Unix timestamp in milliseconds followed by the value.

## Numeric reading

**Topic**

```text
showcase/demo-building/floor-1/ExampleSensor_01/temperature
```

**Payload**

```text
1770000000000, 21.8
```

## Categorical reading

**Topic**

```text
showcase/demo-building/floor-1/ExampleSensor_01/status
```

**Payload**

```text
1770000005000, active
```

## Parsing behaviour described by the implementation

- The device name is taken from the second-to-last topic segment.
- The channel type is taken from the last topic segment.
- The timestamp is interpreted as Unix milliseconds.
- Values parseable as floating point are stored as numeric readings; other values are stored as strings.

Do not publish to a real broker using these examples unless the topic namespace and schema have been explicitly configured for that environment.
