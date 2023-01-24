# Aktualisierung des Systems 

```
apt update
apt upgrade 
apt dist-upgrade
# alte Pakete, die nicht mehr als Abhängigkeit benötigt werden, entfernen 
apt autoremove

# oder geht auch auf älteren Systemen
apt-get update
apt-get upgrade
apt-get dist-upgrade
apt-get autoremove 


# Achtung: Evtl. ist noch ein Reboot aufgrund eines Kernel Upgrades notwendig.
# Vergleichen von  
cd /boot
ls -la vm*

# zeigt den geladenen Kernel 
uname -a 

# Gibt es im Filesystem unter boot einen neueren Kernel als mit uname -a
# muss ! zeitnah neu gebootet werden.

```
