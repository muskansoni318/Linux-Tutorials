# Linux-Tutorials
Linux Tutorials44

Linux - Linux is a widely-used open-source operating system, similar to Windows, Mac, and Android. It shares similarities with Unix, another operating system known for its commercial use. Unix and Linux have comparable components, including the kernel, shell, and programs. Many commands in Unix and Linux exhibit similar behavior and syntax.

HOW TO INSTALL LINUX ?-   https://www.geeksforgeeks.org/how-to-install-linux-mint/

Module 1: System Access and File System-

Important things-

1) Linux has super user account called root 
2) Root is used to create , modify, delete account and make changes to system configuration files.
3) Linux is case sensitive
4) Linux kernel is software in linux os that takes command from users and pass them  to the hardware 

Access to Linux System -

There are 2 types of access-
1) Console - direct connection  
2) Remote - We can open linux putty session through RDP of windows server

To get the IP address of the server-

1) Give command $ifconfig , then click Enter
2) If its not showing install net-tools -->  $sudo apt install net-tools

3) When gave the command ifconfig , it will show enp0s3 and lo intefaces



Introduction  to Linux File system-

File system - used by computer OS to manage the files and directories 
This system controls how data is saved or received.
(predefined files in the OS like c drive in windows os) 

Example- ext3, ext4, xfs, NTFS, FAT etc 
NTFS and FAT are windows file system 

kernel is the heart of the system and act as mediator between hardware and software.

File system structure-

/boot - containes files used by boot loader (grub.cfg)
Everytime when system boots up , so the first thing it looks for /boot files. and check whats the version if is old version or new version

/root--> Root user home directory . It is not same as / 

/dev --> System devices(eg disk , cdrom, speakers , etc, peripheral devices are connected)

/etc --contains configuration mail . If we are running sending mail , application etc on linux system , DNS.
No need to make any changes otherwise have the backup of it 

/bin --> /usr/bin  --> Eveyday user commands 

/sbin -->/usr/sbin --> System /filesystem commands example- extend file system or configure file system 

/opt-->  optionall add-on applications(used for third party application
example- sql oracle 

/proc --> Ruuning processes (only exist i memry ) contains only running processes. It will be erased if system is shut down 

/lib --> /usr/lin -->it have libraries 

strace -e open pwd

/tmp--> directory used for temporary files/ no use files

/home -->  directory used for user

/var-->  system or application logs go in the /var logs 

/mnt --> used to mount external filesystem 
/media --> for mounting cdroms



CD--> cd  change directory
pwd--> print working directory 
ls ---> list files and directories

Linux file types-

There are 7 files-
1) - regular file
2) d Directory 
3) l link
4) c special file o device file
5) s socket
6) p Named pipe
7) b Block device


 Root-
There are 3 types of root-
1)Root account - username on linux machine like admin account , most powerul which has all access commands and files

2) Root as './' --> VERY first drectory in linux also referred as root directory 

3) Root home directory --> root user account also has directory locaed in /root

FILE SYSTEM PATHS-

1) Absoulte path - path to go to directly to particular path
cd /var/log

2) Relative path- path does not directly go to particular path
cd /var  --> cd log(It does not start with /)

CREATING FILES AND DIRECTORIES-

$touch  filename --> to create file
$cp  filename /path --> to copy the file
$vi filename  --> vi is our editor 
$mkdir  directoryname --> creating directories 
$cp -R filename /path --> wll ensure copies not only the specified directory but also all its subdirectories and their contents.

$find . -name "jerry"   --> used to find the file or directories in current directory(.) 
example- find / -name "jerry" --> will check in  root folder

$locate filename --> locate the filename 


locate is much faster than find but its not accurate evetime so to udate locate atabase run updatedb
$updatedb --> used to update all the db and then we can use locate command 

WILDCARDS --> Used to get multiple files or directories on same time 
*--- 0 or more characters
? - single charater
[] - range of characters

ls -l a*  --> will list all the files start with a
ls - l a? --> files starts with a and has only one character
touch abs{1..4}.txt  --> will create file abs1 ,as2 , abs3, abs4 


SOFT AND HARD LINKS-

Inode= pointer or number of file of hard disk
Everytime we careate  file , computer assign a number to it 

