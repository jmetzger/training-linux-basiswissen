# Backups mit tar 

## Sichern 

```
tar cvfz /usr/src/_etc.20220522.tar.gz /etc 

```

# Liste der Dateien aus Archiv anzeigen

```
tar tf /usr/src/_etc.20220522.tar.gz 

# Gibt es die Datei ? 
tar tf /usr/src/_etc.20220522.tar.gz /etc/skel/.bashrc 

```

# Dateien aus Archiv entpacken 

```
mkdir auspackverzeichnis
cp -a _etc.20220522.tar.gz auspackverzeichnis 
cd auspacksverzeichins 
tar xvf /usr/src/_etc.20220522.tar.gz 

# Einzelne Dateien  
tar xvf /usr/src/_etc.20220522.tar.gz /etc/skel/.bashrc 

```

