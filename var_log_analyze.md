# Logfile unter /var/log analysieren

## Beispiel syslog 

```
cd /var/log 
# Achtung: Problem bei zu grossen Logfiles 
# d.h. z.B. 2-3 GB, weil alles erst in den Arbeitsspeicher geladet 
less syslog 

## Alternative 
## nur 10.000 letzte Zeilen auswerten
tail -n 10000 syslog | less 
tail -n 10000 syslog > meinlog 
less meinlog 

## Alternative Level 2 (gleich mit filtern) 
tail -n 10000 syslog | grep ssh | less 

```
