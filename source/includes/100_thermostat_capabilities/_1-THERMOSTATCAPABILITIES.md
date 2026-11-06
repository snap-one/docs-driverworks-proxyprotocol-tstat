## THERMOSTAT CAPABILITIES

The following Capabilities are supported with the Thermostat Proxy. 

Note the reference to the [Dynamic Capabilities Changed][1] notification in many of the capabilities defined below. Using the Dynamic Capabilities notify  is a way for a protocol driver to send updates about some capabilities that can be changed when settings change on the hardware.  An example would be a thermostat that now includes a humidifier. The thermostat would need to tell the proxy it can now do humidification. The  `<can_humidify></can_humidify>`  capability is designated as  a capability that can be changed using Dynamic Capabilities Changed. The capability can be passed as a parameter in the notify to update the thermostat proxy regarding humidification ability.

Additionally, please see the Samples folder delivered in this SDK for additional Thermostat (V2) code examples.

### can_calibrate
Indicates if the device is capable of calibrating itself. Enables the [SET_CALIBRATION][2] command. Valid values: True/False.



### can_change_scale
Boolean to enable/disable Navigator UIs and ComposerPro from being able to change the scale of the hardware. Valid values: True/False. This capability can be changed through the [`CAN_CHANGE_SCALE` ][4] dynamic notification.



### can_cool
Indicates if this thermostat supports cooling and indicates to UIs and Programming that the device could execute this functionality. Valid values: True/False. This capability can be changed through the [`CAN_COOL` ][5] dynamic notification.


### can_dehumidify
Boolean to enable/disable `can_dehumidity` capability, if the device supports this feature, default is True. This capability can be changed through the [`CAN_DEHUMIDIFY` ][6] dynamic notification. This is older functionality that indicated to UI's and Programming that the device could execute this functionality.  However, their limitation is that they do not take into account if the current HVAC mode supported them.  HVAC Modes replaced their functionality, but older drivers still use them and they do work. Control4  recommends the use of HVAC Modes now and that this capability be set to false in the driver's configuration file.


### can_do_auto
 Indicates if this thermostat can automatically switch from heat to cool and indicates to UIs and Programming that the device could execute this functionality. If the device can deadband enforcement, it will be done on the UIs as specified with the deadband capabilities. Valid values: True/False. This capability can be changed through the [`CAN_AUTO` ][3] dynamic notification.


### can_fixed_schedule_and_presets
Introduced in 4.3.0. Indicates support for both the legacy schedule plus presets. When `<can_fixed_schedule_and_presets>` is true then `<can_preset>` and `<can_preset_schedule>` should be set to false. This capability allows the driver to use the legacy scheduler along with supporting presets. This capability can be changed through the [`CAN_FIXED_SCHEDULE_AND_PRESETS` ][7] dynamic notification.


### can_heat
Indicates if this thermostat supports heating  and indicates to UIs and Programming that the device could execute this functionality. Valid values: True/False. This capability can be changed through the [`CAN_HEAT` ][8] dynamic notification.


### can_humidify
Boolean to enable/disable `can_humidity` capability, if the device supports this feature, default is True. It indicates to UIs and Programming that the device could execute this functionality. This capability can be changed through the [`CAN_HUMIDIFY` ][9] dynamic notification. 


### can_inc_dec_setpoints
Boolean indicating if the device has internal commands to increment and decrement both heat and cool set points independently. If false the proxy will take the current setpoint and +/- 1 (or the resolution) and adjust the setpoint accordingly. If true, the command is passed on to the protocol driver. The following commands use this capability; [DEC_SETPOINT_COOL][60], [DEC_SETPOINT_HEAT][61], [DEC_SETPOINT_SINGLE][62], [INC_SETPOINT_COOL][63], [INC_SETPOINT_HEAT][64] and [INC_SETPOINT_SINGLE][65].


### can_lock_buttons
 Indicates if the buttons on the TSTAT can be locked out to prevent changes. Valid values: True/False.


### can_lock_screen
Introduced in 4.3.0. Indicates if the screen on the thermostat device is able to be locked. The modes that are supported are provided by the `<lock_screen_modes>` capability. This capability can be changed through the [`CAN_LOCK_SCREEN` ][10] dynamic notification.


