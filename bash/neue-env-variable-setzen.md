# Umgebungsvariable setzen 

## example 

```
sudo su -
cd 
# root-verzeichnis /root 
pwd 
echo "export NACHNAME=Mustermann" >> .bashrc

## testen - neu als root einloggen  
su -
# Jetzt müsste NACHNAME in den Umgebungsvariablen zu sehen sein 
env 
```
