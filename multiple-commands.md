# Mehrere Befehle ausführen 

```
# Beide Befehle ausführen, auch wenn der 1. fehlschlägt 
befehl1; apt upgrade

# 2. Befehl nur ausführen, wenn 1. erfolgreich war.
apt update && apt upgrade 

# 2. Befehl nur ausführen, wenn der 1. NICHT erfolgreich war 
# befehl1 oder befehlt2 (im weitesten Sinne) 
befehl1 || befehl2
```
