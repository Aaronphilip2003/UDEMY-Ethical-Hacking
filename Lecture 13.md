## Man in the middle Attacks

A man in the middle (MITM) attack is a general term for when a perpetrator positions himself in a conversation between a user and an application—either to eavesdrop or to impersonate one of the parties, making it appear as if a normal exchange of information is underway.

The goal of an attack is to steal personal information, such as login credentials, account details and credit card numbers. Targets are typically the users of financial applications, SaaS businesses, e-commerce sites and other websites where logging in is required.

### Method 1: ARP Spoofing/ Poisoning:
In this methods the packets flow through the hackers computer instad of directly going to the router.

- #### ARP (Adress Resolution Protocol)
- An ARP is a simple protocol used to map IP address of a machine to its MAC address
- The device which needs to communicate with the other device sends out an ARP packet which basically broadcasts the message asking who has the specified MAC address. All devices in the network ignore this ARP packet except the target device.
- To see the arp table  (links the router's IP to its MAC address) of a kali/windows machine :
	- `arp -a` 
- We make the router believe that we are the target device and the target device believe that we are the router (It updates in the arp table of the devices/routers)

## Reasons why ARP Spoofing is possible

- Client accepts responses even if they did not send a request
- Client trusts a response without asking any form of verification