Soft lInk- link will e removed if file is removed or renamed
Hard link -- deleting, renameing or orgiinal file will not affect the hard link

[NOTE ]

Command syntax-
command option(s) argument(s)

Example- ls -ltr

File directory and permissions-

Every user has access to control its or change its permissions
there are 3 type o permissions-
read
write
execute

ech permission are controlled by three level 
u -user
g - group
o- ther

File directory permission can be displayed by useing ls -l command rwxrwxrwx

Chmod command to change the permissions

chmod u-w jerry==> It will remove write permission from u for file jerry
chmod a jerry --> all permissions 
chmod u+w --> will assign permission to user

chmod a-x file --> will remove file execute permissions 

Permission using numeric values-

format--  u g o 

0=no permissions ---
1=execute            --x
2=write                 -w-
3=execure+write   -wx
4=read                   r-- 
5=read+execute    r-x   
6=read+write          rw-
7=all                      rwx          

exaple- chmod 764 file
rwxrw-r--  ugo
wNote- We can rollback the permissions

2 owners are there - user and grps 

chown -- changes the ownership of file
chgrp --changs the group membership of a file 

-R it will not only the specified directory but also all its subdirectories and their contents.

ACL -Access Control List
give permissions for any user or group to any resource

Command to assign and remove ACL permissions are : setfacl and getfacl

To add permissin for user 
setfacl -m u:user:rwx /path/to/file

user- username 

TO add permissions for a group
setfacl -m g:group:rw /path

TO remove a specific entry
setfacl -x u:user /path/to/file

TO remove all entries:
setfacl -b pathtofile

To check what type of access and user group access file have 
getfacl filename 

HELP Commnds-

1) whatis command
2) command --help
3) man command


Adding text to files(Redirect)-

1) vi editor 
2)Redirect command utput > or >>
3) echo > or >>:   > will write on the file >> will append 
4) cat filename 

tee command is used to store and view the ourput of any command any time.
example- echo "This is muskan" | tee filename

Pipe=  
This are used by shell to connect the output of one command add as input to other command .
example command1 argument1 | command2 argument2

example- ls -ltr | more


cp command - cp filename destination 
It will copy the file from source to destination 

rm command --> remove the file command/
Example- rm filename 
rm -Rf will forcefilly delete the file and directory 


mv command --> mv filename destination
Move the file to the destination path

mkdir command --mkdir directoryname
Command is used to create the directory on that particular path even we can give to any path
mkdir dir_name path where need to create directory

rmdir command - rmdir directryname
Command is used to delete the directory from the path

chgrp commad - chgrp groupname filename 
Used o change the group name if that file 

chown command --chown username file
Used to change the owner of the file and directory

more command - more
Gives whole commands in a page

less command -- less 
Used to give the less of page 

tail- tail -10 
command used to get the last 10 files of that path

head- head -10
Used to get then upper 10 files and directories fof the path 

More- command used to give output in one page

Less-command used to give less output in 1 page

             awk command- command used for data extractions from the file or from an ouput 
example - a file with first name and last name there and we wnt the first name only

awk '{print $1}' file

ls -l | awk '{print $1}' --it will show the first column details of ls -l ouput 

echo "Hello Tom" | awk '{$2="Adam"; print $0}'  Replaces words filed word
output- Hello Adam

grep command - grep processes text line by line and prints the line where match is specified
syntax- grep keyword file

egrep commmand - used to search or 2 key words
syntax= egrep -i "keyword1|keywod2" file 


sort command - sort the output in alphabetical orfer
syntax-  sort -r filename this will sort all the files in the file

sort -k3 file -->it will show the indexing 

Uniq filename -->command will show the uniqu filenames 

we can also user sort file | uniq  used to remove duplicacy

sort file | uniq -c --shows the cunting 

wc command --> used to generate newline, count, word count and byte count 

COMPRES FILES-

diff(companre line by line)
cmp(compare bytes by bytes)

COMPRESSING AND UNCOMPRESSING FILES-

tar -cvf "file"  file.tar  --> to zip tte file 
tar -xvf file.tar --> to unzip the file 

gzip  --> compresses the file 
gzip filename.tar --to compress the zip file to decrease tts size 

