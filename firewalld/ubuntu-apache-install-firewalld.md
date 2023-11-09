# Exercise: Ubuntu: Install apache2 and configure firewalld 

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
