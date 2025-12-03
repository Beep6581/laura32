# Operating behaviour

The project is a battery-powered LoRa environmental sensor.

This document describes the intended high-level runtime behaviour.

## Measurement and transmit schedule

- Every 60 seconds the device wakes from sleep to:
  - power the sensors
  - measure environmental values
  - store the readings and update any internal state

- Under normal conditions, if readings change within a small threshold, the device:
  - accumulates measurements over time, and
  - sends a data update every 10 minutes.

- If a significant change in measured values is detected compared to the previously sent data (for example a sharp rise in temperature beyond a configured threshold), the device:
  - sends a data update immediately, but not more often than once every 60 seconds.

## Multiple devices

The design is intended to allow several such sensor devices to communicate with a single master or gateway device over LoRa. The exact protocol, data format and addressing scheme are unspecified for now.
