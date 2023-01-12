# Bash Beispiele Scripte 1 

## Beispiel 1: for 

```
cd /usr/local/bin
vi liste.sh
```

```
#!/bin/bash

LISTE="etc dev boot"
for i in $LISTE
do
  ls -la "/$i"
done
```

```
chmod o+x liste.sh
# Testen 
liste.sh 
```

# Beispiel 2: for mit befehl und Konfig-Datei 

```
# vi /etc/liste.conf 
```

```
LOGTO=/var/log/liste.log
```

```
# vi /usr/local/bin/liste.sh
```

```
#!/bin/bash
# DATUM=$(date)
source /etc/liste.conf
echo $LOGTO


LISTE=$(echo $PATH | tr ':' ' ')

for i in $LISTE
do
  ls -la "/$i" >> $LOGTO
done
```

```
chmod o+x /usr/local/bin/liste.sh 
# testen 
liste.sh
```