gzip -d file.tar.gz  --compress zip file 


Truncate file size == to shrink and extend the size of file to specified size 
Syntax-  truncate -s 10 filename 


COMBINING AND SPLITTNG OF FILES INTO ONE-

cat file1 file2 file3 > file4 
split file4


LINUX SYSTEM ADMINISTRATIONS-

--------------------------------------------------------------------------------------------------------
Linux file editor-  enables you to create and manipulate data in linux file 
There are several-
vi, ed, ex , smacs, pico, vim 

VIsupplies command inserting and deleting text ,replacing text, moving around file , finding and substtituting strings , cutting and pasting text

i -insert
esc-escape
r-replace
d=delete
:q! - quit without saving
:wq! -quit and save

sed command - Substitte command which maniputlae the files
Replace a string in file with new string
Find and delete a line'

---------------------------------------------------------------------------------

USER ACCOUNT MANAGEMENT- 

Commands use to manage the user account 

useradd  --to add new user
groupadd -- to add new group
userdel - to delete the user
groupdel --to delete the group
usermod -- to modify the user


/etc/passwd
/etc/group
/etc/shadow 

useradd -g superheroes -s /bin/bash c "Iron man" -m -d  /home/spidermin spiderman(user)
will create user and provide the details like group 

passwrd username -->command to add the password of user 

The Chage command- used to set paramerters around the password '
Will not make any change to user



chage [-d lastday] [-m mindys] [-M msxdays] [-W warndays ] [-I inactive][-e EXPIREDATAE] user


-d = 3 last passwrd change 
-m -4 minimum
-M=5 Maximum
-W=6 Warn
-I=7 Inactive
-E=8 Expire

MONITORS USERS IN THE SYSTEM -

who-->command will tell who are logged in to the server
last  --command will show the last time user logged in what he did 
w  -cmmand is same as who
finger
id --command will give details of user name 


LINUX ACCOUNT AUTHENTICATIONS-

Type of accounts-
1) Local account  - most of the account basic created in linux machine 
2) Domain /directory account -  if we want 10000 user acount suddenly then will use it 

Exmple- cleint send authentication request to seerver it will respond liek user authenticated to client 

Windows = active directory
Linux= LDAP (PROTOCOL NOT DIRECTORY)  


SYSTEM UTILITY COMMANDS-

date command
uptime command
hostname command
unam command  --tells which machine it is linux , solaris etc.
which command  --tells the location of command located
cal command 
bc command -binary calculators 2





HOW much commands we can run , the isting

ls -l /usr/bin


PROCESSES AND JOBS-

application =services  program that runs in server
Script=  shell script or command list of instructions 
Process=Running applications and servers . We culd have multiple proceeses 
Daemon= Runs until interrupted same as process  but willrun continuously
Threads= multiple proceeses associated with each other 
Service-- Process ---Thread --Thread2--Thread 3
Job= created by scheduler to run applications and process

Process/Services commands-

systemctl or service --system control command to control system services 
syntax-  systmectl start|stop|status|restart servicename,service

systemctl enable servicename -- to enabe the service 
systemctl list-units --all command will give all the services in the system 
The ouput will tell UNIT, LOAD, ACTIVE, SUB , and decsiption

To add a service under systemctl management 
Create a file in /etc/systemd/system/servicename.service

TO control system with systemctl - systemctl powerofff
systemctl halt 
systemctl poweroff

ps  -- shows proceses runnign in system 
It stands for process status
Consistes of PID, TTY (TERMINAL TYPE USERS LOGGED IN), TIME, CMD

ps -e --shows all runnign roceses 
ps -ef shows all running proceeses in full format
ps -u username =shows all processes by username 



top --memory and cpu informations about proceses
top -u username -- shows the processes run by the username 


kill -used to kill the process 
Syntax- kill PID

KILL -1  -restart the rocess
kill -2 PID   -interrupt from the keyboard
kill -9 PID -forcefully kill the process
kill -15 PID  -kill process gracefully
killall - kill all processees



crontab-- used to schedule these application, procesess in the system
crontab -e  Edit the crontab
crontab -l list crontab entries
crontab -r remove the crontab
crond  crontab daemon / ervices that manages scheduling
systermctl status crond  to manage crond service 