### can_preset
Boolean indicating if the device supports the preset functionality including `custom_fields`. This capability can be changed through the [`CAN_PRESET` ][11] dynamic notification.


### can_preset_schedule
Boolean indicating if the thermostat will support the `SET_EVENTS` commands for running presets based on scheduling created in Navigators. This capability can be changed through the [`CAN_PRESET_SCHEDULE` ][12] dynamic notification.


### current_temperature_max_c
Double indicating the maximum temperature that the thermostat will report in C. Default is 48. This capability can be changed through the [`TEMPERATURE_MAX_C` ][53] dynamic notification.


### current_temperature_max_f
Double indicating the maximum temperature that the thermostat will report in F. Default is 120. This capability can be changed through the [`TEMPERATURE_MAX_F` ][54] dynamic notification.


### current_temperature_min_c
Double indicating the minimum temperature that the thermostat will report in C. Default is -40. This capability can be changed through the [`TEMPERATURE_MIN_C` ][55] dynamic notification.


### current_temperature_min_f
Double indicating the minimum temperature that the thermostat will report in F. Default is -40. This capability can be changed through the [`TEMPERATURE_MIN_F` ][56] dynamic notification.


### current_temperature_resolution_c
Double indicating the increments that the temperature will follow, such as .1, .5, 1, 2, 5, etc. Default is 1. This capability can be changed through the [`TEMPERATURE_RESOLUTION_C` ][57]notification.


### current_temperature_resolution_f
Double indicating the increments that the temperature will follow, such as .2, .5, 1, 2, 5, etc. Default is 1. Note .2 is the lowest F resolution supported. This capability can be changed through the [`TEMPERATURE_RESOLUTION_F` ][58] dynamic notification.


### fan_modes
This is a comma delimited list of possible fan modes this thermostat supports. For example: Auto, Low, Medium, High with no spaces after the comma. This capability can be changed through the [`ALLOWED_FAN_MODES_CHANGED` ][59] notification.


### fan_states
This is a comma delimited list of all the possible states that the HVAC system fan supports. For example: Off, On, Low, Med, Circulate with no spaces after the commas. This is a static capability and must be set in the driver.xml file.


### has_connection_status
Boolean indicating if the device reports online/offline status of the hardware device, this is often forgotten about but very important to implement in new protocol drivers drivers.


### has_extras
Boolean indicating if the device has extras commands support. This capability can be changed through the [`HAS_EXTRAS` ][22] dynamic notification.


### has_humidity
Boolean indicating if the device can report the current humidity. This capability can be changed through the [`HAS_HUMIDITY` ][24] dynamic notification.


### has_outdoor_temperature
Boolean indicating if the device can provide an outdoor temperature. This capability can be changed through the [`HAS_OUTDOOR_TEMPERATURE` ][25] dynamic notification.


### has_remote_sensor
Indicates if this thermostat has a remote sensor. Valid values: True/False.


### has_single_setpoint
 Boolean indicating if the device is single setpoint.  `can_heat, can_cool` and `can_auto` should be set to false if this option is used. It indicates to UIs and Programming that the device could execute this functionality.  This capability can be changed through the [`HAS_SINGLE_SETPOINT` ][27] dynamic notification. 


### has_temperature
Boolean indicating if the device can provide a temperature of the thermostat/room. This capability can be changed through the [`HAS_TEMPERATURE` ][28] dynamic notification.


### has_vacation_mode
Vacation support has been deprecated. This capability should always be set to false.


### hold_modes
This is a comma delimited list of the possible hold modes this thermostat supports. Valid values include: Off, 2 Hours, Until Next, Permanent with no spaces after the commas. This capability can be changed through the [`ALLOWED_HOLD_MODES_CHANGED` ][66] notification.


### hold_until_mode
Introduced in 4.3.0. Controls whether Hold Until uses `time` semantics or `date,time` semantics. The default is `date,time`. Some thermostats only supports setting the hold until mode within a 24 hour period and only supplies the time. If this is the case then set `<hold_until_mode>` to "time". This capability can be changed through the [`HOLD_UNTIL_MODE` ][37] dynamic notification.


### hold_until_resolution
Introduced in 4.3.0. Minute resolution used for Hold Until rounding and UI input behavior. Double indicating the increments that the hold_until  will follow, such as 1, .5, 10 etc. Default is 5. This capability can be changed through the [`HOLD_UNTIL_RESOLUTION` ][38] dynamic notification.


