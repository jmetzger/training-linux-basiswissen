# Beispiel einer Funktion 

```
vi /usr/local/bin/functiontest.sh
```

```
#!/bin/bash

LOGTO=/var/log/logme

function logto {
  date >> $LOGTO
  echo "hello : $1" >> $LOGTO
}

logto 'Hans hat Glück'
echo "----"
cat $LOGTO
```

```
chmod u+x /usr/local/bin/functiontest.sh  
# im script wird Funktion aufgerufen 
functiontest.sh
```

