# Gepackte Datei anzeigen

## zcat 

```
zcat /var/log/syslog.2.gz 
```

## Datei zu komprimieren

```
cp -a /etc/services /root/servicecopy
cd /root
# produces servicecopy.gz 
gzip servicecopy 

# Version 2
cat servicecopy | gzip > servicecopy.gz 
# mysqldump | gzip > dump.sql.gz 
```
