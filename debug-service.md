# Debug Service 

## Walkthrough 

```
# Dienst startet nicht 

# Schritt 1 : status -> was sagen die logs (letzte 10 Zeilen) 
systemctl status mariadb.service 

# Nicht fündig-> Schritt 2:
jourrnalctl -xe

# Nicht fündig -> Schritt 3:
journalctl -u mariadb.service 

# Nicht fündig -> Schritt 4:
# Spezifisches Log von Dienst suchen 
# und evtl. LogLevel von Dienst hochsetzen
# z.B. bei mariadb (durch Internetrecherche herausfinden) 
less /var/log/mysql/error.log 

# Nicht fündig -> Schritt 5
# Allgemeines Log
# Debian/Ubuntu 
/var/log/syslog
# REdhat/Centos 
/var/log/messages 


```

## Find error in logs quickly

```
cd /var/log/mysql 
cat error.log | grep -i error
```