### humidity_modes
A comma separated list of all the modes the device supports. For example: "Off,Humidify,Dehumidify,Auto" with no spaces after the commas. This capability can be changed through the [`ALLOWED_HUMIDITY_MODES_CHANGED` ][67] dynamic notification.


### humidity_states
 A comma separated list of all the modes the device supports. Usually something like "Off,Humidifying,Dehumidifying", with no spaces after the commas.


### hvac_modes
A comma separated list of all the modes the device supports. For example:  "Off,Heat,Cool", with no spaces after the commas.


### hvac_states
This is a comma delimited list that represents all of the possible states that the HVAC system supports. For example: Off, Heat, Cool, Heating, Stage 1 Cool, etc with no spaces after the commas


### lock_screen_modes
Introduced in 4.3.0. This is a comma delimited (no spaces) list of the possible lock screen modes this thermostat supports. V This capability can be changed through the [`LOCK_SCREEN_MODES` ][44] notification.


### outdoor_temperature_resolution_c
Double indicating the increments that the temperature will follow, such as .2, .5, 1, 2, 5, etc. Default is 1. Note that .2 is the lowest C resolution supported. This capability can be changed through the [`OUTDOOR_TEMPERATURE_RESOLUTION_C` ][45] dynamic notification.


### outdoor_temperature_resolution_f
Double indicating the increments that the temperature will follow, such as .2, .5, 1, 2, 5, etc. Default is 1. Note .2 is the lowest F resolution supported. This capability can be changed through the [`OUTDOOR_TEMPERATURE_RESOLUTION_F` ][46] dynamic notification.


### preset_fields
XML of fields for settings that are potentially unique to the protocol driver, yet will be displayed in the UI during the creation or modification of presets for scheduling. This capability can be changed through the [`PRESET_FIELDS_CHANGED` ][68] dynamic notification.


### schedule_default
An XML block indicating the default schedule for the device.  Legacy scheduling is mutually exclusive to preset scheduling unless `can_fixed_schedule_and_presets` is true which was introduced in 4.3.0. In 4.3.0, `scheduling` and `schedule_default` can be handled dynamically. If either capability is missing from the static capability set, thermostatV2 proxy treats it through the dynamic capability flow. If `scheduling` is true and the driver is not providing `schedule_default` through that dynamic flow, the driver should provide a `schedule_default` block in `driver.xml`. See the example below.


```xml
<schedule_default>
    <schedule_day_info Entries = "6" DefaultHeat = "200" DefaultCool = "278">
        <schedule_entry Name = "Wake" Time = "360" Enabled = "True" CanChangeName="False" CanDelete="False"/>
        <schedule_entry Name = "Leave" Time = "480" Enabled = "True" CanChangeName="False" CanDelete="False"/>
        <schedule_entry Name = "Return" Time = "1080" Enabled = "True" CanChangeName="False" CanDelete="False"/>
        <schedule_entry Name = "Sleep" Time = "1320" Enabled = "True" CanChangeName="False" CanDelete="False"/>
        <schedule_entry Name = "Custom 1" Time = "1380" Enabled = "False" CanChangeName="True" CanDelete="True"/>
        <schedule_entry Name = "Custom 2" Time = "1380" Enabled = "False" CanChangeName="True" CanDelete="True"/>
    </schedule_day_info>
</schedule_default>
```

#### Example of driver providing the schedule default

