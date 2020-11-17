In order to configure the TUN interface, please follow the instructions in order.

**NOTE:** These settings are not preserved after restarting the Linux computer.

## 1. Create TUN Device

In order to create TUN device, run the following commands:

```
sudo ip tuntap add name uesimtun mode tun
```

---

## 2. Add IP to the TUN

You need to replace {IP} with UE's IP given by core network. You can also execute multiple times to add multiple IP addreses.

```
sudo ip addr add {IP} dev uesimtun
```

For example:

```
sudo ip addr add 10.45.0.2 dev uesimtun
sudo ip addr add 10.45.0.3 dev uesimtun
sudo ip addr add 10.45.0.4 dev uesimtun
```

**Warning:** Better to make sure that no other interface in your system uses the same IP address. For example Open5GS, free5gc and other core networks may have their own TUN interface. Using both UERANSIM and core networks in same environment **may** cause problems.

---

## 3. Set Up The TUN

```
sudo ip link set uesimtun up
```
---
## 4. Configure Routing

Now we need to create a routing table called `uesimtable` **if not exist**. Use `nano` or `echo` to create the table.

Run:
```
sudo nano /etc/iproute2/rt_tables
```

and insert the following line to the bottom of the file:
```
1453 uesimtable
```

---
Now run this command to create a rule and also you can execute multiple times in order to add rules for multiple IP addresses:

```
sudo ip rule add from {IP} table uesimtable
```
For example:

```
sudo ip rule add from 10.45.0.2 table uesimtable
sudo ip rule add from 10.45.0.3 table uesimtable
sudo ip rule add from 10.45.0.4 table uesimtable
```

(You can validate it with `sudo ip rule`)

---

Now run this command to create a route:
```
sudo ip route add default dev uesimtun table uesimtable
```

(You can validate it with `sudo ip route list table uesimtable`)

---

## 5. Done

Configuring the TUN interface is done, now you can use the interface.

[Using the TUN interface](https://github.com/aligungr/UERANSIM/wiki/Using-the-TUN-interface)