## HOLD\_MODE\_CHANGED

Notification that should be sent to the proxy when hold mode has changed. Changes the variables [`HOLD_MODE`][1], [`ANA_HOLDMODE`][2]. Fires event [`HOLD_MODE_CHANGED`][3].


### Name

`HOLD_MODE_CHANGED ()`


| Parameter | Type | Range     | Description                                                                              |
| --------- | ---- | --------- | ---------------------------------------------------------------------------------------- |
| MODE      | STR  |           | Required: Mode name. If MODE is "Hold Until" then the following parameters will be sent: |
| YEAR      | INT  | 0-99 (YY) | Required if MODE is "Hold Until" and if `hold_until_mode` capability is "date,time".     |
| MONTH     | INT  | 1-12      | Required if MODE is "Hold Until" and if `hold_until_mode` capability is "date,time".     |
| DAY       | INT  | 1-31      | Required if MODE is "Hold Until" and if `hold_until_mode` capability is "date,time".     |
| HOUR      | INT  | 0-23      | Required if MODE is "Hold Until".                                                        |
| MINUTE    | INT  | 0-59      | Required if MODE is "Hold Until".                                                        |



[1]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-proxy-variables
[2]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-proxy-variables
[3]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-proxy-variables