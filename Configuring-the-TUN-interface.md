With the version v2.2.1 all TUN configurations are automatically applied.

After successful establishment of a PDU session, the UE automatically performs the following operations:

1) A TUN interface is created.
2) A routing table, an IP rule, and an IP route are configured.

**NOTE 1:** You can start UERANSIM with `--no-route-config` if you don't want the automatic routing configurations (item 2). However TUN interface is always created after a PDU session establishment (item 1).

**NOTE 2:** Using UE/gNB and Core Network on the same computer is likely to cause problems. We strongly suggest the usage of 2 different machines (virtual or non-virtual).

Next Steps:
[Using the TUN interface](https://github.com/aligungr/UERANSIM/wiki/Using-the-TUN-interface)