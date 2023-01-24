# Dienst installieren und starten 

## Step 1: Suchen und installieren (Ubuntu / Debian) 

```
apt update 
# Suchergebnis und eine zusätzliche Zeile finden 
apt search apache | grep -A 1 ^apache
# Abhängige Paket (weitere) ohne Nachfrage installieren 
apt install -y apache2 
```

## Step 1: Suchen und installieren (OpenSuSE) 

```
zypper search apache2 
zypper install -y apache2 
```

## Step 2: Dienstnamen herausfinden (weil nicht gestartet -> SLES/OpenSuSE) 

```
# Ministep 2.1 - Dienstnamen rausfinden
systemctl list-units -t service 
systemctl list-units -t service | grep apache

# Ministep 2.2 - Status abfragen
systemctl status apache2.service 

# Ministep 2.3. - Dienst starten (kein Problem, wenn er bereits läuft) 
systemctl start apache2.service 

# Ministep 2.4 - Is Autostart aktiviert ? und.. autostart aktivieren
systemctl is-enabled apache2.service 
systemctl enable apache2.service 




```
