## Setting up a windows Virtual Environment

- Download the windows 10 virtual machine from the official distribution of windows
- Default password is - Passw0rd!

 ## Gathering information (Post connection attacks)

 - One of the most important things after gaining access to the network is to gather information about the devices that are connected to the network.

 ## Important:
 - Gather all devices on the network
 - Display their
	 - IP address
	 - MAC address
	 - Operating System
	 - Open Ports
	 - Running services 

### Using netdiscover to gather information

`netdiscover -r 10.0.2.1/24` 
- Basically searching for all devices within the same subnet ie
 10.0.2.1-10.0.2.24
- Connect kali to the internet

If it doesn't work use `netdiscover -c 10 -r 10.0.2.1/24`
-c will just increase the number of packets

