## SET_SETPOINT_HUMIDIFY

Sets the humidify setpoint. This command is available through programming and is only available if the [can_humidify][1] is enabled. The protocol driver must apply the setpoint and notify the proxy when the value changes.


### Name

`SET_SETPOINT_HUMIDIFY ()`



| Parameter | Type | Description                                                                                                                                                 |
| --------- | ---- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| SETPOINT  | INT  | Required: The value is an integer percentage from 0 to 100, depending on the thermostat’s [setpoint_humidify_min][1] and [setpoint_humidify_max][1] values. |


### Notification

When the thermostat actually changes the humidify setpoint, the protocol driver should send back a [HUMIDIFY_SETPOINT_CHANGED][2] notification.




[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-capabilities
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-humidify_setpoint_changed