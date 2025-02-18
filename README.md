# Zigbee Water EC PH ORP Sensor Data Documentation

## Overview

This repository contains structured Zigbee data logs related to water quality monitoring. The data is structured with various fields following Zigbee Cluster Library standards, including different sensor readings, requests, and responses.

## Data Structure
### Zigbee Application Support Layer

| Frame Control ID | Destination Endpoint | Cluster ID | Profile ID | Source Endpoint | Counter |
| ---------------- | -------------------- | ---------- | ---------- | --------------- | ------- |
| 0x00             | 0x01                 | 0x00 0xef  | 0x04 0x01  | 0x01            | 0x01    |


### Zigbee Cluster Library

```
Command 0x00 to write data
Command 0x02 to read data
```

| Frame Control ID | Transaction Seq Num  | Command Identifier | Source ID  |  Sequence  |
| ---------------- | -------------------- | ------------------ | ---------- | ---------- | 
| 0x09             | 0x46                 | 0x02               | 0x00       | 0x01       |


### Notable Data Points (Payload)

Source? | Sequence | DataPointID | DataType     | Data Length  | Parameter        | Validity      | Notes                 |
| ----- | -------- | ----------- | ------------ | -----------  | ---------------- | ------------- | --------------------- |
| 0x00  | 0x01     | 0x01        | 0x02 (Value) | 0x00 0x04    | TDS              | Not Confirmed | Probably use EC * 0.5 |
| 0x00  | 0x01     | 0x02        | 0x02 (Value) | 0x00 0x04    | Temperature      | Valid         |                       |
| 0x00  | 0x01     | 0x07        | 0x02 (Value) | 0x00 0x04    | Battery %        | Valid         |                       |
| 0x00  | 0x01     | 0x0a        | 0x02 (Value) | 0x00 0x04    | pH               | Valid         |                       |
| 0x00  | 0x01     | 0x0b        | 0x02 (Value) | 0x00 0x04    | EC               | Valid         |                       |
| 0x00  | 0x01     | 0x65        | 0x02 (Value) | 0x00 0x04    | ORP              | Valid         |                       |
| 0x00  | 0x01     | 0x66        | 0x02 (Value) | 0x00 0x04    | Chlorine         | Valid         |                       |
| 0x00  | 0x01     | 0x67        | 0x01 (Bool)  | 0x00 0x01    | pH Buffer Select | Valid         | 0x00 Asia, 0x01 Europe|
| 0x00  | 0x01     | 0x68        | 0x01 (Bool)  | 0x00 0x01    | Backlight        | Not Confirmed |                       |
| 0x00  | 0x01     | 0x69        | 0x02 (Value) | 0x00 0x04    | Backlight Value  | Valid         | LED Indicator         |
| 0x00  | 0x01     | 0x6a        | 0x02 (Value) | 0x00 0x04    | pH Max Value     | Valid         |                       |
| 0x00  | 0x01     | 0x6b        | 0x02 (Value) | 0x00 0x04    | pH Min Value     | Valid         |                       |
| 0x00  | 0x01     | 0x6c        | 0x02 (Value) | 0x00 0x04    | EC Max Val       | Valid         |                       |
| 0x00  | 0x01     | 0x6d        | 0x02 (Value) | 0x00 0x04    | EC Min Val       | Valid         |                       |
| 0x00  | 0x01     | 0x6e        | 0x02 (Value) | 0x00 0x04    | ORP Max Val      | Valid         |                       |
| 0x00  | 0x01     | 0x6f        | 0x02 (Value) | 0x00 0x04    | ORP Min Val      | Valid         |                       |
| 0x00  | 0x01     | 0x70        | 0x02 (Value) | 0x00 0x04    | Chlorine Max Val | Valid         |                       |
| 0x00  | 0x01     | 0x71        | 0x02 (Value) | 0x00 0x04    | Chlorine Min Val | Valid         |                       |
| 0x00  | 0x01     | 0x72        | 0x02 (Value) | 0x00 0x04    | pH Cal Value     | Valid         | Using pH Buffer       |
| 0x00  | 0x01     | 0x73        | 0x02 (Value) | 0x00 0x04    | EC Cal Value     | Valid         | Input Value           |
| 0x00  | 0x01     | 0x74        | 0x02 (Value) | 0x00 0x04    | ORP Cal Value    | VAlid         | Input Value           |
| 0x00  | 0x01     | 0x75        | 0x02 (Value) | 0x00 0x04    | Salinity Value   | Valid         | Input Value           |
| 0x00  | 0x01     | 0x76        | 0x01 (Bool)  | 0x00 0x01    | Reset pH Cal     | Valid         |                       |

## Usage

This dataset can be used to analyze sensor performance, validate readings, and understand the communication structure of Zigbee-based water quality monitoring devices.

