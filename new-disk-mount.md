# Create new partition on new disk and mount it 

## Walkthrough (Creation and mountoing manually)

```
# Step 0: 
Eventually stop server to create new disk

# Step 1:
Create Disk (e.g. on virtualbox)

# Step 2: 
# Boot server and look for disk
# should show up here without partitions 
lsblk 

# Step 3: Create partition(s) on disk 
parted /dev/sdb 
parted>mktable msdos 
parted>mkpart 
parted>quit 

# Step 4: Filesystem aufgebracht 
mkfs.ext4 /dev/sdb1 

# Step 5: Mountpunkt erstellen 
mkdir /mnt/platte 
mount /dev/sdb1 /mnt/platte 
cd /mnt/platte 
touch README 
cd ..

# Step 6: Platte wieder aushängen zum Testen 
umount /mnt/platte 
# keine Dateien mehr zu sehen 
ls -la /mnt/platte 

```

## Mount persistently with testing 

```
nano /etc/fstab
```

```
## add these lines 
/dev/sdb1 /mnt/platte ext4 defaults 0 0
```

```
## Test it
# does it mount properly 
# mounts everything from /etc/fstab of not mounted yet 
mount -av 
```
