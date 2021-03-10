# Download and extracting of tar.file 

```
# Walkthrough 
# Schritt 1: Download-Link in Browser kopieren (rechte Maustaste) 

# Schritt 2: 
cd /usr/src 
 # falsche Dateiname -> umbenannt.
wget https://github.com/phayes/geoPHP/tarball/master
mv master master.tar.gz
# Schritt 3: Sicherheitsverzeichnis anlegen und entpacken
mkdir foo
mv master.tar.gz foo
cd foo
tar xvf master.tar.gz
```
