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
*DHCPREQUEST message*
Ethernet: source=sender's MAC; destination=FF:FF:FF:FF:FF:FF

IP: source=10.0.2.15; destination=255.255.255.255;[a]
UDP: source port=67; destination port=67
XID 0x7ad7c

*DHCPACK message*
IP: source=10.0.2.15; destination=255.255.255.255;[a]
UDP: source port=68; destination port=67
XID 0x7ad7c

![p3ipDevice](../misc/images/p3ipDevice.png)