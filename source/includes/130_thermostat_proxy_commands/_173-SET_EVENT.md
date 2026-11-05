## SET_EVENT

Used in conjunction with Preset Scheduling. This command is sent to the protocol driver when the preset scheduler determines it's time for a new event to be run for Preset Scheduling. 

Sets a single thermostat event payload. This command is **NOT** handled by the proxy and must be implemented in the protocol driver. This command is available through programming and is used when the thermostat exposes event-driven behavior that must be forwarded to the connected device.


### Name

`SET_EVENT ()`


| Parameter | Type   | Description                            |
| --------- | ------ | -------------------------------------- |
| PRESET    | STRING | Name of the Preset that was triggered. |


### Command Sent to Protocol Driver

`SET_EVENT`


### Notification

Once the protocol driver has handled the `SET_EVENT` command or the the driver receives a notification from the thermostat that the preset changed, then a [PRESET_CHANGED][1] notification should be sent to the proxy.



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-preset_changed