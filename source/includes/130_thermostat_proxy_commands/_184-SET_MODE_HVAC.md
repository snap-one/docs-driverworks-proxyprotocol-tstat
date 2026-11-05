## SET_MODE_HVAC

Sets the thermostat HVAC mode. This command is available through programming.


### Name

`SET_MODE_HVAC ()`



| Parameter | Type   | Description                                                                                |
| --------- | ------ | ------------------------------------------------------------------------------------------ |
| MODE      | STRING | Required: HVAC mode name. The mode names are determined by the [hvac_modes][1] capability. |

### Parameter

`MODE`

### Notification

When the thermostat actually changes the HVAC mode, the protocol driver should send back the corresponding [HVAC_MODE_CHANGED][1] notification.



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-hvac_mode_changed