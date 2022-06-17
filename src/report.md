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

## Part 4. OS Update
![p4upgrade](../misc/images/p4upgrade.png)
Update the system packages to the latest version
## Part 5. Using the sudo command

![p5sudoAdmin](../misc/images/p5sudoAdmin.png)
The main purpose of sudo is to execute a command on behalf of another user, usually from root. The point of executing a command from root is that he has elevated access rights and, using sudo, an ordinary user can perform those actions for which he does not have enough rights.

![p5checkSudo](../misc/images/p5checkSudo.png)
Check sudo (add passwrd admin)

## Part 6. Installing and configuring the time service
![p6timeSync](../misc/images/p6timeSync.png)
sudo timedatectl set-ntp on - command for active NTPSynchronized=yes

## Part 7. Installing and using text editors
#### VIM: https://linuxize.com/post/vim-search/
![p7vimInstall](../misc/images/p7vimInstall.png)
Install VIM: sudo apt-get install vim

![p7vimWrite](../misc/images/p7vimWrite.png)
done to exit with the changes saved with command: :wq!

![p7vimNotSave](../misc/images/p7vimNotSave.png)
done to exit without saving the changes with command: :q!

![p7vimFind](../misc/images/p7vimFind.png)
find command: /RASS

![p7vimReplace](../misc/images/p7vimReplace.png)
replace command::.,$/PIDO/RASS/gi

#### NANO: https://tecadmin.net/how-to-search-in-nano/
![p7nanoInstall](../misc/images/p7nanoInstall.png)
Install NANO: sudo apt-get install nano

![p7nanoWrite](../misc/images/p7nanoWrite.png)
done to exit with the changes saved with command: ^X next y

![p7nanoNotSave](../misc/images/p7nanoNotSave.png)
done to exit without saving the changes with command: ^X next n

![p7nanoFind](../misc/images/p7nanoFind.png)
find command: ^w next Enter

![p7nanoReplace](../misc/images/p7nanoReplace.png)
replace command: ^w next ^r next Enter

#### JOE: https://wiert.me/2016/10/07/installing-the-joe-terminalconsole-text-editor-on-mac-os-x/
![p7joeInstall](../misc/images/p7joeInstall.png)
Install JOE: sudo apt-get install joe

![p7joeWrite](../misc/images/p7joeWrite.png)
done to exit with the changes saved with command:^KS Y

![p7joeNotSave](../misc/images/p7joeNotSave.png)
done to exit without saving the changes with command: ^KQ

![p7joeFindReplace](../misc/images/p7joeFindReplace.png)
find command: ^KF next R (REPLACE) next N(NO)
replace command: ^KF next R (REPLACE) next Y(YES)

## Part 8. Installing and basic setup of the SSHD service
![p8sshdInstall](../misc/images/p8sshdInstall.png)
Install the SSHd service

![p8autoStart](../misc/images/p8autoStart.png)
Add an auto-start of the service whenever the system boots

![p8portChange](../misc/images/p8portChange.png)
Reset the SSHd service to port 2022

![p8psAux](../misc/images/p8psAux.png)
Show the presence of the sshd process using the ps command
https://andreyex.ru/operacionnaya-sistema-linux/komanda-ps-v-linux/
*Option a* instructs ps to display the processes of all users, except for those processes that are not associated with the terminal and the processes of the leader group.
*The U—stands* for a user-oriented format that provides detailed information about processes.
*The x option* in ps lists processes without a control terminal. Basically, these are processes that run during boot and run in the background.

![p8netstat](../misc/images/p8netstat.png)
Reboot the system and run netstat -tan command
https://linuxconfig.org/learning-linux-commands-netstat
-t	Display TCP connections only
-a	Show both listening and non-listening sockets
-n	Show numerical addresses instead of trying to determine symbolic host, port or user names.
https://serverfault.com/questions/78048/whats-the-difference-between-ip-address-0-0-0-0-and-127-0-0-1
When a service is listening on 0.0.0.0 this means the service is listening on all the configured network interfaces, when listening on 127.0.0.1 the service is only bound to the loopback interface (only available on the local machine)

## Part 9. Installing and using the top, htop utilities

#### TOP: https://linux-notes.org/kak-uznat-uptime-v-linux-unix/
![p9tnttcm](../misc/images/p9tnttcm.png)
uptime, number of authorised users, total system load, total number of processes, cpu load, memory load

![p9pidMem](../misc/images/p9pidMem.png)
pid of the process with the highest memory usage

![p9pidTime](../misc/images/p9pidTime.png)
pid of the process taking the most CPU time

#### HTOP:
![p9pid](../misc/images/p9pid.png)
sorted by PID

![p9cpu](../misc/images/p9cpu.png)
PERCENT_CPU

![p9mem](../misc/images/p9mem.png)
PERCENT_MEM

![p9time](../misc/images/p9time.png)
TIME

![p9sshd](../misc/images/p9sshd.png)
filtered for sshd process

![p9syslog](../misc/images/p9syslog.png)
with the syslog process found by searching

![p9hostname](../misc/images/p9hostname.png)
with hostname, clock and uptime output added


## Part 10. Using the fdisk utility
https://opensource.com/article/18/9/swap-space-linux-systems
![p10fdisk](../misc/images/p10fdisk.png)
/dev/sda   Sectors= 43675648 Size= 20.8G
Linux swap size= 4G
https://losst.ru/nastrojka-swap-v-ubuntu-16-04

