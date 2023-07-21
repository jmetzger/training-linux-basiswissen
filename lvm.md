# lvm 

## keine Befehle lvdisplay,vgdisplay etc.

```
# Debian / Ubuntu 
apt install lvm2
# Redhat 
dnf install lvm2 
```

## 3 Befehle zum anzeigen der Bereiche 

```
pvdisplay # physical volumes anzeigen = partition unter lvm nutzung
vgdisplay # Alle Volume Groups im System anzeigen
lvdisplay # Alle Logical Volumes im System anzeigen
```

## Schritt 1: Partitionen vorbereiten 

```
# parted /dev/sdb

# partitionen erstellen z.B. 1 und 2 
# 2x mkpart .....
# und ein flag für lvm setzen
(parted) set 2 lvm on
(parted) set 3 lvm on 

quit 
```

## Schritt 2: Physical Volumes vorbereiten (1. lvm Schritt) 

```
pvcreate /dev/sdb2 /dev/sdb3
pvdisplay 
```

## Schritt 3: Volume Group erstellen (vg) 

```
vgcreate vg1 /dev/sdb2 /dev/sdb3
vgdisplay
```

## Schritt 4: Logical Volume erstellen (lv) 

```
lvcreate -n data -L5G vg1
lvdisplay
```

## Schritt 5: filesystem aufbringen (ext4) und probehalber mounten 

```
mkfs.ext4 /dev/vg1/data
mkdir -p /mnt/lvmplatte
mount /dev/vg1/data /mnt/lvmplatte
```

## Schritt 6: /etc/fstab 

```
umount /mnt/lvmplatte
# vi /etc/fstab 
/dev/vg1/data /mnt/lvmplatte  ext4  defaults 0 1 

mount -av

reboot 

# teste, ist platte wieder eingehängt


```

## Schritt 7: Vergrößern des Logical Volumes 

```
# Voraussetzung, ausreichend Speicher in der volumegroup 
# oder dazufügen
# 1. neue partition erstellen (auch auf komplett neuer Platte möglich) 
# 2. pvcreate /dev/sdb1 
# 3. vgextend vg /dev/sdb1 

# --resizefs
sudo lvresize -L +200M --resizefs vg0/data

```

## Fall 2: logical volume erweitern 

```
# gleich mit Erweiterung des Filesystems 
lvextend --resizefs -l +100%FREE /dev/mapper/ubuntu--vg-ubuntu--lv

```


## Reference:

   
  * lvresize: https://www.digitalocean.com/community/tutorials/how-to-use-lvm-to-manage-storage-devices-on-ubuntu-18-04