```lua
local DEFAULT_SCHEDULE_ENTRIES = {
    { EntryIndex = 1, TimeHour = 6, TimeMinute = 0, Enabled = true, HeatSetpoint = 70, CoolSetpoint = 74, Scale = "F", CanChangeName = false, CanDelete = false, EntryName = "Wake" },
    { EntryIndex = 2, TimeHour = 9, TimeMinute = 0, Enabled = true, HeatSetpoint = 71, CoolSetpoint = 75, Scale = "F", CanChangeName = false, CanDelete = false, EntryName = "Away" },
    { EntryIndex = 3, TimeHour = 16, TimeMinute = 0, Enabled = true, HeatSetpoint = 72, CoolSetpoint = 76, Scale = "F", CanChangeName = false, CanDelete = false, EntryName = "Home" },
    { EntryIndex = 4, TimeHour = 22, TimeMinute = 0, Enabled = true, HeatSetpoint = 73, CoolSetpoint = 77, Scale = "F", CanChangeName = false, CanDelete = false, EntryName = "Sleep" },
    { EntryIndex = 5, TimeHour = 22, TimeMinute = 40, Enabled = true, HeatSetpoint = 74, CoolSetpoint = 78, Scale = "F", CanChangeName = true, CanDelete = true, EntryName = "Custom 1" },
    { EntryIndex = 6, TimeHour = 23, TimeMinute = 0, Enabled = true, HeatSetpoint = 75, CoolSetpoint = 79, Scale = "F", CanChangeName = true, CanDelete = true, EntryName = "Custom 2" }
}

function SetDefaultSchedule()
    for dayIndex = 0, 6 do
        for _, entry in ipairs(DEFAULT_SCHEDULE_ENTRIES) do
            SetScheduleEntry(
                dayIndex,
                entry.EntryIndex,
                entry.TimeHour,
                entry.TimeMinute,
                entry.Enabled,
                entry.HeatSetpoint,
                entry.CoolSetpoint,
                entry.Scale,
                entry.CanChangeName,
                entry.CanDelete,
                entry.EntryName
            )
        end
    end
end

function SetScheduleEntry(dayOfWeek, entryIndex, timeHour, timeMinute, isEnabled, heatSetpoint, coolSetpoint, scale, canChangeName, canDelete, entryName)
    LogTrace("SetScheduleEntry  %s %s %s %s %s %s %s %s %s %s %s", tostring(dayOfWeek), tostring(entryIndex), tostring(timeHour), tostring(timeMinute), tostring(isEnabled), tostring(heatSetpoint), tostring(coolSetpoint), tostring(scale), tostring(canChangeName), tostring(canDelete), tostring(entryName))

    local zeroBasedEntryIndex = tonumber(entryIndex)
    if(zeroBasedEntryIndex == nil) then
        zeroBasedEntryIndex = 1
    end
    zeroBasedEntryIndex = zeroBasedEntryIndex - 1

    local params = {
        DayIndex = tostring(dayOfWeek),
        EntryIndex = tostring(zeroBasedEntryIndex),
        EnabledFlag = tostring(isEnabled),
        TimeMinutes = tostring((tonumber(timeHour) or 0) * 60 + (tonumber(timeMinute) or 0)),
        HeatSetpoint = tostring(heatSetpoint),
        CoolSetpoint = tostring(coolSetpoint),
        Units = tostring(scale)
    }

    if(canChangeName ~= nil) then
        params.CanChangeName = tostring(toboolean(canChangeName))
    end

    if(canDelete ~= nil) then
        params.CanDelete = tostring(toboolean(canDelete))
    end

    if(entryName ~= nil and tostring(entryName) ~= "") then
        params.EntryName = tostring(entryName)
    end

    SendNotify("SCHEDULE_ENTRY_CHANGED", params, 5001)

    if(type(UpdateScheduleEntryCapabilityTracking) == "function") then
        UpdateScheduleEntryCapabilityTracking(zeroBasedEntryIndex, entryName, canChangeName, canDelete)
    end
end
```

### schedule_entry
There is one `<schedule_entry>` for each schedule entry during the day. Each entry attribute defines that entry. The following table describes each of the potential attributes. CanChangeName and CanDelete were added in OS Release 4.3.0.

| Attribute     | Version | Value      | Description                                                                                                                                   |
| ------------- | ------- | ---------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| Name          |         | String     | Indicates the name of the entry that will show up in composer and navigator.                                                                  |
| Time          |         | Number     | Indicates the name of the entry that will show up in composer and navigator. The time units are minutes since midnight, so 360 means 6:00 AM. |
| Enabled       |         | True/False | Indicates whether or not this entry is initially enabled or not.                                                                              |
| CanChangeName | 4.3.0   | True/False | Indicates whether or not this entry name can be changed. This is optional. Default is False.                                                  |
| CanDelete     | 4.3.0   | True/False | Indicates whether or not this entry can be deleted. This is optional. Default is False.                                                       |

In the example used here, there are six schedule entries.

