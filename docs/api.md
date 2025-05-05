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

### Message Type 1: Sensor Broadcast

This message type broadcasts all sensor data.  
uint16_t is in big endian form

.             | byte 1    | byte 2     | byte 3-4
--------------|-----------|------------|-----------
Variable Name | msg_type  | sensor_num | sensor_val
Variable Type |   `char`  | `uint8_t`  | `uint16_t`
Min Value     | 1 `0x31`  | 1          | -40
Max Value     | 1 `0x31`  | 4          | 1300
Example       | 1 `0x31`  | 3          | 37

Sensors      | Number   | Data Min | Data Max
-------------|----------|----------|---------
wind speed   | 1 `0x01` | 0        | 100
temperature  | 2 `0x02` |-40       | 85
humidity     | 3 `0x03` | 20       | 80
air pressure | 4 `0x04` | 10       | 1300

Sender | Destination
---|---
Ian `'i'` | Broadcast `'X'`

### Message Type 3: Subsystem Error Code

This message type sends an error code corresponding to the amount of current functionality.

.             | byte 1   | byte 2
--------------|----------|---------
Variable Name | msg_type | err_code
Variable Type | `char`   | `uint8_t`
Min Value     | 3 `0x34` | 1 `0x01`
Max Value     | 3 `0x34` | 3 `0x03`
Example       | 3 `0x34` | 1 `0x01`

Senders | Destination
---|---
Alex `'c'`<br>Ian `'i'`<br>Kushagra `'k'` | Aarshon `'a'`

### Message Type 4: Subsystem Error Message

This message type sends a description about specific system errors

.             | byte 1   | byte 2-58
--------------|----------|----------
Variable Name | msg_type | err_msg
Variable Type | `char`   | char array (`uint8_t`)
Min Value     | 4 `0x35` | char[1]
Max Value     | 4 `0x35` | char[57]
Example       | 4 `0x35` | "sensor 1 read error"

Senders | Destination
---|---
Alex `'c'`<br>Ian `'i'`<br>Kushagra `'k'` | Aarshon `'a'`

## Received Messages

There are no message types that concern this subsystem as a recipient.

## MPLabX Code

[Application Workspace](./assets/code/sensorSuite.zip)
