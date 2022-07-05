# Journalctl 

## Journal für eine bestimmte unit anzeigen 

```
journalctl -u ssh.service 
journalctl -u ssh.service -e --since "2022-07-05 08:00" --until "2022-07-05 09:00"
```

## Show all boots 

``` 
journalctl --list-boots
 0 3c3cf780186642ae9741b3d3811e95da Tue 2020-11-24 14:29:44 CET▒<80><94>T>
lines 1-1/1 (END)
```

## Show boot log 

```
journalctl -b 
```


## Journal persistent 

  * Normalerweise (auf den meisten Systemen), überlebt das Journal kein Reboot 
 
```
# persistent setzen
# Achtung: in /etc/systemd/journald.conf muss Storage=auto gesetzt sein
# Dies ist auch der Default - Fall 
# Achtung Achtung: Alle gezeigten Einträge mit # am Anfang sind die Default-Werte (in journald.conf) 
mkdir /var/log/journal 
systemctl restart systemd-journal-flush.service 

```

## Restrict how much is logged / data 

```
# in /etc/systemd/journald.conf 
SystemMaxUse=1G 
```

## journalctl 

```
# ubuntu
journalctl -u ssh 
```

## Show journalctl for specific Field 

```
# Hilfreich Damit man die Felder 
journalctl -o json-pretty
journalctl _PID=1 # show all entries for systemd - command startet as first program after kernel is loaded
journalctl _UID=120 # show all log entries for specific user 
```

## Welche Hilfe gibt es ?

```
man journald.conf 
man journalctl 
man systemd.journal-fields
```
