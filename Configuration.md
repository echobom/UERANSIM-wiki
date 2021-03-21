### Overview

Configuration is the most important part, and almost all of the problems are caused by an incorrect configuration (either UERANSIM or core network side).

`nr-ue` accepts a UE configuration file as a parameter, and `nr-gnb` accepts a gNB configuration file as a parameter. The syntax is the following:

```
nr-ue -c myconfig1.yaml
nr-gnb -c myconfig2.yaml
```

We also provide some example configuration files located at `config` folder. You can either edit them, or write your own files. But do not try to use example configurations as is without setting parameters for your own environment.

An example command line for using sample configurations:

```
cd ~/UERANSIM/build

./nr-gnb -c ../config/open5gs-gnb.yaml
./nr-ue -c ../config/open5gs-ue.yaml

./nr-gnb -c ../config/free5gc-gnb.yaml
./nr-ue -c ../config/free5gc-ue.yaml
```

### UE Configuration

- **supi:** IMSI number of the UE must be written in this field. Note that we only support IMSI as a SUPI, i.e NAI is not supported. This field is mandatory except for emergency registration.
- **mcc:** Mobile Country Code value of HPLMN (Home PLMN). This value must be consistent with SUPI.
- **mnc:** Mobile Network Code value of HPLMN (Home PLMN). This value must be consistent with SUPI. MNC value can be either 2 digits or 3 digits. Note that 2-digit values are semantically different from 3-digit values. e.g `25` is different from `025`. More details can be found on [TS 23.501](https://www.etsi.org/deliver/etsi_ts/123500_123599/123501/16.07.00_60/ts_123501v160700p.pdf)
- **key:** This is the permanent subscription key assigned for this specific UE.
- **op:** Operator code value (in either OP or OPC) must be written here. You should set **opType** as **OP** if you write an OP value here, and you should set **opType** as **OPC** if you write an OPC value here. You can either use OP or OPC keys.
- **amf:** Authentication Management Field (AMF) must be written here. Note that this is a different thing from core network function AMF (Access and Mobility Management Function)
- **imei:** IMEI number of the device. IMEI is used if no SUPI provided and for emergency registration etc. This value is generally not used. 
- **imeiSv:** IMEISV number of the device. IMEISV is used if no SUPI and IMEI provided and for emergency registration etc. This value is generally not used. 
- **gnbSearchList:** This is the list of IP addresses of gNB for radio link simulation. You can write multiple IP addresses for multiple gNBs. UE will try to pick some gNB from this list. The IP address must match with `linkIp` parameter in the gNB config file. Otherwise UE cannot connect to the gNB. By default we wrote `127.0.0.1` in the sample configuration files, but change this and `linkIp` parameter according to your environment if you use UE and gNB in different machines.
- **sessions:** This is the list of initial PDU sessions. These sessions are automatically established after the UE successfully registers to the 5G core network. You can add multiple PDU sessions to this list. (No more than 15). If you don't want an initial PDU session, you can completely delete the `sessions` parameter. Sessions has `type`, `apn`, `slice` and `emergency` parameters. Only IPv4 is supported for now as a PDU session type. `apn` field is optional and specifies the Access Point Name. `slice` parameter is optional and specifies the S-NSSAI for this specific PDU session. Also `sd` parameter is optional as well, but `sst` is always required if the `slice` parameter is included. You can delete optional parameters or set `null` to the relevant fields. `emergency` field indicates whether this PDU session is requested for an emergency. `apn` and `slice` parameters are meaningless if `emergency` field is set to `true`.
- **configured-nssai:** Configured NSSAI for this UE by HPLMN (Home PLMN). Content of the NSSAI is already explained above.
- **default-nssai:** Default Configured NSSAI for this UE device. Content of the NSSAI is already explained above.
- **integrity/ciphering:** Here you can set supported integrity and ciphering algorithm for this specific UE. Normally UERANSIM supports all of the algorithms but you can disable some of them manually by this configuration.
- **integrityMaxRate:** This fields specifies the integrity protection maximum data rate for user plane for this UE. Possible values are `64kbps` and `full` as specified by 3GPP 24.501.

### gNB Configuration

- **mcc/mnc:** This fields are already explained above.
- **nci:** This field specifies the NR Cell Identity. Also **idLength** specifies the bit length of the gNB ID which is a part of this NR Cell Identity. More on [TS 38.413](https://www.etsi.org/deliver/etsi_ts/138400_138499/138413/16.04.00_60/ts_138413v160400p.pdf)
- **tac:** Tracking Area Code (TAC) value for this cell.
- **linkIp:** Local IP for radio link simulation for this gNB. UE should connect to this IP address for radio simulation. The IP address must match with `gnbSearchList` parameter in the UE config file. Otherwise UE cannot connect to the gNB. By default we wrote `127.0.0.1` in the sample configuration files, but change this and `gnbSearchList` parameter according to your environment if you use UE and gNB in different machines.
- **ngapIp:** Local IP for N2 interface for this gNB. AMF will send SCTP packets to this IP address, therefore set this IP precisely. Otherwise AMF cannot connect to the gNB and SCTP timeout error occurs. By default we wrote `127.0.0.1` in the sample configuration files, but change this according to your environment if you use gNB and AMF in different machines. (Also our suggestion is always using UERANSIM and core network in different machines.)
- **gtpIp:** Local IP for N3 interface for this gNB. UPF will send GTP packets to this IP address, therefore set this IP precisely. Otherwise UPF cannot send datagrams to the gNB and data plane functions cannot work. By default we wrote `127.0.0.1` in the sample configuration files, but change this according to your environment if you use gNB and UPF in different machines. (Also our suggestion is always using UERANSIM and core network in different machines.)
- **amfConfigs:** List of AMF IP address and port information for N2 (NGAP) interface. This is the other endpoint of what you set in `ngapIp` address. This time you should set this value as AMF's IP address. By default we wrote `127.0.0.X` in the sample configuration files, but change this according to your environment if you use gNB and AMF in different machines. This value is normally a list, but currently only first specified AMF is used. More complex AMF selection mechanism will be implemented in the future.
- **slices:** This field is explained in the UE configurations. And it is the supported list of slices by the gNB.
- **ignoreStreamIds:** Some core networks may not handle SCTP stream numbers properly. Set this field to `true` if you want to ignore such errors. If you are using `open5gs` or `free5gc`, you should set this value to `true`.

### Environment

- Make sure that all of the nodes in your setup (UE, gNB, and core network) can connect to each other over the network, and some firewall rule does not block the 5G traffic between nodes.
- `SCTP` protocol with default port number `38412` is used between gNB and AMF.
  `UDP` protocol with assigned port number `2152` is used between gNB and UPF.
  `UDP` based another protocol with assigned port number `4997` is used between gNB and UE.

### Next Steps

[Usage](Usage)