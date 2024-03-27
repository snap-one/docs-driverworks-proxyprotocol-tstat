## INC\_SETPOINT\_COOL

Used to increase the cool set point by 1. This command is handled by the proxy, and ends up creating a `SET_SETPOINT_COOL` command to send to the protocol driver, unless the capability `can_inc_dec_setpoints` is set to true.


### Name

`INC_SETPOINT_COOL ()`


### Parameter

`None`


### Returns

`None`


