---
title: Application Programming Interface
---

## Team Member IDs

Name    | Subsystem | Address
--------|-----------|--------
Aarshon | HMI       | `0x61`
Alex    | Motor     | `0x63`
Ian     | Sensor    | `0x69`
KD      | Websocket | `0x6B`

## Outgoing Messages

*Broadcast sensor data*  
This message type broadcasts all sensor data.  
uint16_t is in big endian form

.             | byte 1    | byte 2     | byte 3-4
--------------|-----------|------------|-----------
Variable Name | msg_type  | sensor_num | sensor_val
Variable Type | ``uint8_t`` | ``uint8_t``  | `uint16_t`
Min Value     | 1 `0x49`  | 1 `0x49`   | -40
Max Value     | 1 `0x49`  | 4 `0x52`   | 1300
Example       | 1 `0x49`  | 3 `0x51`   | 37

Sensors      | Number   | Data Min | Data Max
-------------|----------|----------|---------
wind speed   | 1 `0x49` | 0        | 100
temperature  | 2 `0x50` |-40       | 85
humidity     | 3 `0x51` | 20       | 80
air pressure | 4 `0x52` | 10       | 1300

*Subsystem Error Code*  
This message type sends an error code corresponding to the amount of current functionality.

.             | byte 1   | byte 2
--------------|----------|---------
Variable Name | msg_type | err_code
Variable Type | `uint8_t`  | `uint8_t`
Min Value     | 4 `0x52` | 0 `0x48`
Max Value     | 4 `0x52` | 2 `0x50`
Example       | 4 `0x52` | 1 `0x49`

*Subsystem Error Message*  
This message type sends a description about specific system errors

.             | byte 1   | byte 2-58
--------------|----------|----------
Variable Name | msg_type | err_msg
Variable Type | `uint8_t`  | char array (`uint8_t`)
Min Value     | 5 `0x53` | char[1]
Max Value     | 5 `0x53` | char[57]
Example       | 5 `0x53` | "sensor 1 read error"

## Received Messages

There are no message types that concern this subsystem as a recipient.

## MPLabX Code

[Software](./assets/source_docs/sensorSuite.zip)
