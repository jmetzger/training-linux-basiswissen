# Systemctl / Service 

## systemctl Beispiele 
```
# Status eines Dienstes überprüfen 
service sshd status 
systemctl status sshd 

# Wie heisst der Dienst / welche Dienste gibt es ? 
systemctl list-units -t service 
# für apache
systemctl list-units -t service | grep ^apache
# die Abkürzung 
systemctl -t service | grep ^apache


# Dienst aktivieren
systemctl enable apache2 
# Ist Dienst aktiviert 
systemctl is-enabled apache2
enabled
echo $?
0 # Wenn der Dienst aktiviert ist 

# Dienst deaktivieren (nach Booten nicht starten)
systemctl disable apache2
systemctl is-enabled 
disabled
echo $?
1 # 1 wenn nicht aktiviert

# Rebooten des Servers
# verweist auf systemctl 
reboot
systemctl reboot
shutdown -r now  

# Halt (ohne Strom ausschalten) 
halt
systemctl halt 
shutdown -h now 

# Poweroff 
poweroff
systemctl poweroff 
```

## Wie sehe ich, wie ein Service konfiguriert ist ? 

```
# z.B. für Apache2
systemctl cat apache2.service
```

## Welche Dienste sind aktiviert/deaktiviert 
```
systemctl list-unit-files -t service
```

## Dienstekonfiguration anzeigen 

```
systemctl cat sshd.service 
```

## Dienste bearbeiten 
```
systemctl edit sshd.service 
# Dann eintragen
[Unit]
Description=Jochen's ssh-server 
# Dann speichern und schliessen (Editor) 

systemctl daemon-reload 
systemctl status 
```

## Targets (wechseln und default) 

```
# Default runlevel/target auslesen 
systemctl get-default 
# in target wechseln 
systemctl isolate multi-user 
# Default target setzen (nach start/reboot) 
systemctl set-default multi-user 
```

## Alle Target anzeigen in die ich reinwechseln kann (isolate) 

```
# Ubuntu 
grep -r "AllowIsolate" /lib/systemd/system 
/lib/systemd/system/reboot.target
...
...
...
systemctl isolate reboot.target 
```

## Dienste maskieren, so dass sie nicht gestartet werden können 

```
systemctl mask apache2
# kann jetzt gestartet werden
systemctl start apache2

# de-maskieren 
systemctl unmask apache2 
# kann wieder gestaret werden
systemctl start apache2
```

## systemctl Cheatsheet 

  * https://access.redhat.com/sites/default/files/attachments/12052018_systemd_6.pdf



