### Overview

Configuration is the most important part, and almost all of the problems are caused by an incorrect configuration.

`nr-ue` accepts a UE configuration file as a parameter, and `nr-gnb` accepts a gNB configuration file as a parameter. The syntax is the following:

```
nr-ue -c myconfig.yaml
nr-gnb -c myconfig.yaml
```

We also provide some example configuration files located at `config` folder. You can either edit them, or write your own files. But do not try to use example configurations as is without setting parameters for your own environment.

// TODO