## **Method 2: Using a Wordlist**

### WPA/WPA2 cracking:
- Fixed all the weaknesses in WEP.
- Packets contain no useful information unlike the WEP.
- The only packets that can aid in the cracking process are known as the handshake packtes.
	- These are 4 packets sent when a client connects to the network

Step 1: Run airodump-ng and store all the available information about the target network in a file.

Step 2: The only way we crack the code is if we get a WPA handshake and we get that when a new device connects to the network. 

Step 3: If we dont want to wait around for a new device to connect to the network, we can use a fake authentication attack and disconnect one of the devices from the network and the moment they reconnect, we will get a WPA handshake.


Step 4: The handshake does not contain data that helps recover the key
- It only contains data that can be used to check whether the key is valid or not.

Step 5: Creating a wordlist / using a wordlist
- First we'll create a wordlist using this tool called crunch
> `crunch[min][max][characters]-t[pattern ]-o[filename]`
> eg. `crunch 6 8 123abc$ -o wordlist -t a@@@b`
> `crunch 9 9 anaro231$ -o wordlist -t aar@@@@@@`
> in the above example it will generate all passwords between a and b
- To see the file we can do `cat test.txt`

Step 6: Now that we have created/ we are using a wordlist, we'll start the attack

The MIC or Message Integrity Code is what's used by the access point to verify whether the entered password is correct or not. (EAPOL)

The Message integrity code is then checked with the password, if the MIC of the password and the network are the same, then we can say with surety that the password we checked is infact the right password for the network

- Initiate Attack using aircrack-ng

`aircrack-ng wpa_handshake.cap -w test.txt`