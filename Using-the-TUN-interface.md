First of all please make sure that you have cloned and built the latest version of UERANSIM.

### Starting the TUN Agent.

In order to use the TUN interface, UERANSIM and the `tun-agent` must be running.

Execute the following command to start UERANSIM:
```
sh run.sh
```

Execute the following command to start `tun-agent`:

```
sudo ./build/tun-agent
```

And at least one PDU Session is required (for sure). Therefore make sure that you have successfully established a PDU Session using UERANSIM agent.

*NOTE*: UERANSIM and TUN agents should remain open. Restarting UERANSIM requires another establishment of a PDU Session.

### Using the TUN Interface

If you want to manually utilize the interface just bind the TCP/IP socket to `uesimtun` interface. But this is not required for most of the people. See the next section for practical usage of the interface.