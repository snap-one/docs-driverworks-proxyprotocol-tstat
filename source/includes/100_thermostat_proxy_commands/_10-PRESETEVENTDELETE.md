## PRESET\_EVENT\_DELETE

Deletes a Preset Schedule Preset if the protocol driver has the `can_preset_schedule` capability.


### Name

`PRESET_EVENT_DELETE ()`


| Parameter | Type | Description                                                                                                    |
| --------- | ---- | -------------------------------------------------------------------------------------------------------------- |
| NAME      | STR  | Using `""` (an empty string) will match all presets to make deleting all events of a given preset name easier. |
| WEEKDAY   | INT  | 0-6 with Sunday being 0. Using -1 will match any weekday.                                                      |
| HOUR      | INT  | 0-23 Using -1 Will match any Hour.                                                                             |
| MINUTE    | INT  | 0-60 Using -1 will match any Minute.                                                                           |


### Returns

`None`


### Usage Note

Usage Note:

Using `""` for the Preset or -1 for the weekday, hour or minute might be useful for UI's, Agents or Protocol Drivers as when a matching parameter is used you can delete multiple events at once AND only one Notify of the changes that were made are sent rather than causing a notify for each and every modification if they were done one at a time.

