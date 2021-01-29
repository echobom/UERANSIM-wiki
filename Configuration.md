### Overview

Configuration is the most important part, and almost all of the problems are caused by an incorrect configuration.

`nr-ue` accepts a UE configuration file as a parameter, and `nr-gnb` accepts a gNB configuration file as a parameter. The syntax is the following:

```
nr-ue -c myconfig1.yaml
nr-gnb -c myconfig2.yaml
```

We also provide some example configuration files located at `config` folder. You can either edit them, or write your own files. But do not try to use example configurations as is without setting parameters for your own environment.

An example command line for using sample configurations:

```
cd ~/UERANSIM/build
./nr-ue -c ../config/open5gs-ue.yaml
```

### UE Configuration

- **supi:** IMSI number of the UE must be written in this field. Note that we only support IMSI as a SUPI, i.e NAI is not supported.
- **mcc:** Mobile Country Code value for this UE. This value must be consistent with SUPI.
- **mnc:** Mobile Network Code value for this UE. This value must be consistent with SUPI. MNC value can be either 2 digits or 3 digits. Note that 2-digit values are semantically different from 3-digit values. e.g `"25"` is different from `025`. More details can be found on TS [23.501](https://www.etsi.org/deliver/etsi_ts/123500_123599/123501/16.07.00_60/ts_123501v160700p.pdf)
- **key:** This is the permanent subscription key assigned for this specific UE.
- **op:** Operator code value (in either OP or OPC) must be written here. You should set **opType** as **OP** if you write an OP value here, and you should set **opType** as **OPC** if you write an OPC value here. You can either use OP or OPC keys.
- **amf:** Authentication Management Field (AMF) must be written here. Note that this is a different thing from core network function AMF (Access and Mobility Management Function)
- **imei:** IMEI number of the device. IMEI is used if no SUPI provided and for emergency registration etc. This value is generally not used. And this is the only field that is not much important. All other fields must be set precisely.
- **gnbSearchList:** This is the list of IP addresses of gNB for radio link simulation. You can write multiple IP addresses for multiple gNBs. UE will try to pick some gNB from this list. The IP address must match with `linkIp` parameter in the gNB config file. Otherwise UE cannot connect to the gNB. By default we wrote `127.0.0.1` in the sample configuration files, but change this and `linkIp` parameter according to your environment if you use UE and gNB in different machines.
- **sessions:** This is the list of initial PDU sessions. These sessions are automatically established after a UE successfully registers to the 5G core network. You can add multiple PDU sessions to this list. (No more than 15). If you don't want an initial PDU session, you can completely delete the `sessions` parameter. Sessions has `type`, `apn` and `slice` parameters. Only IPv4 is supported for now as a PDU session type. `apn` field specifies the Access Point Name. `slice` parameter is optional and specifies the S-NSSAI for this specific PDU session. Also `sd` parameter is optional as well, but `sst` is always required if the `slice` parameter is included. You can delete optional parameters or set `null` to the relevant fields.
- **slices:** List of requested NSSAIs by this UE. This field is explained above, except this time `slices` parameter itself is not optional. (`sd` is still optional but `sst` is required.)
- **integrity/ciphering:** Here you can set supported integrity and ciphering algorithm for this specific UE. Normally UERANSIM supports all of the algorithms but you can disable it some of them manually by this configuration.

TODO