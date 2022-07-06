# Einfachen mit Endlos-Schleife bauen 

## Walkthrough 

```
#!/bin/bash
# vi /usr/local/bin/loop.sh 
while /bin/true
do
  date 
  echo "neuer Durchlauf"
  sleep 5
done
```

```
chmod u+x loop.sh
```

```
# systemctl edit --force --full loop.service 
[Unit]
Description=script von jochen

[Service]
Type=simple 
ExecStart=/usr/local/bin/loop.sh

[Install]
WantedBy=multi-user.target
```

```
systemctl status loop
systemctl start loop
systemctl status loop
# Evtl. aktivieren für nächsten reboot
```
