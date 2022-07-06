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
