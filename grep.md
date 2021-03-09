# Grep 

## Beispiele 

```
# alle Zeilen in den tcp vorkommt 
cat /etc/services | grep tcp 
# alle Zeilen in denen tcp nicht vorkommt
cat /etc/services | grep -v tcp 
# alle Zeilen in denen tcp nicht vorkommt
# egal ob gross oder klein geschrieben.
cat /etc/services | grep -iv TCP 

cat /etc/services | grep '#'
cat /etc/services | grep "#"
cat /etc/services | grep "^#"
# alle Zeilen, die am Anfang der Zeile kein # haben 
cat /etc/services | grep -v "^#"
cat /etc/services | grep -v "^#" > /root/services
cat /etc/services | grep -v "^#" | head -n 20

cat /etc/services | grep -v "s$"
# alle Zeilen die als letztes Zeichen ein s haben 
cat /etc/services | grep  "s$"

```
