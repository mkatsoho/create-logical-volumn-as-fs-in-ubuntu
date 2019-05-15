# create-logical-volumn-as-fs-in-ubuntu
create a logical volumn and mount it as file system in Ubutnu


```bash
lvremove /dev/test48-vg/home 
lvcreate -L 275G -n home test48-vg
  
lvscan
pvscan
  
mkfs.ext4 /dev/test48-vg/home
  
mount /dev/test48-vg/home /home

vi /etc/fstab 
# /dev/mapper/test48--vg-root /               ext4    errors=remount-ro 0       1
# /dev/mapper/test48--vg-home /home           ext4    errors=remount-ro 0       1

mount -a
  
df -Th

  ```
