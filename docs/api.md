---
title: Application Programming Interface
---

## Outgoing Messages

*Broadcast sensor data*  
This message type broadcasts all sensor data.

.             | byte 1   | byte 2-3   | byte 4-5    | byte 6-7 | byte 8-9
--------------|----------|------------|-------------|----------|---------
Variable Name | msg_type | wind_speed | temperature | humidity | air_press
Variable Type | uint8_t  | uint16_t   | uint16_t    | uint16_t | uint16_t
Min Value     | 1        | 0          | -40         | 20       | 10
Max Value     | 1        | 100        | 85          | 80       | 1300
Example       | 1        | 15         | 25          | 43       | 1013

*Subsystem Error Code*  
This message type sends an error code corresponding to the amount of current functionality.

.             | byte 1   | byte 2     | byte 3
--------------|----------|------------|--------
Variable Name | msg_type | system_num | err_code
Variable Type | uint8_t  | uint8_t    | uint8_t
Min Value     | 4        | 0          | 0
Max Value     | 4        | 3          | 2
Example       | 4        | 1          | 2

*Subsystem Error Message*  
This message type sends a description about specific system errors

.             | byte 1   | byte 2-58
--------------|----------|----------
Variable Name | msg_type | err_msg
Variable Type | uint8_t  | char array (uint8_t)
Min Value     | 5        | char[1]
Max Value     | 5        | char[57]
Example       | 5        | "sensor 1 read error"

## Received Messages

There are no message types that concern this subsystem as a recipient.
