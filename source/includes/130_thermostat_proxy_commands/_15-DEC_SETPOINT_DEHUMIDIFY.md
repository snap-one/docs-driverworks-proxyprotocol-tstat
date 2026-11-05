## DEC_SETPOINT_DEHUMIDIFY

Decreases the humidity setpoint. This command is **NOT** handled by the proxy and must be implemented in the protocol driver. This command is available through programming and is only available if [can_dehumidify][1] is true. The capability [`setpoint_dehumidify_resolution`][1] may be used to determine the decrement value. Use the [DEHUMIDIFY_SETPOINT_CHANGED][2] notification to notify the proxy of the new dehumidify setpoint value.


### Name

`DEC_SETPOINT_DEHUMIDIFY ()`


### Parameter

`None`

### Notification

When the thermostat actually changes the dehumidify setpoint, the protocol driver should send back a notification in the form:

- `DEHUMIDIFY_SETPOINT_CHANGED`
- Parameters:
    - `SETPOINT`

See the [dehumidify setpoint changed][2] notification documentation for the exact parameter details and valid values.


### Returns

`None`


[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-capabilities
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-dehumidify_setpoint_change