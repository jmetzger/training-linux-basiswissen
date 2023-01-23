# Enable sudo for user 

## Benutzer zum Sudo benutzer machen

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