```xml
<schedule_day_info>
   <schedule_entry Name="Awake" Time="360" Enabled="True" CanChangeName="False" CanDelete="False" />
   <schedule_entry Name="Leave" Time="480" Enabled="True" CanChangeName="False" CanDelete="False" />
   <schedule_entry Name="Return" Time="1080" Enabled="True" CanChangeName="False" CanDelete="False" />
   <schedule_entry Name="Sleep" Time="1320" Enabled="True" CanChangeName="False" CanDelete="False" />
   <schedule_entry Name="Custom 1" Time="1380" Enabled="False" CanChangeName="True" CanDelete="True" />
   <schedule_entry Name="Custom 2" Time="1380" Enabled="False" CanChangeName="True" CanDelete="True" />
</schedule_day_info>
```

### scheduling
A boolean indicating if the device supports a programmed schedule. If it is true, it should have a `schedule_default` entry in the capabilities section in the driver.xml file. Mutually exclusive to Preset Scheduling unless `can_fixed_schedule_and_presets` is true. In 4.3.0, `scheduling` and `schedule_default` can be handled dynamically. If either capability is missing from the static capability set, thermostatV2 proxy treats it through the dynamic capability flow. If `scheduling` is true and the driver is not providing `schedule_default` through that dynamic flow, the driver should provide a `schedule_default` block in `driver.xml`.


### setpoint_cool_max
Integer indicating the highest temperature the cool setpoint can be configured as. Default is 89. If used,`_f `and `_c` do not need to be set but since this value is Celsius x 10, it will result in a potentially undesired Fahrenheit conversion.  This capability can be changed through the [`COOL_SETPOINT_MAX_C` ][13] dynamic notification.


### setpoint_cool_max_c
Integer indicating the highest temperature the cool setpoint can be configured as. Default is 90. This capability can be changed through the [`COOL_SETPOINT_MAX_C` ][13] dynamic notification.



### setpoint_cool_max_f
Integer indicating the highest temperature the cool setpoint can be configured as. Default is 89. This capability can be changed through the [`COOL_SETPOINT_MAX_F` ][14] dynamic notification.


### setpoint_cool_min
Integer indicating the lowest temperature the cool setpoint can be configured as. Default is 39. If used,`_f` and `_c` do not need to be set but since this value is Celsius x 10 it will result in a potentially undesired Fahrenheit conversion. This capability can be changed through the [`COOL_SETPOINT_MIN_C` ][15] dynamic notification.


### setpoint_cool_min_c
 Integer indicating the lowest temperature the cool setpoint can be configured as. Default is 42. If used, `_f` and `_c` do not need to be set but since this value is Celsius x 10 it will result in a potentially undesired Fahrenheit conversion. This capability can be changed through the [`COOL_SETPOINT_MIN_C` ][15] dynamic notification.


### setpoint_cool_min_f
Integer indicating the lowest temperature the cool setpoint can be configured as. Default is 42. This capability can be changed through the [`COOL_SETPOINT_MIN_F` ][16] dynamic notification.


### setpoint_cool_resolution_c
Double indicating the increments that the setpoint will follow, such as .1, .5, 1, 2, 5, etc. Default is 1. This capability can be changed through the [`COOL_SETPOINT_RESOLUTION_C` ][17] dynamic notification.


### setpoint_cool_resolution_f
Double indicating the increments that the setpoint will follow, such as .1, .5, 1, 2, 5, etc. Default is 1. This capability can be changed through the [`COOL_SETPOINT_RESOLUTION_F` ][18] dynamic notification.


### setpoint_dehumidify_max
Integer indicating the highest dehumidify setpoint, default 100.  This capability can be changed through the [`DEHUMIDIFY_SETPOINT_MAX` ][19] dynamic notification.


### setpoint_dehumidify_min
Integer indicating the lowest dehumidify setpoint, default 0.  This capability can be changed through the [`DEHUMIDIFY_SETPOINT_MIN` ][20] dynamic notification.


### setpoint_dehumidify_resolution
 Integer indicating the increments that the setpoint will follow, Default is 1. This capability can be changed through the [`DEHUMIDIFY_SETPOINT_RESOLUTION` ][21] dynamic notification.