CRONTAB ENTRY - 
minutee(0-59) housr(0-23) day of month(1-31) month(!-12) day of week(0-6- 7 is also as subnday ) 

CRONTAB -E 
SCHEDULE, ECHO "THIS IS MY FIRST" >CROTNAB-ENTRY > 

at-- at is schedules as one time basis or ad hoc process.


PROCESS MANAGEMENT-

Background =ctrl+z , jobs, and bg 

When we run processes and it will not give output instantly , so we cn make it as bacground

Foreground= fg (wen u want to see the process kept in background)
Run process even after exit = nojhup process &
or 
nohup process > /dev/null  2>&1 &

kill process by name = pkill 

Process prioirty =nice  eg. nice -n 5 process
nice scale goes from-20 to 19

process monitoring = top
process listing = ps

NOTE- EVERYTIME WE CLOSE TERMINA IT WILCLOSE THE JOBS (AS THEY ARE INTERRELATED)

SYSTEM MONITORING-

top 
df 
dmesg
iostate 1
netstat
free
cat /proc/cpuinfo
cat /proc/meminfo


LOG monitoring -

Log directory == /var/log
boot
chronyd =NTP
cron
maillog
secure
messages
https

SYSTEM MAINTAIANCE COMMANDS-

shutdown 
init 0-7
0=simply shutdown 6=reboot
3=multiuser mode
reboot'
halt


FINDING SYSTEM INFORMATION-


cat /etc/redhat-release -infor about os
uname -a  infor about kernel and os 
dmidecore - processor memoruy ad os details 


TERMINAL COMMANDS-

Clean command used to clear the screen
exit command to come out of the shell, terminal or user shell
script command stores terminal activities in a log file 

RECOVERING ROOT PASSWORD-

1)	Restart your computer 
2)	Edit grub 
3)	Change password 
4)	Reboot



ENVOINRMENTAL VARIABLE - An envoirnmental variable can affect the way running processeswill behave o computer. Set of defined rules and values to build envoirnmentl

SHELL SCRPTING- 

Kernel - Program stored in os and its interface between hardware and software 

Shell - Its like a container and the interface between users and kernel/OS 
Example-  CLI is a shell 

Find your shell-
echo $0
Avilable Shells "cat /etc/shells"
/etc/passwrd

TYPES OF LINUX SHELLS-

1) Gnome -  Grapical envoirnment in linux 
commnd line interface

2) KDE
3) sh (shell)  
4) bash 
5) csh and tcsh
6) ksh 

cat /etc/shells


SHELL SCRIPT=  Executable file containing code executed sequentially

sHELL #!/bin/bash
Comments - #
Commands- echo, cp, grep etc.
Statements - if, while, for etc.

Sheell script should be called from absolute path

Basic Shell Script-

CREATA  file -- 

touch myfile
vi myfile 

WRITE ON FILE-

#!/bin/bash

 
firstly assign them the permission to execute chmod 777 myfile

OUTPUT FILE-

./filename 

INPUT / OUTPUT-

read  -->read inputs
echo --> shows ouput 
 

DISK MANAGEMENT AND RUN LEVELS-

There are runlevels in the system that brings the system to differnt mode.
6 different kinds of run lebe-

synatx- init runlevel

0 -shut down / halt the system
1- single user mde, usually as s or S
6- reboot the system
2- multisuer mode without networking (cannot communicate with other systems)
3- multi user mode with networking 
5- multiuser mode with networking and GUI 


LINUX BOOT PROCESS-

BIOS - Basic Input / Output System executed MBR
Everytime we on the system it goes to BIOS and at this stage it performes some system integrity checks, load and boot loader files.It looks for boot loader, folppy disk, cdrom etc. to make the system up.

MBR - MASTER BOOT RECORD 

Located in the first sector of bootable disc like DEV, HDA, or SDA .
MBR is somehow like 512 mb size.
It contains informaton about GRUB

GRUB- GRAND UNIFIED BOOT LOADER
If we have multiple kernel installed in system , we can use which one to use it and the GRUB config located in /boot , /grub and the file grub.conf

Kernel- kERNEL executed /sbin/init
Kernel is one that mounts the root file system as specified in root equal in grub.conf file.
It eexcute init program

