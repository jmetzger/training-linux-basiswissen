# Rechte 

## Arten 

```
r = Lesen 
w = Schreiben
x = Ausführen 
```

## Aufbau triple 

```
kurs@ubuntu2004-101:~$ # rwx | rw- | r--
kurs@ubuntu2004-101:~$ #  u    g      o
kurs@ubuntu2004-101:~$ # 421 | 42- | 4--
kurs@ubuntu2004-101:~$ #  7  |  6  | 4

# rwx | rw- | r--
#  u    g      o
# 421 | 42- | 4--
#  7  |  6  | 4
```

## Bedeutung Oktalzahlen 

```
# rwx 
# r = 4, w = 2, x = 1
```

## Beispiele 

```
- w -  
0 2 0  = 020 
```


## Berechtigungen mit Symbolen setzen 

```
chmod g+w,o+r testfile
```

## Die Maske als Basis für neue Dateien 

```
# als kurs benutzer automatisch so gesetzt für alle unpriviligierten
umask 
0002 

# als Basis für Dateien 
   6 6 6 
-  0 0 2
========
   6 6 4 - neue Dateien werden mit 664 angelegt 
   
# als Basis für Verzeichnisse
   7 7 7
-  0 0 2
========
   7 7 5 - neue Dateien werden mit 664 angelegt


```
