# Cracking WEP encrypted networks

WEP stands for Wired Equivalent Privacy and it is an old encryption method that uses the RC4 algorithm. 

For this to work we need to capture a large number of packets.

**Method by which RC4 works**

- WEP sends data to the router in an encrypted format. So the router needs the key to crack it which it already is configured with. Along with the key, to crack WEP we need the initialization vector also.
- When data is sent encrypted in WEP, it send the initialization vector (24 bits) along with the data, so this makes it fairly easy to crack.


*Suppose we need to send data as "hello" to the router, it'll send it as IVhello where IV is the 24 bit initialization vector.*


 ## **Method 1: To crack a Busy Netword with WEP Encryption**
 *First and foremost the, wireless adapter needs to be in monitor mode*
 ```
 airodump-ng --bssid ::::: --channel __ --write basic_wep wlan0
 ```

 Now since it is a busy network we can crack it easily by running the following command on the capture file (.cap)

 ```
 aircrack-ng basic_wep-01.cap
 ```

 After running this it will give us the key 11:22:33:44:55:66 (ASCII: As23e)

 We can connect using the ASCII key, but sometimes it does not appear so we will use the other key without the colons to connect

 password: 112233445566

 