Init- Then it systrts initial RAM disc.
initrd is used by kernel is temporary root file system untill kernel is booted and real root file is mounted.
It contains necessry drivers compiled inside whic helps to manage harware partitions 

RUNLEVL-
/etc/init file to decide the run level in the server.
cd /etc/rc.d


NEW VERSION OF LINK= /etc/systemd/system/default.target

To set new default run-level run  
#systemctl set-default [new-target]

Older version of linux= /etc/inittab



==============================================

MESSAGE OF THE DAY
It will apprear on screen onse we are logged i to the server

Customize message of data -

1) create a new file in /etc/profile.d/motd.sh
2) Add desired command in motd.sh file 
3) Modily the /etc/ssh/sshd_config file to edit #PrintMotd yes to PrintMotd no

4) restart ssshd service

COMPUTER STORAGE--

Used to store data and information
Types of storage -
1) Local storage - RAM, HDD , SSD etc.
2) DAS -Eg. cd ,dvd, USB, EXTRENAL DISK
3) SAN - storage area network - storage attached through isci or fiber cables.
4) NAS -network attached storage - attached to computer or network.example- TCP/IP , NFS, Samba etc.
It is given an IP address 

\

DISK PARTITIONS- 

Shows which file system has been artitions

df - shows the disk information
fdisk - how much total disk size is 

fdisk 0l command will tell the partitions and disk size information 

ADD DISK AND CREATING PARTITIONS-

LVM- 
Logical Volume Mangement 
VM Allows disks to be combined together.

SWAP SPACE-  
used when RAM is full , 
Used when system wants more memory 
It should not be considered as actual memory
Slower access time 


dd if=/dev/zero of=/newswap bs=1M count=1024

dd=command to create new file 
if =read from file 
of=write to file
bs =byte size
count=total size


FILE SYSTEM CHECKS-

command used to repair the file system

fsck 
xfs_repari

Linux fsck utility is used to check and repair Linux file systems
example- ext3 ext 2, ext4, etc.

Note-  ony to execute fsck command on unmounted file syste to avoid data corruptions'

Linux xfs_repariuility is used to check and repair fiesystems for xfs filesystem type

Basically the system runs the fsck during boot time to check whether the filesystem is in consistent state or not and xfs_repair does not run ata boot time.

NETWORK FILE SYSTEM-

Sharing your disk, directory , files wih other computers and systesm.
Its not local and also called NAS (networ attached storage)

Client./Server system that allows users to access files acoss network.
The rocess includes exporting and then mounting 

NFS request go to server and then based on rules it will proveide acknowledged and approve to clients.

STEPS for Nfs- server -

1) Install NFS package 
yum install nfs-utils rpcbind
2) ENbae NFS services 
ssystemctl enable nfs-server /rpcbin, nfs-server, rpc-statd, nfs-idmapd

3) Create NFS share directory and assign permissions

4) Modify /etc.exports file to add new file shared filesystem 

/mypret client_ip (rw,sycn , no_root_sqaush) =for only 1 host
example- .mypret 192.168.12.3 (rw, sync, no_root_squash) 
root will have the access to the file 

/mylinusfile *(rw,sync,no_root_squash) = for everyone

5) Eport NFS file system

exportfs -rv 

STEPS for Nfs client-

1) Install NFS packge
2) Start the sevice 

service rpcbind start

3) Make sure firewalld or iptables stopped
ps -ef | egrep "firewall|iptable"

4) Shows mount from NFS server
showmount -e 192.186.1.5 (NFS server IP) 

5)Create Mount point
mkdir /mnt/app

Mount the NFS file system
mount 192.168.1.5: /mypret /mt.kramer

6) Verify mounted filesystem
df -h

to unmount = unmount /mnt/krmaer

3 main commands to transfer files from one computer to another
ftp, scp, rsync

Which component typically contains the bootloader and its configuration in a modern computer?  Hard drive or SSD

default NFS port number for NFS services- 2049

file is commonly used to configure NFS exports on a Linux server- /etc/nfs/exports


NETWORKING-


NIC information- Network interface comman used to connect ethernet to laptop 
NIC has multiple ports associated.
command- ethtool nicname

example- ethtool enp0s3

