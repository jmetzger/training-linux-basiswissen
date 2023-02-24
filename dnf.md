# dnf

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
