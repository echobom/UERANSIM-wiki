### Overview

Configuration is the most important part, and almost all of the problems are caused by an incorrect configuration.

`nr-ue` accepts a UE configuration file as a parameter, and `nr-gnb` accepts a gNB configuration file as a parameter. The syntax is the following:

```
nr-ue -c myconfig1.yaml
nr-gnb -c myconfig2.yaml
```

We also provide some example configuration files located at `config` folder. You can either edit them, or write your own files. But do not try to use example configurations as is without setting parameters for your own environment.

An example command line for using sample configurations:

```
cd ~/UERANSIM/build
./nr-ue -c ../config/open5gs-ue.yaml
```

// TODO