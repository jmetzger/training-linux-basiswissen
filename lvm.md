# lvm 

## keine Befehle lvdisplay,vgdisplay etc.

```
apt install lvm2
```


## Schritt 1: Partitionen vorbereiten 

```
# parted /dev/sda 

# partitionen erstellen z.B. 1 und 2 
# 2x mkpart .....
# und ein flag für lvm setzen
(parted) set 1 lvm on
(parted) set 2 lvm on 

quit 
```

## Schritt 2: Physical Volumes vorbereiten (1. lvm Schritt) 

```
pvcreate /dev/sda1 /dev/sda2
pvdisplay 
```

## Schritt 3: Volumen Group erstellen (vg) 

```
vgcreate vg0 /dev/sda1 /dev/sda2
vgdisplay
```

## Schritt 4: Logical Volume erstellen (lv) 

```
lvcreate -n data -L500M vg0
lvdisplay
```

## Schritt 5: filesystem aufbringen (ext4) und probehalber mounten 

```
mkfs.ext4 /dev/vg0/data
mkdir -p /mnt/platte
mount /dev/vg0/data /mnt/platte
```

## Schritt 6: /etc/fstab 

```
umount /mnt/platte
# vi /etc/fstab 
/dev/vg0/data /mnt/platte  ext4  defaults 0 1 

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
sudo lvresize -L +5G --resizefs LVMVolGroup/test


```