### setpoint_heat_max
Integer indicating the highest temperature the heat setpoint can be configured as. Default is 88. If used, `_f `and`_c` do not need to be set but since this value is Celsius x 10 it will result in a potentially undesired Fahrenheit conversion. This capability can be changed through the [`HEAT_SETPOINT_MAX_C` ][31] dynamic notification.


### setpoint_heat_max_c
Integer indicating the highest temperature the heat setpoint can be configured as. Default is 31. Best to use `_f `and `_c` and not the older celsius x 10 capability.  This capability can be changed through the [`HEAT_SETPOINT_MAX_C` ][31] dynamic notification.


### setpoint_heat_max_f
Integer indicating the highest temperature the heat setpoint can be configured as. Default is 89. Best to use `_f `and `_c` and not the older celsius x 10 capability.  This capability can be changed through the [`HEAT_SETPOINT_MAX_F` ][32] dynamic notification.


### setpoint_heat_min
Integer indicating the lowest temperature the heat setpoint can be configured as. Default is 40. If used, `_f` and `_c `do not need to be set but since this value is Celsius x 10 it will result in a potentially undesired Fahrenheit conversion. This capability can be changed through the [`HEAT_SETPOINT_MIN_C` ][33] dynamic notification.


### setpoint_heat_min_c
Integer indicating the lowest temperature the heat setpoint can be configured as. Default is 4. Best to use `_f` and `_c` and not the older Celsius x 10 capability. This capability can be changed through the [`HEAT_SETPOINT_MIN_C` ][33] dynamic notification.


### setpoint_heat_min_f
Integer indicating the lowest temperature the heat setpoint can be configured as. Default is 38. Best to use `_f` and `_c` and not the older celsius x 10 capability. This capability can be changed through the [`HEAT_SETPOINT_MIN_F` ][34] dynamic notification.


### setpoint_heat_resolution_c
Double indicating the increments that the setpoint will follow, such as .1, .5, 1, 2, 5, etc. Default is 1. This capability can be changed through the [`HEAT_SETPOINT_RESOLUTION_C` ][35] dynamic notification.


### setpoint_heat_resolution_f
Double indicating the increments that the setpoint will follow, such as .1, .5, 1, 2, 5, etc. Default is 1. This capability can be changed through the [`HEAT_SETPOINT_RESOLUTION_F` ][36] dynamic notification.


### setpoint_heatcool_deadband_c
Double indicating the deadband range in Celcius that the hardware requires between heat and cool.  Default is 2.  Default is 2.  Post operating system 2.7.0, UI's will show both heat and cool setpoints moving if in Auto and the movement will be based on this deadband value. If a user tries to move heat above cool or cool below heat, the UI's will only send the setpoint command for the primarily moving setpoint.  A protocol driver will need to send two notifies back, one for heat and one for cool if in fact both setpoints were changed on the hardware. This capability can be changed through the [`HEATCOOL_SETPOINTS_DEADBAND_C` ][29] dynamic notification.


### setpoint_heatcool_deadband_f
Double indicating the deadband range in Fahrenheit  that the hardware requires between heat and cool.  Default is 2.  Post operating system 2.7.0, UI's will show both heat and cool setpoints moving if in Auto and the movement will be based on this deadband value. If a user tries to move heat above cool or cool below heat, the UI's will only send the setpoint command for the primarily moving setpoint.  A protocol driver will need to send two notifies back, one for heat and one for cool if in fact both setpoints were changed on the hardware. This capability can be changed through the [`HEATCOOL_SETPOINTS_DEADBAND_F` ][30] dynamic notification.


### setpoint_humidify_max
Integer indicating the highest humidify setpoint, default 100. This capability can be changed through the [`HUMIDIFY_SETPOINT_MAX` ][40] dynamic notification.


### setpoint_humidify_min
Integer indicating the lowest humidify setpoint, default 0. This capability can be changed through the [`HUMIDIFY_SETPOINT_MIN` ][41] dynamic notification.


### setpoint_humidify_resolution
Integer indicating the increments that the setpoint will follow, Default is 1. This capability can be changed through the [`HUMIDIFY_SETPOINT_RESOLUTION` ][42] dynamic notification.


### setpoint_humidity_deadband
Integer indicating the deadband that the hardware requires between the humidify and dehumidify setpoints. Default is 5. This capability can be changed through the [`HUMIDIFY_SETPOINT_RESOLUTION` ][42] dynamic notification.


