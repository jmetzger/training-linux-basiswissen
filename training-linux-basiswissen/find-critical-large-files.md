# Wie finde ich das Programm das mein Filesystem gerade voll macht ?

## Schritt 1: Datei identifizieren durch Suche 

```
# Variante 1: 
# Welche Partition ist betroffen 
# -h human readable, m megabytes 
df -hm /var 

# Variante 2:
# Zeigt alle verzeichnisse mit verwendeter Größe an 
du -hm /var 
# auch nochmal sichtbar des großen betroffenen Verzeichnisses 
```

```
ls -la /var/lib/snapd/snaps
total 399368
drwxr-xr-x  3 root root      4096 Jan 25 04:49 .
drwxr-xr-x 22 root root      4096 Jan 25 04:54 ..
-rw-------  2 root root  64970752 Aug  9 11:58 core20_1587.snap
-rw-------  1 root root  66347008 Jan 23 10:22 core20_1778.snap
-rw-------  1 root root 107986944 Jan 23 10:22 lxd_23541.snap
-rw-------  1 root root 117387264 Jan 25 04:49 lxd_24322.snap
drwxr-xr-x  2 root root      4096 Aug  8 09:17 partial
-rw-------  1 root root  52248576 Jan 23 10:22 snapd_17950.snap
```

```
# Variante 3: Gezielt nach Dateien suchen, die größer sind als z.B. 2M 
find /var -type f -size +2M -exec ls -la {} \;
```

## Schritt 2: Welche Programm verursacht das ? 

```
## Minischritt 1:
# zeige das programm, welche in syslog schreibt 
fuser /var/log/syslog 
# process id rausbekommen 
# /var/log/syslog:     112920

## Minischritt 2: wie wollen den Prozess haben -> d.h. welches programm
ps -ef | grep 112920
# Ergebnis 
syslog    112920       1  0 Jan24 ?        00:00:00 /usr/sbin/rsyslogd -n -iNONE

## Minischritt 3: Finde heraus, ob ein Dienst (Service) startet 
# Dienste in /usr/lib/systemd/system /lib/systemd/system /etc/systemd/system definiert 
# in Konfigurations
grep -r rsyslogd /usr/lib/systemd/system 
grep -r rsyslogd /lib/systemd/system 
grep -r rsyslogd /etc/systemd/system 
```

