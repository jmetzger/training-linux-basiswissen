# Parted and mkfs 

## Walkthrough 

```
# Schritt 1: Platte in virtualbox oder gui-interface anlegen 

# Schritt 2: Platte identifizieren
lsblk 

# Schritt 3: Platte partitionieren 
mkpart /dev/sdb1
mklabel gpt
mkpart data2 ext4 2048s 500M # data2 ist name der Partition bei gpt 
quit 

# Schritt 4: Partition formatiert 
lsblk # Partition identfiziert 
mkfs.ext4 /dev/sdb1 

# Schritt 5: Mount-Punkt erstellen 
mkdir /mnt/platte

# Schritt 6: einhängen und aushängen
mount /dev/sdb1 /mnt/platte 
# Add-on: Eingehängte Partitionen anzeigen 
mount 

# Aushängen 
umount /mnt/platte 

# Schritt 7: Persistent konfiguriren
# Eintragen in /etc/fstab
/dev/sdb1 /mnt/platte ext4 defaults 0 0 

# Schritt 8: Test, ob fstab gut ist (keine Fehler) 
mount -av # v steht für geschwätzig.

# Wenn das klappt: Schritt 9 
reboot

# Nach dem Rebooten 
mount | grep platte  # taucht platte hier auf ? 

```
