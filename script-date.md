# Einfaches Script zur Datumsausgabe 

## Beliebiges Verzeichnis 

```
# Mit nano öffnen / datei muss vorher nicht vorhanden sein
# nano script.sh 
# Folgendes muss drin stehen, mit 1. Zeile beginnend mit # 

#!/bin/bash 
date 

# Speichern CRTL + O -> RETURN, CTRL X 

# Ausführbar machen 
chmod u+x script.sh
./script.sh # Ausführen und wohlfühlen 

```

## Besser: /usr/local/bin 

### Gründe 

 * Wird gefunden, egal in welchem Verzeichnis ich bin ?
 * Warum ? Weil /usr/local/bin Teil der PATH-Variablen ist 

### Beispiel 

```
cd /usr/local/bin 
# Mit nano öffnen / datei muss vorher nicht vorhanden sein
# nano script.sh 
# Folgendes muss drin stehen, mit 1. Zeile beginnend mit # 

#!/bin/bash 
date 

# Speichern CRTL + O -> RETURN, CTRL X 

# Ausführbar machen 
chmod u+x script.sh

# z.B. 
cd /etc
# Script wird ausführt, weil die bash es im Verzeichnis /usr/local/bin findet
# anhand von $PATH 
echo $PATH
env 
script.sh
```
