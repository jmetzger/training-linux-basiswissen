# Best practice structure 

## File 1: config.sh 

```
# vi /usr/local/bin/config.sh
LOGTO=/var/log/logme
DATUM=$(date) 
```

## File 2: functions.sh 

```
# vi /usr/local/bin/functions.sh
function logto {
  # echo "hello jochen"
  date >> $LOGTO
  echo "hello jochen: $1" >> $LOGTO
}
```

## File 3: script.sh 

```
# vi /usr/local/bin/script.sh
#!/bin/bash
  
source /usr/local/bin/config.sh
source /usr/local/bin/functions.sh


logto 'Hans hat Glück'
echo "----"
cat $LOGTO
echo $LOGTO 
echo $DATUM

```

```
chmod u+x script.sh
script.sh
```
