## SET_SCALE

Sets the thermostat temperature scale. This command is available through programming and is used to switch the thermostat between Celsius and Fahrenheit scale values. This command is only available when [can_change_scale][1] is enabled.


### Name

`SET_SCALE ()`


| Parameter | Type   | Description                               |
| --------- | ------ | ----------------------------------------- |
| SCALE     | STRING | Required: CELSIUS, FAHRENHEIT, C, c, F, f |


### Notification

When the thermostat actually changes the scale, the protocol driver should send back the [SCALE_CHANGED][2] notification.



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-capabilities
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-scale_changed