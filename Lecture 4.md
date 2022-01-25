# Running a De-Auth Attack

DeAuth attack / *Deauthentication attack* is an attack where you disconnect the target deivce from the router for a large number and he'll try and reconnect but wont be able to unless we quit aireplay-ng

- The concept is that we pretend to be the MAC address of the target device and we send the signal to the let's say router and then we pretend to be the MAC address of the router and disconnect the target device as requested by the phone (which is us in the first place).
- We dont have to do this manually as `aireplay-ng` does this for us automatically


**RUNNING A DEAUTHENTICATION ATTACK**

We need to disconnect the target device. To do this run the following command:

`aireplay-ng --deauth 100000000 -a ::::: -c :::::: wlan0`

> after -a we use the mac address of the router.
> after -c we use the mac address of the target device.(client)

If we want to reconnect the device we will do ctrl+c on the terminal which kills aireplay-ng and allows the target device to reauthenticte with the target device
