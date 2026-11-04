
## UPDATE_SCHEDULE_ENTRY_ENABLED_FLAG

New to 4.3.0. Updates the enabled state of a single schedule entry for one day.


### Name
UPDATE_SCHEDULE_ENTRY_ENABLED_FLAG ()

  

| Parameter     | Type | Description                                                     |
| ------------- | ---- | --------------------------------------------------------------- |
| `ENTRY_INDEX` | INT  | Required. The schedule entry index to enable/disable the entry. |
| `DAY_INDEX`   | INT  | Required. The schedule day index to enable/disable the entry.   |
| ENABLED_FLAG  | BOOL | True/False.  Enable or Disables a schedule entry.               |


### Command Sent to Protocol Driver

`UPDATE_SCHEDULE_ENTRY_ENABLED_FLAG` -  sends the schedule entry enabled flag to the protocol driver with the relevant `DAY_INDEX`, `ENTRY_INDEX` and ENABLED_FLAG  values.

### Returns

`None`

