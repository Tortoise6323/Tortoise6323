---
title: Application Programming Interface
---

## Team Member IDs

Name    | Subsystem | Address
--------|-----------|--------
Aarshon | HMI       | `0x61 'a'`
Alex    | Motor     | `0x63 'c'`
Ian     | Sensor    | `0x69 'i'`
KD      | Websocket | `0x6B 'k'`
Broadcast |         | `0x58 'X'`

## Outgoing Messages

*Broadcast sensor data*  
This message type broadcasts all sensor data.  
uint16_t is in big endian form

.             | byte 1    | byte 2     | byte 3-4
--------------|-----------|------------|-----------
Variable Name | msg_type  | sensor_num | sensor_val
Variable Type | `uint8_t` | `uint8_t`  | `uint16_t`
Min Value     | 1 `0x31`  | 1 `0x31`   | -40
Max Value     | 1 `0x31`  | 4 `0x34`   | 1300
Example       | 1 `0x31`  | 3 `0x33`   | 37

Sensors      | Number   | Data Min | Data Max
-------------|----------|----------|---------
wind speed   | 1 `0x31` | 0        | 100
temperature  | 2 `0x32` |-40       | 85
humidity     | 3 `0x33` | 20       | 80
air pressure | 4 `0x34` | 10       | 1300

Sender | Destination
---|---
Ian `'i'` | Broadcast `'X'`

*Subsystem Error Code*  
This message type sends an error code corresponding to the amount of current functionality.

.             | byte 1   | byte 2
--------------|----------|---------
Variable Name | msg_type | err_code
Variable Type | `char`   | `uint8_t`
Min Value     | 4 `0x34` | 0 `0x30`
Max Value     | 4 `0x34` | 2 `0x32`
Example       | 4 `0x34` | 1 `0x31`

Senders | Destination
---|---
Alex `'c'`<br>Ian `'i'`<br>Kushagra `'k'` | Aarshon `'a'`

*Subsystem Error Message*  
This message type sends a description about specific system errors

.             | byte 1   | byte 2-58
--------------|----------|----------
Variable Name | msg_type | err_msg
Variable Type | `char`   | char array (`uint8_t`)
Min Value     | 5 `0x35` | char[1]
Max Value     | 5 `0x35` | char[57]
Example       | 5 `0x35` | "sensor 1 read error"

Senders | Destination
---|---
Alex `'c'`<br>Ian `'i'`<br>Kushagra `'k'` | Aarshon `'a'`

## Received Messages

There are no message types that concern this subsystem as a recipient.

## MPLabX Code

[Software](./assets/source_docs/sensorSuite.zip)
