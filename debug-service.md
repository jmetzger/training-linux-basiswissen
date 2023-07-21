# Debug Service 

## Vorbereiten für Training -> Fehler einbauen 

```
# falsche Konfigurationeinstellung in
/etc/mysql/mariadb.d/50-server.cnf unter
[mysqld]
z.B.
sonnenschirm

eintragen 
```

## Walkthrough 

```
# Dienst startet nicht / nach Ausführen von systemctl restart wird Fehlermeldung ausgegeben
systemctl restart mariadb.service 

# Schritt 1 : status -> was sagen die logs (letzte 10 Zeilen) 
systemctl status mariadb.service 

# Nicht fündig-> Schritt 2:
jourrnalctl -xeu mariadb.service 

# Nicht fündig -> Schritt 3:
# Spezifisches Log von Dienst suchen 
# und evtl. LogLevel von Dienst hochsetzen
# z.B. bei mariadb (durch Internetrecherche herausfinden) 
less /var/log/mysql/error.log 

# Nicht fündig -> Schritt 5
# Allgemeines Log
# Debian/Ubuntu 
/var/log/syslog
# REdhat/Centos & SLES (OpenSuSE) 
/var/log/messages 
```

## Wie verfahren bei SystemV 

```
Wie bei walkthrough aber ab Schritt 4
```

## Find error in logs quickly

```
cd /var/log/mysql 
# -i = case insensitive // egal ob gross- oder kleingeschrieben
cat error.log | grep -i error
```

## Schweizer Taschenmesser der Suche 


```
# Fehler ist gummitulpe - option - falsch in Konfigurationsdatei, aber wo ? 
grep -r gummitulpe /etc
# mit zeilennummer 
grep -nr gummitulpe /etc
# mit zeilennummer und egal ob gross oder kleingeschrieben 
grep -inr GUMMITULPE /etc
```
