# Große Logs analysieren 

## Wichtigste Regel 

```
Ausgabe möglichst lange aufschieben
und
vorher schon mit Tools verkleinern
```

## Beispiele 

```
# Bestimmter Tag mit Uhrzeit und dann alle Fehler rausextrahieren 
cd /var/logs 
cat messages | grep "Feb 23 13" | grep -i "error" > report-error.log
```
