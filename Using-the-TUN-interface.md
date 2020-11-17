First of all please make sure that you have cloned and built the latest version of UERANSIM.

### Starting the TUN Agent.

In order to use the TUN interface, UERANSIM and the `tun-agent` must be running.

Execute the following command to start UERANSIM:
```
./run.sh
```

Execute the following command to start `tun-agent`:

```
sudo ./build/tun-agent
```

And at least one PDU Session is required (for sure). Therefore make sure that you have successfully established a PDU Session using UERANSIM agent.

*NOTE*: UERANSIM and TUN agents should remain open. Restarting UERANSIM requires another establishment of a PDU Session.

---

### Using the TUN Interface

If you want to manually utilize the interface, just bind your TCP/IP socket to `uesimtun` interface. But this is not required for most of the people. See the next section for easy and practical usage of the interface.

---

### Using the TUN via Another Application

You can bind the `uesimtun` interface to almost any application using `ue-bind.sh` tool.

Usage:

```
./ue-binder.sh {IP} {COMMAND} {ARGS}
```

For example:

```
./ue-binder.sh 10.45.0.2 curl google.com
```

In this way, `curl` command will use UE's internet connection with IP `10.45.0.2`

You can also use web browsers such as Firefox. For example:

```
./ue-binder.sh 10.45.0.2 firefox
```

After running this command, all network traffic occurred in Firefox, will use UE's internet connectivity.

**NOTE**: Please kill all Firefox processes before running the command above.

---

### Troubleshooting

If you are not able to connect the internet, make sure following conditions are satisfied:

- UERANSIM and core network successfully configured.
- A PDU Session with IPv4 type successfully established.
- Correct IP address of the related IPv4 PDU Session is given to `ue-binder`.

