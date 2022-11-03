# ssh absichern 

## Walkthrough 


```
# Schritt 1: 
# nano /etc/ssh/sshd_config 
# ganz unten hinzufügeb 
AllowGroups sshadmin 
```
``
# wichtig !! auch der root-Benutzer, muss dann der Gruppe angehören
# sollte ich mich mit dem Root-Benutzer über public/private key verbinden 


```
# Schritt 2: 
# Jeden Benutzer der sich mit ssh verbinden können soll, der Gruppe sshadmin hinzfügen 
usermod -aG sshadmin kurs 

```

```
# Schritt 3:
systemctl restart sshd 
```

## Achtung: /etc/ssh/sshd_config.d 

```
Diese Dateien überschreiben die config aus /etc/ssh/sshd_config 
```
