# Packet Sniffing

**Can only be done in monitor mode**

- While in monitor mode
- run `airodump-ng wlan0`

**ESSID** - This shows us the names of the networks around us
**BSSID** - This shows us the MAC address of the target network
**PWR** - This shows us the signal strength (POWER) of the target network (Higher the number, the better)
**Beacons** - Frames sent by the network to broadcast its existence
**\#Data** - Useful data packets
**\#S** - Number of data packets that we collected in the last 10 seconds
**CH** - Channel that the network works on
**MB** - Shows us the maximum speed supported by the network
**ENC** - Shows us the encryption used by the network
**CIPHER** - Shows us the cipher used in the network
**AUTH** - Shows us the authentication used in that network

By default almost all wireless adapters pick up only 2.4GHz bands

To pick up on 5GHz bands run the following command:
`airodump-ng --band a wlan0`

"--band a"  -  This band "a" picks up only on 5GHz networks

We can specify multiple bands:

To detect 2.4 and 5GHz bands together run the following command:
`airodump-ng --band abg wlan0`

*Sniffing on 2 bands is slower as airodump needs to sniff on all the bands at the same time*

**Sniffing on a particular network**
`airodump-ng --bssid 00:11:22:33:44:55 --channel 2 --write test wlan0 `

The above command runs airodump on the given bssid and channel and we use the --write command to write all the information about the network into a file called test.

This creates many test-01 files of different extensions the suffix -01 is added automatically by kali.

Next we can see more information by opening the test-01.cap file in wireshark

To open wireshark run the following command:
`wireshark`
and then proceed to select the .cap file 

.cap stands for the capture file




