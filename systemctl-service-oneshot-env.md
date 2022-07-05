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

## Schritt 2: service ohne env erstellen.

```
# --force weil datei nicht existiert.
# --full eine vollständige service-datei und nicht überschwierig 
systemctl edit --full --force script.service 
```

```
[Unit]
Description=script von jochen

[Service]
Type=oneshot
ExecStart=/usr/local/bin/script-ng.sh
RemainAfterExit=true
StandardOutput=journal

[Install]
WantedBy=multi-user.target

```

```
# editor speichern und schliessen
```

## Referenz:

  * https://gist.github.com/drmalex07/d006f12914b21198ee43
