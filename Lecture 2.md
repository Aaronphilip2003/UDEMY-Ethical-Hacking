 # Change to monitor mode

- if we run `iwconfig` on the terminal it'll show us all the wireless connections
- On wlan0 (our wireless adapter) the mode shown will be *managed*.
- We need to change this to *monitor* mode

# Steps to change to *monitor* mode
- First we'll disable wlan0
- Then we'll kill any process that might interfere with it being changed
- Finally we'll change to monitor mode
- Now we'll enable wlan0

```
ifconfig wlan0 down
airmon-ng check kill
iwconfig wlan0 mode monitor
ifconfig wlan0 up
```

Now if we run `iwconfig` we'll see that wlan0 is in monitor mode
