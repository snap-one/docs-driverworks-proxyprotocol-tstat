## PRESET\_FIELDS\_CHANGED

Updates the  Preset FIELDS TEMPLATE that UIs display for adding and modifying Presets. To UI comes through as `preset_fields`.  If this is modified, it is possible that existing presets will have data that is not in compliance. However, a protocol driver can modify this to have new `preset_fields` which are compatible. Do not delete this as Events are erased when presets are deleted. 


### Name

`PRESET_FIELDS_CHANGED ()` 


| Parameter | Type | Description                                                |
| --------- | ---- | ---------------------------------------------------------- |
| XML       | XML  | XML text string of XML matching the Preset Schedule schema |

### Sample preset_fields XML

```xml
<preset_fields>
    <field
        id = "heat_setpoint_f"
        type = "number"
        label = "Heat Below"
        min = "50"
        max = "90"
        res = "1"/>
    <field
        id = "heat_setpoint_c"
        type = "number"
        label = "Heat Below"
        min = "10"
        max = "32"
        res = "0.5"/>
    <field
        id = "cool_setpoint_f"
        type = "number"
        label = "Cool Above"
        min = "50"
        max = "90"
        res = "1"/>
    <field
        id = "cool_setpoint_c"
        type = "number"
        label = "Cool Above"
        min = "10"
        max = "32"
        res = "0.5"/>
    <field
        id = "humidify_setpoint"
        type = "number"
        label = "Humidify Setpoint"
        min = "0"
        max = "90"
        res = "5"/>
    <field
        id = "dehumidify_setpoint"
        type = "number"
        label = "Dehumidify Setpoint"
        min = "10"
        max = "100"
        res = "5"/>
    <field id = "hvac_mode" type = "list" label = "HVAC Mode">
        <list>
            <item text = "Off" value = "Off"/>
            <item text = "Heat" value = "Heat"/>
            <item text = "Cool" value = "Cool"/>
        </list>
    </field>
    <field id = "humidity_mode" type = "list" label = "Humidity Mode">
        <list>
            <item text = "Off" value = "Off"/>
            <item text = "Humidify" value = "Humidify"/>
            <item text = "Dehumidify" value = "Dehumidify"/>
            <item text = "Auto" value = "Auto"/>
        </list>
    </field>
    <field id = "fan_mode" type = "list" label = "Fan Mode">
        <list>
            <item text = "On" value = "On"/>
            <item text = "Auto" value = "Auto"/>
            <item text = "Circulate" value = "Circulate"/>
        </list>
    </field>
</preset_fields>

```