## INC_SETPOINT_HUMIDIFY

Increases the humidity setpoint. This command is **NOT** handled by the proxy and must be implemented in the protocol driver. This command is available through programming and is only available if [can_humidify][1] is true. The capability [`setpoint_humidify_resolution`][1] may be used to determine the increment value. Use the [HUMIDIFY_SETPOINT_CHANGED][2] notification to notify the proxy of the new humidify setpoint value.


### Name

`INC_SETPOINT_HUMIDIFY ()`


### Parameter

`None`

### Notification

When the thermostat actually changes the humidify setpoint, the protocol driver should send back a notification in the form:

- `HUMIDIFY_SETPOINT_CHANGED`
- Parameters:
    - `SETPOINT`

See the [humidify setpoint changed][2] notification documentation for the exact parameter details and valid values.


### Returns

`None`


[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-capabilities
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-humidify_setpoint_changed
