# Enable sudo for user 

## Benutzer zum Sudo benutzer machen (Redhat RHEL, Rocky Linux) 

```
sudo su -
adduser newuser
## passwort setzten
passwd newuser 

## append - hinzufügen zu der Gruppe 
usermod -aG wheel newuser
## testing 
su - newuser
groups # see if we are in groups sudo 
id # shows the same but more info 

## testen ob sudo funktioniert 
sudo su -
```


## Benutzer zum Sudo benutzer machen (Debian/Ubuntu) 

```
adduser newuser
## append - hinzufügen zu der Gruppe 
usermod -aG sudo newuser
## testing 
su - newuser
groups # see if we are in groups sudo 
id # shows the same but more info 
# need to enter password here 
sudo su -
```
