# Logrotate 

## Was macht es ?

```
Rotiert die Logs täglich auf Basis einer config unter /etc/logrotate.d
```

## Beispiel 

```
# Ziel 
# Rotieren von log unter /var/log/script.log 
cd /etc/logrotate.d 
nano script 
```

```
/var/log/script.log {
    daily
    missingok
    rotate 14
    compress
    delaycompress
    notifempty
    create 640 root root
}
```

```
# testen 
# -f forced das ganze 
logrotate -f /etc/logrotate.conf 

# Jetzt werden die logs unter /var/log rotiert, auch script 
```

## Anzeigen von gepackten 

```
# d.h. alle Dateien mit der Endung .gz 
# z.B. dmesg.1.gz 
# zcat wird mit gzip mitinstalliert 
zcat dmesg.1.gz 
```
