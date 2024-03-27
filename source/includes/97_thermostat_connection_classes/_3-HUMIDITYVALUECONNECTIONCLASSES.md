## HUMIDITY VALUE CONNECTION CLASS COMMANDS

Please see the Samples folder delivered in this SDK for Thermostat (V2) code examples.


## VALUE\_INITIALIZED
The value has been initialized. OnBindingChanged will cause this command to be sent automatically when the sending device goes Online.

### Signature

`VALUE_INITIALIZED ()`


| Parameter | Description |
| --- | --- |
| str | STATUS: Default is the status after first loading a driver and the value has never been set. `active` - Status if the value is active. `last_known` - The Last value received. The device either went offline or it has not been heard from since a reboot. |
| int | TIMESTAMP:  Timestamp of when the change occurred. |




## VALUE\_CHANGED
The value has changed.

### Signature

`VALUE_CHANGED ()`


| Parameter | Description |
| --- | --- |
| int | VALUE |
| int | TIMESTAMP:  Timestamp of when the change occurred. |




## VALUE\_UNAVAILABLE
The value is possibly no longer accurate. OnBindingChanged, device went Offline, etc

### Signature

`VALUE_UNAVAILABLE ()`


| Parameter | Description |
| --- | --- |
| str | STATUS: offline - Device went offline or was unbound. |