### setpoint_single_max_c
Integer indicating the highest temperature the single setpoint can be configured as. Default is 32. This capability can be changed through the [`SINGLE_SETPOINT_MAX_C` ][47] dynamic notification.


### setpoint_single_max_f
Integer indicating the highest temperature the single setpoint can be configured as. Default is 90. This capability can be changed through the [`SINGLE_SETPOINT_MAX_F` ][48] dynamic notification.


### setpoint_single_min_c
Integer indicating the lowest temperature the single setpoint can be configured as. Default is 4. This capability can be changed through the [`SINGLE_SETPOINT_MIN_C` ][49] dynamic notification.


### setpoint_single_min_f
Integer indicating the lowest temperature the single setpoint can be configured as. Default is 38. This capability can be changed through the [`SINGLE_SETPOINT_MIN_F` ][50] dynamic notification.


### setpoint_single_resolution_c
Double indicating the increments that the setpoint will follow, such as .2, .5, 1, 2, 5, etc. Default is 1. Note .2 is the lowest F resolution supported. This capability can be changed through the [`SINGLE_SETPOINT_RESOLUTION_C` ][51] dynamic notification.


### setpoint_single_resolution_f
Double indicating the increments that the setpoint will follow, such as .2, .5, 1, 2, 5, etc. Default is 1. Note .2 is the lowest F resolution supported. This capability can be changed through the [`SINGLE_SETPOINT_RESOLUTION_F` ][52] dynamic notification.


[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-dynamic_capabilities_changed
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-proxy-commands-set_calibration
[3]:  https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-can_auto
[4]:  https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-can_change_scale
[5]:  https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-can_cool
[6]:  https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-can_dehumidify
[7]:  https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-can_fixed_schedule_and_presets
[8]:  https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-can_heat
[9]:  https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-can_humidify
[10]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-can_lock_screen
[11]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-can_preset
[12]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-can_preset_schedule
[13]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-cool_setpoint_max_c
[14]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-cool_setpoint_max_f
[15]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-cool_setpoint_min_c
[16]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-cool_setpoint_min_f
[17]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-cool_setpoint_resolution_c
[18]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-cool_setpoint_resolution_f
[19]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-dehumidify_setpoint_max
[20]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-dehumidify_setpoint_min
[21]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-dehumidify_setpoint_resolution
[22]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-has_extras
[24]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-has_humidity
[25]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-has_outdoor_temperature
[26]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-has_schedule
[27]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-has_single_setpoint
[28]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-has_temperature
[29]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-heatcool_setpoints_deadband_c
[30]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-heatcool_setpoints_deadband_f
[31]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-heat_setpoint_max_c
[32]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-heat_setpoint_max_f
[33]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-heat_setpoint_min_c
[34]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-heat_setpoint_min_f
[35]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-heat_setpoint_resolution_c
[36]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-heat_setpoint_resolution_f
[37]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-hold_until_mode
[38]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-hold_until_resolution
[40]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-humidify_setpoint_max
[41]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-humidify_setpoint_min
[42]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-humidify_setpoint_resolution
[44]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-lock_screen_modes
[45]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-outdoor_temperature_resolution_c
[46]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-outdoor_temperature_resolution_f
[47]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-single_setpoint_max_c
[48]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-single_setpoint_max_f
[49]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-single_setpoint_min_c
[50]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-single_setpoint_min_f
[51]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-single_setpoint_resolution_c
[52]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-single_setpoint_resolution_f
[53]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-temperature_max_c
[54]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-temperature_max_f
[55]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-temperature_min_c
[56]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-temperature_min_f
[57]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-temperature_resolution_c
[58]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-temperature_resolution_f
[59]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-allowed_fan_modes_changed
[60]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-proxy-commands-dec_setpoint_cool
[61]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-proxy-commands-dec_setpoint_heat
[62]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-proxy-commands-dec_setpoint_single
[63]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-proxy-commands-inc_setpoint_cool
[64]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-proxy-commands-inc_setpoint_heat
[65]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-proxy-commands-inc_setpoint_single
[66]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-allowed_hold_modes_changed
[67]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-allowed_humidity_modes_changed
[68]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-preset_fields_changed