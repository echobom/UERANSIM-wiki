**Q1. Why am I getting java.net.SocketException: Protocol not supported exception?**  

This error usually happens if you are using some Linux VM container in Windows. Windows does not support SCTP protokol, therefore you *may* require a physical Linux machine depending on your VM choice.

Also it is possible that your specific Linux distribution does not support SCTP. However Ubuntu 16.04 and later should support it. 

**Q2. Why am I getting java.net.ConnectException: Connection refused exception?**  

This error means SCTP connection could not established between RAN and AMF. Therefore make sure these 3 following conditions:

1. AMF is running and listening NGAP port (38412).
2. AMF's NGAP IP address and port number exactly matches with gnb.yaml config file.
3. AMF is reachable by RAN over the network. (Check firewall etc.)
  

**Q3. I can't build native libraries.**

Make sure that you set the `JAVA_HOME` environment variable, and have correct version of gcc/g++. You can check the current version with `gcc -v`. In order to upgrade gcc/g++ run the following command:
```
sudo apt update
sudo apt upgrade
sudo apt install g++
``` 

**Q4. How to increase the number of UE and RANs?**

In order to increase the number of UEs, you can change the `number-of-UE` value in `config/testing.yaml`. If you want to increase RAN count, you can run multiple instance of UERANSIM on multiple machines.
