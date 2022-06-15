## Part 1. Installation of the OS
![p1verUbuntu](../misc/images/p1verUbuntu.png)
Ubuntu Version Info

## Part 2. Creating a user
![p2addUser](../misc/images/p2addUser.png)
Add new user 'admin' have permission to read logs from the /var/log folder
![p2allUser](../misc/images/p2allUser.png)
Screenshot of the command `cat /etc/passwd` output

## Part 3. Setting up the OS network
![p3user1](../misc/images/p3user1.png)
Set the machine name as user-1
![p3timeZone](../misc/images/p3timeZone.png)
Set the time zone corresponding to your current location
![p3namesNet](../misc/images/p3namesNet.png)
Output the names of the network interfaces using a console command
*lo:* Occasionally, you will also see the dummy hostname localhost being used instead of the IP-address. ifconfig will look up the name in the hosts file where an entry should declare it as the hostname for 127.0.0.1:
           localhost     127.0.0.1
![p3ipDevice](../misc/images/p3ipDevice.png)
get the ip address of the device you are working on from the DHCP server
#### DHCP: 
*LFP*
https://unix.stackexchange.com/questions/653063/what-are-lpf-and-socket-fallback-in-the-output-of-dhclient-v

*DHCPREQUEST message*
Ethernet: source=sender's MAC; destination=FF:FF:FF:FF:FF:FF
IP: source=10.0.2.15; destination=255.255.255.255;[a]
UDP: source port=68; destination port=67
XID 0x7ad7c
The next message to be transmitted will be a DHCPREQUEST, which will be broadcast. If no response is heard, the client will bind to its address and move to the BOUND state.


*DHCPACK message*
IP: source=10.0.2.15; destination=255.255.255.255;[a]
UDP: source port=68; destination port=67
XID 0x7ad7c
The server sends a confirmation to the client. SRC IP: 10.0.2.15 DST IP: 255.255.255.255. The options and fields of this packet do not differ from DHCPOFFER, except for the option with the code 53 (DHCP message type) equal to 0x05, which means that this packet is a confirmation from the DHCP server.
https://habr.com/ru/company/dsec/blog/333978/

*bound to 10.0.2.15 -- renewal in 37962 seconds*

![p3gwIp](../misc/images/p3gwIp.png)
default from routel
![p3allIp](../misc/images/p3allIp.png)
all from netstat
![p3setIP](../misc/images/p3setIP.png)
Set static (manually set, not received from DHCP server) ip, gw, dns settings (use public DNS servers, e.g. 1.1.1.1 or 8.8.8.8)
![p3reboot](../misc/images/p3reboot.png)
Reboot
![p3ping](../misc/images/p3ping.png)
Ping to 1.1.1.1 and ya.ru