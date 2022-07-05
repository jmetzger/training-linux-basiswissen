# Script mit systemctl verwalten inkl. Environment-Variables 

## Schritt 1: Script erstellen 

```
#!/bin/bash 
# vi /usr/local/bin/script-ng.sh
echo "script script-ng schreibt was ins log...." 
env
date >> /var/log/script-ng.sh
env >> /var/log/script-ng.sh

```

```
chmod u+x /usr/local/bin/script-ng.sh 
script-ng.sh 
# Sichtprüfung im Log
cat /var/log/script-ng.sh 
```
