# dnf

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
