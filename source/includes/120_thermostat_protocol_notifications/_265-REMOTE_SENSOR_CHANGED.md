## REMOTE\_SENSOR\_CHANGED

Updates the remote sensor usage state the proxy tracks for the thermostat. The protocol driver sends this after the thermostat updates its remote sensor state, for example in response to a [SET_REMOTE_SENSOR][1] command. Only applies when [has_remote_sensor][2] is enabled.


### Name

`REMOTE_SENSOR_CHANGED ()`


| Parameter | Type | Description                                                |
| --------- | ---- | ---------------------------------------------------------- |
| IN_USE    | BOOL | True/False indicating if the remote sensor should be used. |


### Returns

`None`


[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-proxy-commands-set_remote_sensor
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-capabilities-thermostat-capabilities-has_remote_sensor
