# Zigbee Sensor Data Documentation

## Overview

This repository contains structured Zigbee data logs related to water quality monitoring. The data is structured with various fields following Zigbee Cluster Library standards, including different sensor readings, requests, and responses.

## Data Structure

Each data entry contains the following fields:

- **FrameCtrlId**: Frame control identifier.
- **DestinationEndpoint**: The endpoint where the data is sent.
- **ClusterID**: Identifies the cluster.
- **ProfileID**: Profile identifier.
- **SourceEndpoint**: The originating endpoint.
- **Counter**: Message counter.
- **FrameCtrlFld**: Frame control field.
- **TransactionSeqNum**: Transaction sequence number.
- **CmdIdentifier**: Command identifier.
- **SourceID**: Source identifier.
- **Sequence**: Sequence number.
- **DataPointID**: Data point identifier.
- **DataType**: Type of data.
- **Data Length**: Length of the data.
- **Data**: The actual data value.
- **Description**: Explanation of the data entry.

## Example Entries

### Data Query

```
FrameCtrlId: 0x00
DestinationEndpoint: 0x01
ClusterID: 0x00
ProfileID: 0xef
SourceEndpoint: 0x04
Counter: 0x01
FrameCtrlFld: 0x01
TransactionSeqNum: 0x18
CmdIdentifier: 0x11
SourceID: 0x3f
Sequence: 0x03
```

### Data Report (TDS Sensor)

```
FrameCtrlId: 0x00
DestinationEndpoint: 0x01
ClusterID: 0x00
ProfileID: 0xef
SourceEndpoint: 0x04
Counter: 0x01
FrameCtrlFld: 0x01
TransactionSeqNum: 0x7a
CmdIdentifier: 0x09
SourceID: 0x46
Sequence: 0x02
DataPointID: 0x71
DataType: 0x01
Data Length: 0x02
Data: 0x00 0x04 0x00 0x00 0x00 0x00
Description: TDS Measurement
```

## Notable Data Points

| DataPointID | Parameter        | Validity      |
| ----------- | ---------------- | ------------- |
| 0x71        | TDS              | Not Confirmed |
| 0x72        | Temperature      | Valid         |
| 0x73        | Battery %        | Valid         |
| 0x74        | pH               | Valid         |
| 0x75        | EC               | Valid         |
| 0x76        | ORP              | Valid         |
| 0x77        | Chlorine         | Valid         |
| 0x78        | pH Buffer Select | Valid         |
| 0x79        | Backlight        | Not Confirmed |
| 0x7A        | Backlight Value  | Valid         |
| 0x7B        | pH Max Value     | Valid         |
| 0x7C        | pH Min Value     | Valid         |

## Usage

This dataset can be used to analyze sensor performance, validate readings, and understand the communication structure of Zigbee-based water quality monitoring devices.

## License

This project is licensed under the MIT License.

