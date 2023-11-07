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
When System Successfully boot, it will ask for username and password. But you don't know the root's password. To change the root password you need to boot the system into single user mode. You can pass the kernel arguments from the boot loader.
1. Restart the System.
2. You will get the boot loader GRUB screen.
3. Press a and type 1 or s for single mode ro root=LABEL=/ rhgb queit s
4. System will boot on Single User mode.
5. Use passwd command to change.
6. Press ctrl+d
7. 
</p>
</details>
