# Linux ACL's 

```
# als unpriviligierter Benutzer 
touch datei10
 chmod u=r,g=rw,o= datei10
 sudo chown root:root datei10
# geht nicht 
cat datei10
echo "test" > datei10
sudo setfacl -m u:training:rw datei10
ls -la
getfacl datei10
#  das geht 
echo "data" > datei10
cat datei10
# acl's entfernt 
sudo setfacl -x u:training datei10
ls -la
getfacl datei10
# jetzt geht es wieder nicht
echo "aus" > datei10
cat datei10
```
