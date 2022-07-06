# Beispiel eines Timers zum Üben 


```
#!/bin/bash 
# vi /usr/local/bin/scriptv2.sh
LOGTO=/var/log/scriptv2.log
echo "script script-ng schreibt was ins log...." 
env
date >> $LOGTO
env >> $LOGTO
```

```
chmod u+x /usr/local/bin/scriptv2.sh
```

```
# systemctl edit --force --full scriptv2.service 
[Unit]
Description=simple script for testing timer 
[Service]
Type=oneshot
ExecStart=/usr/local/bin/scriptv2.sh
#RemainAfterExit=true
StandardOutput=journal
```

````
systemctl status scriptv2
systemctl start scriptv2
systemctl status scriptv2
```
