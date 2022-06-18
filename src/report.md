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

## Part 11. Using the df utility
![p11df](../misc/images/p11df.png)
*root partition (/):*
partition size= 17234228 Bytes
space used= 6355308 Bytes
space free= 9980412 Bytes
percentage used= 39 %

![p11dfTh](../misc/images/p11dfTh.png)
*root partition (/):*
partition size= 17 GB
space used= 6.3 GB
space free= 9.4 GB
percentage used= 41 %

## Part 12. Using the du utility
![p12duvarHomeLog](../misc/images/p12duvarHomeLog.png)
Output the size of the /home, /var, /var/log folders (in bytes, in human readable format)

![p12duVarLog](../misc/images/p12duVarLog.png)
Output the size of all contents in /var/log (not the total, but each nested element using *)

## Part 13. Installing and using the ncdu utility
![p13ncduHome](../misc/images/p13ncduHome.png)
Output the size of the /home
![p13ncduVar](../misc/images/p13ncduVar.png)
/var
![p13ncduVarLog](../misc/images/p13ncduVarLog.png)
/var/log
*size approximately the same as in Part 12*

![p13ncduCmd](../misc/images/p13ncduCmd.png)
used commands

## Part 14. Working with system logs
Open for viewing:
1. nano /var/log/dmesg
2. nano /var/log/syslog
3. nano /var/log/auth.log
![p14login](../misc/images/p14login.png)
last successful login time, user name and login method 

![p14rsshd](../misc/images/p14rsshd.png)
Restart SSHd service

## Part 15. Using the CRON job scheduler
![p15uptime](../misc/images/p10fdisk.png)
run the uptime command in every 2 minutes
![p15list](../misc/images/p15list.png)
crontab -e
(crontab -u admin -e for current user)
screenshots of the execution lines and the list of current tasks
![p15cronR](../misc/images/p15cronR.png)
Remove all tasks from the job scheduler
crontab -r
