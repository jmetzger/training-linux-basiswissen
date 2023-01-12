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
