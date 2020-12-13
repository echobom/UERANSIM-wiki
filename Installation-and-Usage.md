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

