First of all please make sure that you have cloned and built the latest version of UERANSIM.

### Before Using the TUN Interface

In order to use the TUN interface, UERANSIM must be running (both UE and gNB). And at least one PDU session is required (for sure). Therefore make sure that you have successfully established a PDU Session using UERANSIM.

**NOTE**: UERANSIM should remain open. Restarting UERANSIM requires another establishment of a PDU session.

---

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

---

### Using the TUN via `./nr-binder`

You can bind the `uesimtunX` interface to almost any application using `./nr-binder` tool.

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

---

### Troubleshooting

If you are not able to connect the internet, make sure following conditions are satisfied:

- UERANSIM and core network successfully configured.
- A PDU Session with IPv4 type successfully established.
- IP address given to `nr-binder` is exactly same with the IP address of the related IPv4 PDU Session.

