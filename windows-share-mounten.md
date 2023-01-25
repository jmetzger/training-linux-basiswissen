# Windows Share mounten 

## Walkthrough 

```
apt install cifs-utils 
#  danach muss mount.cifs zur Verfügung stehen 

# Unser Windows: Windows Share erstellen für entsprechen Nutzer zB Admin
# Wenn keine Auflösung des Hostnamens auf Windows erfolgen kann, dann IP rausfinden
# WIN + cmd -> cmd.exe 
# ipconfig 

# Ein Mountpunkt erstellt
mkdir /mnt/windows 

# und dann einhängen 
mount.cifs //10.10.11.116/Users/Admin /mnt/windows -o username=Admin,password='mein@P@dss!$?'

# Jetzt stehen die Daten unter 
# /mnt/windows zur Verfügung 
cd /mnt/windows
ls -la 
```

```
# /etc/fstab 
//10.10.11.116/Users/Admin /mnt/platte2 cifs username=Admin,password=mein@P@dss!$? 0 0 
```

```
# testen von /etc/fstab
mount -av
```
