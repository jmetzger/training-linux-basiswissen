# Vordefinierte Bash-Variablen

```
cd /usr/local/bin
vi params.sh
```

```
#!/bin/bash
echo "0:"$0
echo "1:"$1
echo "2:"$2
echo "@:"$@
echo '#'$#
echo Hallo heute ist:$(date)

#exit 22
```

```
chmod u+x params.sh
params.sh
```
