# apt und dpkg 

## Alle Pakete anzeigen, die installiert sind auf dem System 

```
dpkg -l 
# oder 
apt list --installed
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

## Pakete händisch mit dpkg installieren 

```
# Schritt 1: Im Browser
# Paket online finden und Link kopieren (Browser - Rechte Mauataste Link kopieren) 

# Schritt 2: auf dem Linux Server
sudo apt install wget
cd /usr/src
wget http://archive.ubuntu.com/ubuntu/pool/main/a/acl/acl_2.2.53-10build1_amd64.deb
sudo dpkg -i acl_2.2.53-10build1_amd64.deb
```

## Pakete mit apt search suchen 

```
# Vorbereitung
apt update

# suche nache apache 
apt search apache 
# mit pager
apt search apache | less 

# Alle Paket in denen apache am Anfang der Zeile fehlt 
apt search ^apache | less

```

# Installieren mit apt install 

```
# mit genauem Namen 
apt install apache2 
```
