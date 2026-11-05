## SET_REMOTE_SENSOR

Sets the thermostat remote sensor usage state. This command is only available when [has_remote_sensor][1] is enabled.

### Name

`SET_REMOTE_SENSOR ()`



| Parameter | Type | Description          |
| --------- | ---- | -------------------- |
| IN_USE    | BOOL | Required: True/False |
### Parameter

`IN_USE`

### Notification

When the thermostat actually updates the remote sensor state, the protocol driver should send back the [REMOTE_SENSOR_CHANGED][2] notification.



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-capabilities
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-remote_sensor_changed