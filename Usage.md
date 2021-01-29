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

**NOTE:** Routing configurations may clash with your current settings. You can start the UE with `nr-ue --no-route-config` if you don't want the automatic routing configurations (item 2). However TUN interface is always created after a PDU session establishment (item 1).

**NOTE:** Using UE and Core Network on the same computer usually causes problems. Please use 2 different machines for UERANSIM and core network. (You can use virtual machines or non-virtual machines.)

### Using the TUN Interface

If you want to manually utilize the interface, just bind your TCP/IP socket to `uesimtunX` interface.

For example:

```
ping -I uesimtun0 google.com
```

or


```
sudo curl --interface uesimtun0 google.com
```

etc. However we also provide our experimental `./nr-binder` tool to utilize UE's connection easily.

### Using the TUN via `./nr-binder`

You can bind the `uesimtunX` interface to almost any application using `./nr-binder` tool.

**NOTE:** Automatic routing configurations must be enabled for using `./nr-binder`. i.e. don't start the UE with `--no-routing-config` if you want to use `nr-binder` feature.

**NOTE:** `./nr-binder` is experimental and may not work for some applications.

Usage:

```
./nr-binder {IP} {COMMAND} {ARGS}
```

For example:

```
./nr-binder 10.45.0.2 curl google.com
```

In this way, `curl` command will use UE's internet connection with IP `10.45.0.2`

You can also use web browsers such as Firefox. For example:

```
./nr-binder 10.45.0.2 firefox
```

After running this command, all network traffic occurred in Firefox, will use UE's internet connectivity.

**NOTE**: Please kill all Firefox processes before running the command above.

### Troubleshooting

If you are not able to connect to the internet, make sure that the following conditions are satisfied:

- UERANSIM and core network successfully configured.
- A PDU Session is successfully established.
- IP address given to `nr-binder` is exactly same with the IP address of the related IP PDU Session.

