### Basic Usage

After completing configurations and setups, now you can start using UERANSIM.

Run the following command to start the gNB:

```
nr-gnb -c myconfig.yaml
```

Run the following command to start a UE:

```
nr-ue -c myconfig.yaml
```

You can also set number of UEs by setting:

```
nr-ue -c myconfig.yaml -n 10
```

This way, 10 UEs will start and run in the process. IMSI number is incremented by one for each of the UEs (starting from the IMSI specified in the config file). You can also override IMSI parameter in the config file over the command line by:

```
nr-ue -c myconfig.yaml -i imsi-286010000000001
```

or

```
nr-ue -c myconfig.yaml -n 10 -i imsi-286010000000001
```

### Usage of the Data Plane

We provide a TUN interface in order to use UE's internet connectivity. With the version v2.2.1 all TUN configurations are automatically applied.

A TUN interface is setup for each PDU session. After successful establishment of a PDU session, the UE automatically performs the following operations:

1) A TUN interface is created.
2) A routing table, an IP rule, and an IP route are configured.

**NOTE:** You can start the UE with `nr-ue --no-route-config` if you don't want the automatic routing configurations (item 2). However TUN interface is always created after a PDU session establishment (item 1).

**NOTE:** Using UE and Core Network on the same computer usually causes problems. Please use 2 different machines for UERANSIM and core network. (You can use virtual machines or non-virtual machines)