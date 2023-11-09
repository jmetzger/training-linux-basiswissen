# Exercise: Ubuntu: Install apache2 and configure firewalld 

## Teil 1: Port 80 = Service http

```
Übung:

1. Vorbereitung (wg. docker übung)

systemctl stop docker 
systemctl disable docker 

2. apache2 (installieren)

apt install -y apache2 
systemctl status apache2 

3. Aufrufen im Browser (im RDP) 

4. Auf dem Server: lsof -i
(ist der Port offen und kommuiniziert nach draussen -> LISTEN) 

5. firewall-cmd --list-all 

Ist der Dienst zu sehen ? 
Nein ->
6. 

6. 

firewall-cmd --zone=public --add-service=http
firewall-cmd --runtime-to-permanent

```

## Teil 2: Port 82 aktivieren und in firewalld freischalten

```
part 2:

7. port hinzufügen in  /etc/apache2/ports.conf
Listen 82 # Hinzufügen 

8. apache - server neu laden
systemctl reload apache2 

9. Im Browser testen

http://192.168.56.101:82 

-> geht nicht 

10. Überprüfen -> Lauscht nach aussen ?
lsof -i | grep 82 

11. firewall betrachten

# ist hier der port drin
firewall-cmd --list-all

12. port hinzufügen 

# Step1: do it for runtime + test
firewall-cmd --add-port=82/tcp 

13. funktioniert es jetzt im Browser 

Ja.

14.
# Wenn es funktiniert, dann permanent setzen 

# Step 2: on success add to permanent 
firewall-cmd --runtime-to-permanent
```
