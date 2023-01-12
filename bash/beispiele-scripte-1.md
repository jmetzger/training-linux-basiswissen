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

## Beispiel 2: for mit befehl und Konfig-Datei 

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

## Beispiel 3: mit Übergabe parameter 

```
vi /usr/local/bin/dirmaker.sh
```

```
#!/bin/bash

#echo $0
#echo $1
# echo $#

if test "$1" = ""
then
  read -p "Verzeichnisname?" VERZ
else
  VERZ=$1
  echo $VERZ
fi


if test ! -d /tmp/$VERZ
then
  echo "Verzeichnis /tmp/$VERZ existiert nicht"
  echo "..."
  echo "... wird angelegt"
  mkdir /tmp/$VERZ

else
  echo "Verzeichnis /tmp/$VERZ existiert. Punkt !"
  ls -la /tmp/$VERZ
fi

