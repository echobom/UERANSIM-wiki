##  Requirements
1. Ubuntu 16.04 or later 
2. OpenJDK 11 or later
3. g++/gcc version 6.4.0 or later

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

## Building
1. Make sure that `JAVA_HOME` variable is set.
2. Run the following command:
    ```
    ./build.sh
    ```


## Running
1. Select a configuration profile by modifying `config/profile.yaml`.
2. You may need to further modify the profile configurations for IP addresses and port numbers etc. (see `config/open5gs`, `config/free5gc`, etc.)
3. Execute `./run.sh` to start the application.
4. Use `tail -f` to monitor logs realtime located at `logs/*.log`.
5. Use terminal to trigger test events such as `initial-registration`