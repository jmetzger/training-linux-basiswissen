# Cheatsheet Befehle 

## Bewegungskommandos und Dateimanipulation 

```
cd 
ls -la
# Anlegen verzeichnis 
mkdir 
# wo bind ich
pwd
# kopieren 
cp -a

# datei löschen 
rm dateiname
```

## Unix Tools 

```
cat /etc/passwd 
cat /etc/passwd | grep root
# Zeilen zählen 
cat /etc/passwd | wc -l 
```

## Bearbeitung 

```
vi dateiname 
# datei reinschreiben 
# anhängen 
echo "neue Zeile" >> dateiname 
```


## Pakete installieren 

```
dnf search <such-pattern>
dnf list httpd
dnf install httpd 
```

## Services 

```
systemctl status sshd 
systemctl reload sshd
systemctl restart sshd 
systemctl enable sshd 
systmectl cat sshd 

# journal 
journalctl -u sshd.service 
```

## User

```
# user anlegen 
adduser username
# Passwort setzen 
passwd username 
# Gruppe anlegen 
groupadd sshadmin 
# Weitere Gruppe user hinzufügen 
usermod -aG sshadmin username 
```

## Berechtigungen 

```
# Besitzer darf Berechtigungen ändern 
chmod u+x script.sh 
chmod 444 dateiname 

# Besitzerrechte geändert, darf nur root
chown username dateiname 
```





