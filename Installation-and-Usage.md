Firstly, please make sure that you have the latest [version](https://github.com/aligungr/UERANSIM/releases) of UERANSIM.

##  Requirements
1. Ubuntu 16.04 or later 
2. OpenJDK 11 or later
3. g++/gcc version 6.4.0 or later

---

## Dependencies
```
sudo apt update
sudo apt upgrade
sudo apt install make
sudo apt install g++
sudo apt install openjdk-11-jdk
sudo apt install maven
sudo apt install libsctp-dev lksctp-tools
```

---

## Building
1. Make sure that `JAVA_HOME` variable is set.
2. Run the following command:
    ```
    ./nr-build
    ```

---

## Configuring
1. Select a configuration profile by modifying `config/profile.yaml`.
2. Go to the `gnb.yaml` of your profile, and set `host` and `amfHost` addresses.
3. (Optional) You may need to further modify the profile configurations for `ue.yaml`, `gnb.yaml` etc.

---

## Notes

**Note 1)** Changing the `host` and `amfHost` parameters in `gnb.yaml` file is almost always required. Please make sure that you set `host` as the gNB's IP address, and the `amfHost` as the related AMF IP address correctly.

**Note 2)** Our UE accepts `OP` instead of `OPC`, so make sure that you have `OP` value in `ue.yaml`

---

## Running
1. Execute `./nr-agent` to start the UERANSIM agent.
2. Then you can start using `./nr-cli`.

---

## CLI Commands

```
Usage: nr-cli [-hV] [COMMAND]
  -h, --help      Show this help message and exit.
  -V, --version   Print version information and exit.
Commands:
  gnb-create      Create and initialize a new GNB
  ue-create       Create and initialize a new UE
  gnb-list        List all the gNBs associated with this UERANSIM agent
  ue-list         List all the UEs associated with this UERANSIM agent
  gnb-status      Dump some information about specified gNB's general status
  ue-status       Dump some information about specified UE's general status
  session-create  Trigger a PDU session establishment for a specified UE
  ue-ping         Trigger a ping request for the specified UE
  ue-deregister   Trigger a de-registration for the specified UE

```

You can also run `-h` or `--help` options to see more detailed help about subcommands. 

For example: `./nr-cli gnb-create --help`, or `./nr-cli session-create --help` etc.

## Example Usage

Here's a typical usage example.

1. Start UERANSIM agent

`./nr-agent`

2. Create a new gNB

`./nr-cli gnb-create`

3. Create a new UE

`./nr-cli ue-create`

4. List the UEs

`./nr-cli ue-list`

5. Check the UE status.

`./nr-cli ue-status [imsi]`

6. Create a new PDU session.

`./nr-cli session-create [imsi]`

7. Check the UE status again if you want to see the PDU session.

`./nr-cli ue-status [imsi]`

8. Ping google.com by the UE.

`./nr-cli ue-ping [imsi] google.com -c 3`

---

Please always check the terminal of the nr-agent to see logs realtime, and for more detailed logs see the `logs/` folder. 

Next Steps:
[Using Data Plane Features](https://github.com/aligungr/UERANSIM/wiki/Using-Data-Plane-Features)