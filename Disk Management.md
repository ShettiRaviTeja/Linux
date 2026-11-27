# Disk Management
- It is the process of managing storage devices in Linux.
- It includes:
  - Creating partitions on disks.
  - Resizing existing partitions.
  - Formatting partitions with different file systems.
  - Mounting and unmounting partitions.
  - Managing RAID arrays.

## Steps to do:
1. First create a disk in a virtual box.
2. Now create the partitions to that disk using parted command.
3. Create the filesystems using mkfs.ext4 /dev/partitionname.
4. Perform disk resizing on that disk partitions.

## Commands
1. parted : Used to create the partitions.
2. mkfs.fsname : Used to create the filesystem.
3. resizepart : Used to resize the partitions.
4. resize2fs (partition) (size) : Used to resize the file system.
5. vi /etc/fstab : Used to insert the record to make the mounting permenant.
6. pvcreate partition : Used to create the physical volume.
7. vgcreate vgname partition1 partition2 : Used to create the volume groups.
8. lvcreate -L size -n lv_name vg_name : Used to create a logical volume from the volume group.
9. mdadm --create arr_name --level=5 --raid-devices=3 /dev/sdc /dev/sdd /dev/sde : Used to create the raid arrays.
10. sudo wipefs -a /dev/sdd : Used to wipe the disk.
11. vgs : List the volume groups.
12. pvs : List the physical volumes.
13. lvs : List the logical volumes.
14. mount /dev/sdc /mout/mfiles : Used to mount the partitions.
15. umount /dev/sdc or umount /mout/mfiles : Used to unmount the partitions.
### Persistent mounting : Making the mounting permanent by inserting its record in the fstab vi.
