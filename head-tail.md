# Anfang und Ende einer Datei / Ausgabe anzeigen

## Die ersten 10 
```
# die ersten 10 Zeilen einer Datei anzeigen 
head /etc/services 
# Alternative 1 
cat /etc/services | head

# die letzten 10 Zeilen 
tail /etc/services 
cat /etc/services | tail 

# einer ausgabe // erste 10 Zeilen eines Verzeichnislistings  
ls -la | head 

```

## Die ersten 20

```
head -n 20 /etc/services 
head -n20 /etc/services 
head -20 /etc/services 
head --lines=20 /etc/services

```

## Die letzten 20 

```
tail -n 20 /etc/services 
tail -n20 /etc/services 
tail -20 /etc/services 
tail --lines=20 /etc/services
```
