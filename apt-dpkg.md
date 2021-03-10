# apt und dpkg 

## Alle Pakete anzeigen, die installiert sind auf dem System 

```
dpkg -l 
```

## Alle Paket die zur Verfügung stehen 

```
apt list 
```

## Wo sind die Repos konfiguriert 

```
cat /etc/apt/sources.list 
cd /etc/apt/sources.list.d 
```


## Paket deinstallieren und aufräumen 

```
# mit konfigurationsdateien deinstallieren
apt purge mariadb-server 
# konfgiurationsdateien stehen lassen
apt remove mariadb-server 

# Aufräumen / alle Pakete die nicht mehr benötigt werden
apt autoremove 
```
