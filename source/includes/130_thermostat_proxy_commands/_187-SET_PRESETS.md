## SET_PRESETS

Sets one or more thermostat preset values in a grouped operation. This command is **NOT** handled by the proxy and must be implemented in the protocol driver. This command is available through programming and is used when the thermostat supports preset batching or bulk preset updates.


### Name

`SET_PRESETS ()`


| Parameter     | Type | Description |
| ------------- | ---- | ----------- |
| PRESET_FIELDS | XML  | Required:   |

#### Sample PRESET_FIELDS XML

```xml
<preset_fields>
    <field id = "heat_setpoint_f" value = "50"/>
    <field id = "cool_setpoint_f" value = "86"/>
    <field id = "humidify_setpoint" value = "20"/>
    <field id = "dehumidify_setpoint" value = "56"/>
    <field id = "hvac_mode" value = "Off"/>
    <field id = "humidity_mode" value = "Humidify"/>
    <field id = "fan_mode" value = "On"/>
    <field id = "heat_setpoint_c" value = "10"/>
    <field id = "cool_setpoint_c" value = "30"/>
</preset_fields>
```


