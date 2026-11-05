## SET_MODE_HOLD

Sets the thermostat hold mode. This command is available through programming and is used to place the thermostat into or out of a hold state.


### Name

`SET_MODE_HOLD ()`


| Parameter | Type   | Range     | Description                                                                              |
| --------- | ------ | --------- | ---------------------------------------------------------------------------------------- |
| MODE      | STRING |           | Required: Mode name. If MODE is "Hold Until" then the following parameters are required: |
| YEAR      | INT    | 0-99 (YY) | Required if MODE is "Hold Until" and if `hold_until_mode` capability is "date,time".     |
| MONTH     | INT    | 1-12      | Required if MODE is "Hold Until" and if `hold_until_mode` capability is "date,time".     |
| DAY       | INT    | 1-31      | Required if MODE is "Hold Until" and if `hold_until_mode` capability is "date,time".     |
| HOUR      | INT    | 0-23      | Required if MODE is "Hold Until".                                                        |
| MINUTE    | INT    | 0-59      | Required if MODE is "Hold Until".                                                        |

### Notification

When the thermostat actually changes the hold mode, the protocol driver should send back the [HOLD_MODE_CHANGED][1] notification.



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-hold_mode_changed