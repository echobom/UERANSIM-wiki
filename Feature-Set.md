### Overview

UERANSIM implements the following technologies:

1. 5G Standalone UE (3GPP Access)
2. 5G Standalone RAN (CU gNB)

In basic terms, UE can be considered as a mobile phone and RAN as the base station.

### Interfaces

There are 3 main interface in UE/RAN perspective:

1. Control Interface (between RAN and AMF)
2. User Interface (between RAN and UPF)
3. Radio Interface (between UE and RAN)

### Control Plane

Control Plane has 2 interfaces:
1. **NAS** is in control of **UE**
2. **NGAP** is in control of **RAN**.

### NAS Features

We implemented the following features:

- Primary Authentication and Key Agreement
- Security Mode Control
- Identification
- Generic UE Configuration Update (partial)
- Initial and Periodic Registration
- UE and Network initiated De-registration
- UE initiated PDU session establishment
- UE and Network initiated PDU session release
- Service Request
- Paging

Following features are not implemented yet:

- e-Call Inactivity, Notification
- PDU session authorization, modification

For NAS security,

- All integrity and ciphering algorithms are implemented. (IA1, IA2, IA3, EA1, EA2, EA3)
- All primary authentication and key agreement procedures are implemented. (5G AKA, EAP AKA')

For identification,

- NAI and ciphered SUCI are not implemented yet. All other identity types can be used (IMSI, IMEI, IMEISV)

For registration,

- Initial registration, mobility update registration, periodic registration are implemented.
- Emergency registration is not implemented yet.

### NGAP Features

Following features are implemented in NGAP layer:

- PDU Session Resource Setup
- PDU Session Resource Release
- Initial Context Setup
- UE Context Release (NG-RAN node initiated and AMF initiated)
- UE Context Modification
- Initial UE Message
- Paging
- Downlink NAS Transport
- Uplink NAS Transport
- NAS Non Delivery Indication
- Reroute NAS Request
- NG Setup
- Error Indication

### User Plane

Our RAN implements **GTP** protocol for user plane. And Currently only IPv4 is supported.

### Radio Interface

Here's the current status in summary of the 5G New Radio stack:

- **PHY:** Waiting
- **MAC:** Waiting
- **RLC:** Done
- **PDCP:** In Progress
- **RRC:** In Progress
- **SDAP:** Waiting