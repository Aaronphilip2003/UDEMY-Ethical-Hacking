- # Fake Authentication Attack

## Method 2:  WEP Cracking for non busy WEP

Problems:
- The network is not busy
- Because of the lack of enough data it would take a lot of time to crak WEP networks in the traditional way.

Solution:
- Force the AP to generate new IVs (initialization Vectors).
- Assiciate with the AP before lauching the attack.

**Implementation : Fake Authentication attack**

1.  We first need to associate with the network (*Known as arpreplay*)

`airodump-ng --bssid ::::: --channel __ --write arpreplay wlan0`

2. Now we'll use a fake authentication attack

`aireplay-ng --fakeauth 0 -a ::::: -h :::::: wlan0`

--fakeauth for the fake authentication, 0 because we want to do it only once, -a to paste the target network we want to use and -h for the MAC address of the wireless adapter (*first 6 pairs*) (3. can be found using ifconfig and copy the first 6 pairs) and replace the '-' with ':' 

**IMPORTANT TIP:  *Run 1,2,3 on different terminals simultaneously* **


The moment we run aireplay-ng on the middle terminal, the AUTH on the first terminal will show up to be an open network

**Now we are associated with the network, meaning that we can communicate with it** 

- ## ARP Request replay attack (Most reliable method)
- Now that we are associated with this network, we can start communicating with it, meaning that we can force the router/network to generate new IVs. 

### Working of an ARP Request Replay attack:

- Wait for an ARP packet (a special type of packet)
- Capture it and replay it (retransmit it).
- This causes the AP to produce another packet with a new IV 
- Keep doing this until we have enough IVs to crack the key

*Note: AP - Authentication Packet*

> To run an arpreplay attack run the following command:
> `aireplay-ng --arpreplay -b ::::: -h :::::: wlan0`
> After running this command wait for sometime
> `aircrack-ng arpreplay-01.cap`

*Note: The airodump-ng needs to be running in one terminal*

**The network key is cracked !**
