### Getting the UERANSIM

Firstly, please make sure that you have the latest version of UERANSIM. You can download the source code from [here](https://github.com/aligungr/UERANSIM/releases) or clone the repository:

```
cd ~
git clone https://github.com/aligungr/UERANSIM
```

---

### Requirements

1. Ubuntu 16.04 or later
2. CMake 3.17 or later
3. gcc 9.0.0 or later
4. g++ 9.0.0 or later

Other Linux distributions are likely to work in general. But unfortunately Windows is **not** supported since Microsoft didn't implement SCTP protocol. You would need a virtual machine for a workaround.

**NOTE:** Windows Subsystem for Linux (WSL) cannot be used as a virtual machine as well. Also guest to host NAT based network configurations may not work on Windows because of the same reason. However **VirtualBox** with a **bridged adapter** setting should work fine on Windows.

---

### Dependencies

Firstly it's better to update your apt repositories and upgrade the programs.

```
sudo apt update
sudo apt upgrade
```

Then here's the list of dependencies: (Built-in dependencies shipped with Ubuntu are not listed herein.)

```
sudo apt install make
sudo apt install gcc
sudo apt install g++
sudo apt install libsctp-dev lksctp-tools
sudo apt install iproute2
sudo snap install cmake --classic
```

**NOTE:** Don't install **cmake** with `sudo apt-get install cmake`, because it installs very old version of cmake by default. You can use `sudo snap install cmake --classic` or build [cmake](https://cmake.org/https://cmake.org/) directly from sources.

**NOTE:** `make, g++, cmake` packages are only required for building UERANSIM. However `libsctp-dev, lksctp-tools, iproute2` packages are also required at runtime.

---

### Building

And here's command for building:

```
cd ~/UERANSIM
make
```

And that's it. After successfully compiling the project, output binaries will be copied to `~/UERANSIM/build` folder. And you should see the following files:

1. **nr-gnb** | Main executable for 5G gNB (RAN)
2. **nr-ue** | Main executable for 5G UE
3. **nr-cli** | CLI tool for 5G gNB and UE
4. **nr-binder** | A tool for utilizing UE's internet connectivity.
5. **libdevbnd.so** | A dynamic library for nr-binder

Run `nr-gnb` and `nr-ue` to start using UE and gNB. More details about them can be found in next steps.

`nr-binder` and `libdevbnd.so` are only required for binding UEs internet connectivity to an arbitrary application, and generally not used.

### Next Steps

[Configuration](Configuration)