# Dateien und Verzeichnisse löschen 

## Dateien und Verzeichnisse löschen 

```
# bei symbolischen Links wird nur der symbolische Link und nicht die Datei gelöscht 
rm symlink 
# Datei löschen 
rm dateiname 
# Verzeichnis löschen 
rm -r verzeichnis 
```

## Mehrere Dateien löschen 

```
cd 
touch datei1 datei2 datei3
echo datei* 
rm datei*
```


## Symbolische Links löschen (Verhalten) 

```
cd
touch woche.txt 
ln -s woche.txt woche1.txt
# file woche.txt is still present
rm woche1.txt
ls -la
# Symbolischen Link erneut setzen 
ln -s woche.txt woche1.txt
# Symbolischer Link danach kaputt
rm woche.txt
ls -la
# woche1.txt nicht aufrufbar, da der symbolische Link ins Leere zeigt. 
cat woche1.txt

```
