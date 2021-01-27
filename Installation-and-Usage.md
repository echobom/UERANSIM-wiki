Firstly, please make sure that you have the latest [version](https://github.com/aligungr/UERANSIM/releases) of UERANSIM.

##  Requirements
1. Ubuntu 16.04 or later 
2. CMake 3.17 or later

---

## Dependencies
```
sudo apt update
sudo apt upgrade
sudo apt install make g++ libsctp-dev lksctp-tools iproute2
sudo snap install cmake --classic
```

---

## Building
1. Navigate to UERANSIM root folder.
```
cd /path/to/UERANSIM
```
2. Run the following command:
```
make
```
3. See the binaries located at `build/` folder.
---

## Configuring
We provide some predefined config files located at `config` folder. You can also use your own config files.

---

## Running
Execute `./nr-gnb` and `./nr-ue` to use UERANSIM. For more information, use `./nr-gnb --help` and `./nr-ue --help`

---

Next Steps:
[Using Data Plane Features](https://github.com/aligungr/UERANSIM/wiki/Using-Data-Plane-Features)