lo interface in ifconfig = The loopback device is a special interface that your computer uses to communicate with itself. It is used mainly for diagnostics and troubleshooting, and to connect to servers running on the local machine 

virb0=  the virbr0 or virtual bridge 0 interface is used for NAT (Network adrees translation).  virtual envoirnmnet sometimes use it to connect to the outside network

eth 0 , 1 2for normal interface

NIC bonding-

NIC bonding is also known as Network bonding. It can be defined as aggregation of multiple NIC or combination of NIC into a single bond interface.
Provides high availability and redundancy

Network Manager-

command used network confi methods
Ntwork Manager is service that provides set of tools designed specifically to make it easier to manage the networking configurations on linu syste and is default netwrk management service on rhel8 and rhel9

It makes network management easier
it provides set of connection to the user

FTP file transfer protocol-   The FTP is a standard network protocol ised to transfer of computer files between a client and server on a computer network. FTP built on client-server model and data connections between the client and the server.

FTP is protocol used to transfer the file from A to B
protocols-  FTP port =21 



SCP- Secure copy protocol
Helps to transfer files securely from local to remote host. It adds security and authentication
SCP port = 22

rsync- Remote Synchronization
Used for transffering file and syncing files within same computer or to a remote computer by comparing the modification times and sizes of files

moving files from A to B

Tis is mostly used it for backup the files and directories from one server to another.
RSYNC PORT = 22


SYSTEM UPDATE AND REPOS(Repositories)-

yum(centos), apt-get(other linux) 
Configuation file location: /etc/yum.repos.d

yum does need internet

rpm(red hat package manager)-  rpm used when they dont have internet access and they have the file to instll 

rpm -qa   - command used to get all the package details 

rpm -qa | wc -l --> command will share the total packages installed 

rpm -qa | grep ntp command used to find out the ntp package is installed or not in the server

to remove any package , we can use below commands-

yum remove bind 
yum -e bind


SSH AND TELNET -
accept connections from outside 
telnet is unsecured and ssh is secured 

2 types packages for most of the services-
client package and server package 

HOSTNAME / IP LOOKUP 

command used for the dns lookup-
nslookup and dig 

nslookup www.google.com

NTP -network time protocol service used for time synching.
File- /etc/ntp.conf
service - systemctl restart ntpd
command -ntpq
port- 123 

chronyd - new version of NTP

Package ame= chronyd
config file= /etc/chronyd.conf
log file=/var/log/chrony
service= systemctl status chronyd 
program command = chronyc 


NEW system Utility command- timedatectl

this command will show/change date, time and timezone 
It synchronises the time with NTP server as well 
we can either use chronyd or ntpd and make the ntp setting in  timedatectl as yes


SENDMAIL-
Used to send emails nd receive emails 
files= /etc//mail/sendmail.mc
          /etc//mail/sendmail.cf

service= systemctl restart sendmail
command- mail -s "subject line" email@mydomain.com

CREATING WEB PAGE server- (httpd)

Service =htpd 
Files = /etc/http/conf/httpd.conf or /var/www/html/index.html
Systemctl restart httpd 



CENTRAL LOGGER- RSYSLOG

Genrate logs or collect logs from other servers'
central location consisting of all logs
service = rsyslog
config file=  /etc/rsyslog.conf
port- 514

if we want to make any changes or establish communication then we can add the server and poort 514 in the conf file 



Linux OS HARDENING-

How to secure user accounts- 
Remove un wanted packages
Stop unsed services
Check on listening ports
Secure ssh config
Enable firewall (iptables/firewalld)
Enable SELinux 
Change listening services port number
Keep your OS update 


COCKPIT-
Cockpit is server administrator tool focused providing a modern looking and user friendly interface to mange and administrator servers.

It is easy to use and open web based interface for servers.
We can monitor system resources, add or remove accounts , monitor system usage, shut down and some task can be perfoemed are very accessible web connection

Install cockpit-

We have to perform this on server and client side both-

check network connectivity should be there 
install cockpit package - yum/dnf install cockpit or apt install cockpit
start and enable the service systmctl start cockpit 
Access the web interface-  https://192.168.1.x:9090
ip would be of your system 
Make sure firewall isdisbaled 
and then search for the ips on local host 
