## Question 1 

<details><summary>Create one partitions having size 100MB and mount it on data.</summary>
<p>

#### Explanation:

1. Use fdisk /dev/hda to create new partition.
2. Type n For New partitions.
3. It will ask for Logical or Primary Partitions. Press l for logical.
4. It will ask for the Starting Cylinder: Use the Default by pressing Enter
Key.
5. Type the Size: +100M you can specify either Last cylinder of size here.
6. Press P to verify the partitions lists and remember the partitions name.
7. Press w to write on partitions table.
8. Either Reboot or use partprobe command.
9. Use mkfs -t ext3 /dev/hda?

OR -
mke2fs -j /dev/hda? To create ext3 filesystem.
vi /etc/fstab
Write:
/dev/hda? /data ext3 defaults 1 2
Verify by mounting on current Sessions also: mount /dev/hda? /data

</p>
</details>

## Question 2

<details><summary>You are new System Administrator and from now you are going to handle the system and your main task is Network monitoring, Backup and Restore. But you don't know the root password. Change the root password to redhat and login in default Runlevel.</summary>
<p>

#### Explanation:
Explanation: When you Boot the System, it starts on default Runlevel specified in /etc/inittab:
Id:?:initdefault:
When System Successfully boot, it will ask for username and password. 
But you don't know the root's password. 
To change the root password you need to boot the system into single user mode. 
You can pass the kernel arguments from the boot loader.

1. Restart the System.
2. You will get the boot loader GRUB screen.
3. Press a and type 1 or s for single mode ro root=LABEL=/ rhgb queit s
4. System will boot on Single User mode.
5. Use passwd command to change.
6. Press ctrl+d
   
</p>
</details>

## Question 3

<details><summary>You are a System administrator. Using Log files very easy to monitor the system. Now there are 50 servers running as Mail, Web, Proxy, DNS services etc. You want to centralize the logs from all servers into on LOG Server. How will you configure the LOG Server to accept logs from remote host?</summary>
<p>

#### Explanation:

By default, system accept the logs only generated from local host. To accept the Log from other host configure: vi /etc/sysconfig/syslog SYSLOGD_OPTIONS="-m 0 -r"

Where -
-m 0 disables 'MARK' messages.
-r enables logging from remote machines
-x disables DNS lookups on messages received with -r
service syslog restart
</p>
</details>

## Question 4

<details><summary>Your System is configured in 192.168.0.0/24 Network and your nameserver is 192.168.0.254. Make successfully resolve to server1.example.com.     </summary>
<p>

#### Explanation:

nameserver is specified in question,
1. Vi /etc/resolv.conf
nameserver 192.168.0.254
2. host server1.example.com
   
</p>
</details>

## Question 5

<details><summary>One Package named zsh is dump on ftp://server1.example.com under /pub/updates directory and your FTP server is 192.168.0.254. Install the package zsh.</summary>
<p>

#### Explanation:

rpm -ivh ftp://server1/example.com/pub/updates/zsh-*
or
Login to ftp server : ftp ftp://server1.example.com using anonymous user.
Change the directory: cd pub and cd updates
Download the package: mget zsh-*

Quit from the ftp prompt : bye -

Install the package -
rpm -ivh zsh-*
Verify either package is installed or not : rpm -q zsh

</p>
</details>

## Question 6

<details><summary>Some users home directory is shared from your system. Using showmount -e localhost command, the shared directory is not shown. Make access the shared users home directory.</summary>
<p>

#### Explanation:

Verify the File whether Shared or not ? : cat /etc/exports
Start the nfs service: service nfs start
Start the portmap service: service portmap start
Make automatically start the nfs service on next reboot: chkconfig nfs on
Make automatically start the portmap service on next reboot: chkconfig portmap on
Verify either sharing or not: showmount -e localhost
Check that default firewall is running on system?
If running flush the iptables using iptables -F and stop the iptables service.
</p>
</details>

## Question 7

<details><summary>Add a new logical partition having size 100MB and create the data which will be the mount point for the new partition.</summary>
<p>

#### Explanation:

1. Use fdisk /dev/hda-> To create new partition.
2. Type n ->For New partitions
3. It will ask for Logical or Primary Partitions. Press l for logical.
4. It will ask for the Starting Cylinder: Use the Default by pressing Enter

Keys -
5. Type the size: +100M you can specify either Last cylinder of size here.
6. Press P to verify the partitions lists and remember the partitions name.
7. Press w to write on partitions table.
8. Either Reboot or use partprobe command.
9. Use mkfs -t ext3 /dev/hda?

OR -
1. mke2fs -j /dev/hda? ->To create ext3 filesystem.
2. vi /etc/fstab
3. Write:
/dev/hda? /data ext3 defaults 0 0
4. Verify by mounting on current sessions also:
mount /dev/hda? /data
</p>
</details>

## Question 8

<details><summary>You have a domain named www.rhce.com associated IP address is 192.100.0.2. Configure the Apache web server by implementing the SSL for encryption communication. </summary>
<p>

#### Explanation:

vi /etc/httpd/conf.d/ssl.conf <VirtualHost 192.100.0.2> ServerName www.rhce.com DocumentRoot /var/www/rhce DirectoryIndex index.html index.htm

ServerAdmin webmaster@rhce.com SSLEngine on SSLCertificateFile /etc/httpd/conf/ssl.crt/server.crt SSLCertificateKeyFile /etc/httpd/conf/ssl.key/server.key </VirtualHost>
cd /etc/httpd/conf
3 make testcert
Create the directory and index page on specified path. (Index page can download from ftp://server1.example.com at exam time) service httpd start|restart chkconfig httpd on
Apache can provide encrypted communications using SSL (Secure Socket Layer). To make use of encrypted communication, a client must request to https protocol, which is uses port 443. For HTTPS protocol required the certificate file and key file.
</p>
</details>

## Question 9

<details><summary>     </summary>
<p>

#### Explanation:

</p>
</details>

## Question 10

<details><summary>     </summary>
<p>

#### Explanation:## Question 2

<details><summary>     </summary>
<p>

#### Explanation:

</p>
</details>


</p>
</details>

## Question 2

<details><summary>     </summary>
<p>

#### Explanation:

</p>
</details>

## Question 2

<details><summary>     </summary>
<p>

#### Explanation:

</p>
</details>

## Question 2

<details><summary>     </summary>
<p>

#### Explanation:

</p>
</details>

## Question 2

<details><summary>     </summary>
<p>

#### Explanation:

</p>
</details>

## Question 2

<details><summary>     </summary>
<p>

#### Explanation:

</p>
</details>

v
## Question 2

<details><summary>     </summary>
<p>

#### Explanation:

</p>
</details>

## Question 2

<details><summary>     </summary>
<p>

#### Explanation:

</p>
</details>

## Question 2

<details><summary>     </summary>
<p>

#### Explanation:

</p>
</details>

## Question 2

<details><summary>     </summary>
<p>

#### Explanation:

</p>
</details>

## Question 2

<details><summary>     </summary>
<p>

#### Explanation:

</p>
</details>

