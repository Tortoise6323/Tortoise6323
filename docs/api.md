---
title: Application Programming Interface
---

## Outgoing Messages

*Broadcast sensor data*  
This message type broadcasts all sensor data.

.             | byte 1   | byte 2     | byte 3-4
--------------|----------|------------|-----------
Variable Name | msg_type | sensor_num | sensor_val
Variable Type | uint8_t  | uint8_t    | uint16_t
Min Value     | 1        | 1          | -40
Max Value     | 1        | 4          | 1300
Example       | 1        | 3          | 37

Sensors      | Number | Data Min | Data Max
-------------|--------|----------|---------
wind speed   | 1      | 0        | 100
temperature  | 2      |-40       | 85
humidity     | 3      | 20       | 80
air pressure | 4      | 10       | 1300

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

## MPLabX Code

[Software](./assets/source_docs/sensorSuite.zip)
