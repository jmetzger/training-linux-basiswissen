# Dateien mit scp übertragen 

```
cd
ls -la > testdatei

# testdatei aufs Zielsystem übertragen
scp testdatei 11trainingdo@134.122.81.88:/home/11trainingdo/
# Prüfen ob dort gelandet 
ssh 11trainingdo@134.122.81.88

# Datei vom Zielsystem herunterladen und unter anderem Namen speichern 
scp 11trainingdo@134.122.81.88:/home/11trainingdo/testdatei /tmp/foodatei

```
