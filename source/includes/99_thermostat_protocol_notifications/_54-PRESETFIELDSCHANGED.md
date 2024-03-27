## PRESET\_FIELDS\_CHANGED

Updates the  Preset FIELDS TEMPLATE that UIs display for a Preset Event. To UI comes through as `preset_fields`.  If this is modified, it is possible that existing presets will have data that is not in compliance. However, a protocol driver can modify this to have new `preset_fields` which are compatible. Do not delete this as Events are erased when presets are deleted. 


### Name

`PRESET_FIELDS_CHANGED ()` 


| Parameter | Type | Description                                                |
| --------- | ---- | ---------------------------------------------------------- |
| XML       | XML  | XML text string of XML matching the Preset Schedule schema |

 

### Returns

`None`

