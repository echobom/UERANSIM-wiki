### v3.2.4 Release Notes

#### New Features
- None

#### Improvements
- PDU session status handling in Initial Context Setup and UE Context Release
- "imsi-" prefix handling in UE command line arguments
- Acceptance of IMSI smaller than 15 digits

#### Bug Fixes
- BCD decoding fixed for 5GS Mobile Identity
- SCTP connection reset handling
- RRC initial random ID error fixed
- Empty registration area (TAI list) handling
- Minor typo fix in UE config files

#### Breaking Changes
- None

---

### v3.2.3 Release Notes

#### New Features
- None

#### Improvements
- Automatic IP address detection from interface name for config files

#### Bug Fixes
- IMSI length fixed

#### Breaking Changes
- None

---

### v3.2.2 Release Notes

#### New Features
- NAS replay protection
- NAS count wrapping around handling

#### Improvements
- None

#### Bug Fixes
- Octal litarals removed in YAML parsing

#### Breaking Changes
- Octal litarals removed in YAML parsing

---

### v3.2.1 Release Notes

#### New Features
- Unified Access Control (UAC) implementation
- RRC Establishment Cause handling
- High priority UE configuration

#### Improvements
- None

#### Bug Fixes
- None

#### Breaking Changes
- New UAC fields added to UE config files

---

### v3.2.0 Release Notes

#### New Features
- System Information Broadcast MIB/SIB1
- New PLMN and cell selection mechanism
- New commands and information added to UE Command Line Interface
- Last visited registered TAI, TAI change, and Registration Area handling
- T3511/3512 handling

#### Improvements
- Re-design and implementation of RLS protocol
- RRC connection establishment improvements
- Radio Link Failure handling improvements
- MM state machine behavioral improvements
- MM procedures abnormal case improvements
- Minor logging improvements

#### Bug Fixes
- Protecting initial NAS messages in CM-CONNECTED state

#### Breaking Changes
- Emergency field removed from PDU session configurations in UE config file

---

### v3.1.9 Release Notes

#### New Features
- EAP AKA' implementation

#### Improvements
- Protection of initial NAS messages
- Additional checks for Service Request initiation

#### Bug Fixes
- Session and UE AMBR value fixed
- An incorrect logging fixed in Security Mode procedure

#### Breaking Changes
- None

---

### v3.1.8 Release Notes

#### New Features
- RLS/RRC dissector for Wireshark introduced
- SQN synchronization failure handling in authentication
- Local NAS Security Context derivation for emergency
- Security Mode Command integrity check
- Horizontal key derivation in Security Mode procedure

#### Improvements
- Authentication abnormal case handling
- NAS message container handling in Securty Mode procedure
- Generic UE Configuration Update abnormal case improvements
- De-registration abnormal case improvements
- T3516, T3520 handling
- Minor logging improvements

#### Bug Fixes
- PDU Session Status related IEs encoding fix
- SST and SD value range fixed
- Accepting De-registration as unciphered
- Transport Layer Address for IPv4v6 decoding fix

#### Breaking Changes
- None

---

### v3.1.7 Release Notes

#### New Features
- Service Request procedure implemented
- Paging procedure implemented
- UE context release command added to gNB command line
- Cell coverage information added to UE command line
- Acceptable cell detection and Limited Service support

#### Fixes
- Ciphering of initial NAS messages fixed
- NGAP criticality fixed for some IEs

#### Improvements
- New PLMN search and cell measurement system
- RLF and cell coverage change detection improvements
- GUTI/TMSI handling in Identity Procedure
- Registration and de-registration abnormal case improvements
- Minor logging improvements

#### Breaking Changes
- SD field removed from Open5gs sample config files

---

### v3.1.6 Release Notes

#### New Features
- UE-initated PDU session release implementation
- Network-initated PDU session release implementation
- PDU session establishment routing failure handling
- PDU session establishment reject handling
- 5G-SM status handling
- PDU session establishment through CLI
- PDU session release through CLI

#### Fixes
- Empty requested NSSAI fix

#### Improvements
- Minor logging improvements
- CLI output improvements for command dump

#### Breaking Changes
- None

---

### v3.1.5 Release Notes

#### New Features
- Emergency PDU session support
- T3580, T3502 handling
- eCall inactivity handling
- Integrity protection maximum data rate becomes configurable

#### Fixes
- None

#### Improvements
- Registration attempt counter improvements
- Minor RRC RLF improvements
- Error controls improved in PDU session establishment
- Minor logging improvements
- Status command output slightly changed in UE CLI
- Emergency detection improvements in MM sublayer

#### Breaking Changes
- UE config files slightly changed

---

### v3.1.4 Release Notes

#### New Features
- USIM (Universal Subscriber Identity Module) removal through UE CLI

#### Fixes
- Local release of PDU sessions on UE de-registration
- UE TUN interface MTU size reduced to 1400

#### Improvements
- De-registration abnormal case handling
- Minor logging improvements

#### Breaking Changes
- None

---

### v3.1.3 Release Notes

#### New Features
- None

#### Fixes
- Periodic registration in RM_REGISTERED fix
- Crash when high throughput data traffic fix
- Compilation fixes caused by missing "stdexcept" header

#### Improvements
- Mobility and periodic registration abnormal case handling

#### Breaking Changes
- None

---

### v3.1.2 Release Notes

#### New Features
- Configured and default NSSAIs separation
- UE local NAS connection release implementation
- T3510 and T3519 handling

#### Fixes
- PSI value fixed in PDU session establishment
- Deadlock fixed in the AN-Release-REGISTERED_INITATED conflict
- NAS timer remaining value fix in CLI
- Minor fix in Identity Procedure
- Compilation fix for crypt.cpp

#### Improvements
- Initial Registration abnormal case improvements
- De-registration abnormal case improvements
- Authentication Procedure abnormal case improvements
- Security Mode Control abnormal case improvements
- 5G-Update-Status and emergency information added to UE CLI
- NAS Timer displaying slighly changed in UE CLI
- Authentication keys removed from logging
- Minor logging fixes and improvements

#### Breaking Changes
- NSSAI property in UE config file changed
- Default OP type changed to OPC in sample config files
- Default IMSI value changed in some of the sample config files

---

### v3.1.1 Release Notes

#### New Features
- UE de-registration implementation
- AN (Access Network) release implementation
- UE power-off implementation
- Radio Link Failure handling

#### Fixes
- AMF set id and AMF pointer negative value fix
- GPRS timer negative value fix
- Periodic registration in CM-IDLE state fix

#### Improvements
- CLI help messages simplified
- Minor logging improvements
- RLS PDU format changed

#### Breaking Changes
- None

---

### v3.1.0 Release Notes

#### New Features
- Command line interface for UE and gNB

#### Fixes
- UE "no cell available" fixed
- UE radio link simulation disconnect fixed
- Minor memory leak fixes
- AMF name fixed

#### Breaking changes
- None