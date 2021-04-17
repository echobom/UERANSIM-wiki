### v3.1.7 Release Notes

#### New Features
- Service Request procedure implemented
- Paging procedure implemented
- UE context release command added to gNB command line
- Cell coverage information added to UE command line
- Acceptable cell detection and Limited Service support

#### Fixes
- Ciphering of initial NAS messages disabled
- NGAP criticality fixed for some IEs

#### Improvements
- New PLMN search and cell measurement system
- RLF and cell coverage change detection improvements
- GUTI/TMSI handling in Identity Procedure
- Registration and de-registration abnormal case improvements
- Minor logging improvements

#### Breaking Changes
- SD field removed from Open5gs sample config files

#### Known Issues
- gNB CLI cannot be used while gNB is trying to establish an SCTP connection
- NIA3 and NEA3 algorithms may not work as expected

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

#### Known Issues
- Re-registration requirement after de-registration is not handled yet.
- UE may become unusable in CM-IDLE state, since Service Request procedure is not implemented yet.
- gNB CLI cannot be used while gNB is trying to establish an SCTP connection.
- NIA3 and NEA3 algorithms may not work as expected

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

#### Known Issues
- Re-registration requirement after de-registration is not handled yet.
- UE may become unusable in CM-IDLE state, since Service Request procedure is not implemented yet.
- gNB CLI cannot be used while gNB is trying to establish an SCTP connection.
- NIA3 and NEA3 algorithms may not work as expected


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

#### Known Issues
- Re-registration requirement after de-registration is not handled yet.
- UE may become unusable in CM-IDLE state, since Service Request procedure is not implemented yet.
- gNB CLI cannot be used while gNB is trying to establish an SCTP connection.
- NIA3 and NEA3 algorithms may not work as expected

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

#### Known Issues
- UE may become unusable in CM-IDLE state, since Service Request procedure is not implemented yet.
- gNB CLI cannot be used while gNB is trying to establish an SCTP connection.
- NIA3 and NEA3 algorithms may not work as expected


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

#### Known Issues
- UE may become unusable in CM-IDLE state, since Service Request procedure is not implemented yet.
- gNB CLI cannot be used while gNB is trying to establish an SCTP connection.
- NIA3 and NEA3 algorithms may not work as expected


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

#### Known Issues
- UE may become unusable in CM-IDLE state, since Service Request procedure is not implemented yet.
- AN release or radio link failure while UE in REGISTERED-INITATED state causes deadlock.
- gNB CLI cannot be used while gNB is trying to establish an SCTP connection.
- NIA3 and NEA3 algorithms may not work as expected


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

#### Known issues
- gNB CLI cannot be used while gNB is trying to establish an SCTP connection.
- NIA3 and NEA3 algorithms may not work as expected
