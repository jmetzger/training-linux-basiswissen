# Beispiel einer Funktion 

```
#!/bin/bash
# vi /usr/local/bin/functiontest.sh
# chmod u+x /usr/local/bin/functiontest.sh  

LOGTO=/var/log/logme

function logto {
  # echo "hello jochen"
  date >> $LOGTO
  echo "hello jochen: $1" >> $LOGTO
}

logto 'Hans hat Glück'
echo "----"
cat $LOGTO
```

```
# im script wird Funktion aufgerufen 
functiontest.sh
```
