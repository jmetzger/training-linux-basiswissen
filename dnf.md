# dnf

## Befehle cheatsheet

```
# alle repos anzeigen
dnf repolist all

# alle verfügbaren Pakete anzeigen
dnf list available | less

# alle installierten Pakete anzeigen
dnf list installed 

# paket installieren
dnf install <paket>

# paket deinstallieren 
dnf remove <paket>

# nach updates suchen 
dnf check-update 

# alle Pakete upgraden 
#  --refresh forces an immediate update of the repository lists.
dnf upgrade --refresh 

# nur ein Paket upgraden
# Abhängigkeiten werden dann auch geupgraded 
dnf upgrade <paketname>
```

## Welches Paket installiert ein Programm 

```
dnf whatprovides lsof 

```

## Versionen von Paketen anzeigen die noch nicht installiert sind 

```
dnf list available php 
```

## Alle vorhandenen module in allen repos 

```
dnf list available --showduplicates php 
```

## Paket aus einem bestimmten installieren

```
dnf install --repo=meinrepo php
```

## Arbeiten mit modulen 

  * Beinhalten jeweils mehrere Installationspakete 

```
dnf module list
# Welche genau Version von php wird installiert 
# Das sehe ich bei den Artifakten, die installiert werden 
# Liste die angezeigt wird.
dnf module info php:8.1 | less

```

## Weitere repos ausser die Distri - Repos, wann ? 

```
# Installiert repos mit zusatzpaket 
dnf search epel-release 

# Spezielle Repos vom Hersteller,
# z.B. mariadb 
https://mariadb.org/download/?t=repo-config&d=Red+Hat+Enterprise+Linux+9&v=10.11&r_m=agdsn
# repo einpflegen
```

## Repos mit dem config-manager anlegen

```
# https://dnf-plugins-core.readthedocs.io/en/latest/config_manager.html
dnf config-manager --add-repo http://example.com/some/additional.repo
```

## Pakete und Abhängigkeiten finden 

```
# best bet 
yum deplist httpd

# dependencies
dnf repoquery --requires <package>
dnf repoquery --requires vim

# recommends
dnf repoquery --recommends httpd

# Download package and check for the dependencies
dnf download httpd 
rpm -qpR httpd-2.4.53-7.el9_1.1.x86_64.rpm

# Extract package contents
mkdir packagecontents; cd packagecontents
rpm2cpio ../httpd-2.4.53-7.el9_1.1.x86_64.rpm | cpio -idmv


```


## bestimmte pakete für upgrade speren 

  * https://www.howtoforge.de/anleitung/wie-man-paket-und-kernel-updates-in-centos-rocky-linux-blockiert/
