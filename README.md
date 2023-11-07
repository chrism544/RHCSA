## Question 1 

<details>SIMULATION -
Create one partitions having size 100MB and mount it on data.CLICK ME</summary>
<p>

#### yes, even hidden code blocks!

Explanation:
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
