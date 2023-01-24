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
# Ministep 2.1 
systemctl list-units -t service 
systemctl list-units -t service | grep apache



```
