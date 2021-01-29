### Usage

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

This way, 10 UEs will start and run in the process. IMSI number is incremented by one for each of the UEs (starting from the IMSI specified in the config file). You can also override IMSI parameter in the config file through command line by:

```
nr-ue -c myconfig.yaml -i imsi-286010000000001
```

or

```
nr-ue -c myconfig.yaml -n 10 -i imsi-286010000000001

```