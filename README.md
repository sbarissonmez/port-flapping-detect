# Port flapping detect script will send an email alert if an interface is flapping

If an interface has flapped 5 times in last 5 minutes this script will shutdown that interface. You can change the flapping count to whatever you want. Then the script will wait for 5 mins and enable the shutdown interface. If that interface still flapping at least once script will shutdown the interface and will send an email alert.

This script monitors the interface GigabitEthernet1/0/5, change the interface ID based on your requirement.

This script requires the following variables to be defined:

```
FROM_ADDR
TO_ADDR
name-server ip address
http_proxy and https_proxy commands
```
## Requirements

-- IOS-XE running >/= 16.5.1

## Setup 

* This script requires the IOS-XE guestshell feature. To enable guestshell, configure

    ```
   iox
    ```       

* Then type the following in EXEC mode:

    ```
   guestshell enable
    ```

* Save the script port_flap_email_alert.py in guestshell.

* Next, configure the EEM environment using  EEM_configuration file. Embedded Event Manager (EEM) is a distributed and customized approach to event detection and recovery. EEM offers the ability to monitor events and take informational, corrective, or any desired EEM action when the monitored events occur or when a threshold is reached.