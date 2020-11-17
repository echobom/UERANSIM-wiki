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