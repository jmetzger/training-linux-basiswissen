# Beispiel eines Timers zum Üben 

## Schritt 1: script erstellen und testen

```
vi /usr/local/bin/scriptv2.sh
```

```
#!/bin/bash 
LOGTO=/var/log/scriptv2.log
echo "script script-ng schreibt was ins log...." 
env
date >> $LOGTO
env >> $LOGTO
```

```
chmod u+x /usr/local/bin/scriptv2.sh
scriptv2.sh
```

## Schritt 2: Service erstellen und testen 

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

```
systemctl status scriptv2
systemctl start scriptv2
systemctl status scriptv2
```

## Schritt 3: Timer erstellen und testen 

```
# systemctl edit --force --full scriptv2.timer
[Unit]
Description=Timer for scriptv2
[Timer]
OnCalendar=*:0/5

[Install]
WantedBy=basic.target
```

```
systemctl enable scriptv2.timer

systemctl status scriptv2.timer
systemctl start scriptv2.timer
systemctl status scriptv2.timer

systemctl list-timers
```
