# Journalctl 

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
