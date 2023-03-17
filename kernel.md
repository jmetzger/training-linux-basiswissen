# Kernel Knowledge 

## Welcher Kernel läuft 

```
uname -a 
```

## Rebooten nach kernel update 

```
# Wenn nach einem Update ein neuer Kernel installiert wurde,
muss das System auch rebootet werden, damit dieser verwendet wird.

# Ausnahme 
ubuntu live-patching -> hier wird zwar direkt die neuen Version 
verwendet (ist aber voodoo und der richtige Kernel -> dafür 
muss man auch neu starten)

```

## Kernelmodule 

```
# geladene Kernel-Module anzeigen
lsmod 
# Achtung: entladen eines essentiellen Kernel-Modules führt
# führt zum Stillstand 
# kernel modul entladen
rmmod joydey

# Neu laden mit modprobe -v (nicht insmod) 
# Weil dann gleich die Abhängigkeiten mit berücksichtigt werden
modprobe -v joydey

# Jeder Kernel hat seine eigenen Kernel-Module
# Diese wurden für den neuen Kernel neu kompiliert 
# Befinden sich unter 
# /lib/modules/<kernel-version>
```
