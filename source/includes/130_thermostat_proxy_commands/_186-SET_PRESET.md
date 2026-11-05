## SET_PRESET

Sets the active thermostat preset. This command is available through programming and is only available when [can_preset][1] is enabled..


### Name

`SET_PRESET ()`

| Parameter | Type   | Description            |
| --------- | ------ | ---------------------- |
| NAME      | STRING | Required: Preset name. |

### Notification

Once the thermostat has been updated, the protocol driver should send back the [PRESET_CHANGED][2] notification.

[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-capabilities
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-preset_changed