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

TODO