---

### v3.1.1 Release Notes

#### New Features
- UE de-registration implementation
- AN (Access Network) release implementation
- UE power-off implementation
- Radio link failure handling

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

---