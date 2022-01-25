# Ethical Hacking

### - *Using kali linux virtually loaded on VMware*



####  **Changing of MAC address**



> 1. Disconnect the wireless network adapter
> 1. Open VMware and load kali
> 1. Connect the wireless adapter (TP-Link) and select to use it on the virtual machine instead of the host machine.
> 1. once connected load up the terminator (multiple terminal application installed in kali)
> 1. use the following command:
> `ifconfig`
> 1. if the wireless adapter is connected correctly then `wlan0` will be the name of the wireless adapter.
>1.  the 'ether' address will be displayed

> **Steps to change the MAC address**
> 1. `ifconfig wlan0 down`
> 2. `ifconfig wlan0 hw ether 00:11:22:33:44:55`
> - `it translates to hardware address and then put the new MAC address*`
> 3. `ifconfig wlan0 up`

*Important to note that this just temporarily changes the MAC address and after system reboot, it reverts to the original address.*