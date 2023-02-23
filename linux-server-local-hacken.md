# Linux Server Local hacken 

## Steps 

```
1) System gebootet und mit F2 bzw. F12 in den bootmanager gewechselt
2) Dann: Pfeiltasten nach unten 1x kurz drücken, damit Count-Down aufhört 
3) e gedrückt  und in der Zeile linux und dann init=/bin/bash eingefügt (Achtung englische Tastatur) 
4) System gestartet mit CRTL+x 

## Sobald bash zu sehen als root-Benutzer system readwrite
mount -o remount,rw / 
## Jetzt können wir Änderungen vornehmen 
## Passwort für root ändern 
passwd

## Achtung bei Red Hat auf jeden Fall noch ein /.autorelabel erstellen
touch /.autorelabel 

## System ausschalten -> reboot funktioniert nicht, da systemd nicht läuft. 

## starten
starten des system


```


