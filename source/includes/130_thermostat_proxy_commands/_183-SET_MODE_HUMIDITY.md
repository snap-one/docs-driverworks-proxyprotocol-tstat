## SET_MODE_HUMIDITY

Sets the thermostat humidity mode. This command is available through programming and is only available when [can_humidify][1] is enabled.


### Name

`SET_MODE_HUMIDITY ()`



| Parameter | Type   | Description                                                                                        |
| --------- | ------ | -------------------------------------------------------------------------------------------------- |
| MODE      | STRING | Required: Humidity mode name. The mode names are determined by the [humidity_modes][1] capability. |


### Notification

When the thermostat actually changes the humidity mode, the protocol driver should send back the corresponding [HUMIDITY_MODE_CHANGED][2] notification.



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-capabilities
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-humidity_mode_changed
