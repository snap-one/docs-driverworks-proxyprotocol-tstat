## SET_MODE_FAN

 Sets the thermostat fan mode. This command is available through programming.


### Name

`SET_MODE_FAN ()`



| Parameter | Type   | Description                                 |
| --------- | ------ | ------------------------------------------- |
| MODE      | STRING | Required: Mode name to set the fan mode to. |


### Notification

When the thermostat actually changes the fan mode, the protocol driver should send back the [FAN_MODE_CHANGED][1] notification.



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-fan_mode_changed
