# File - rename/copy/mv 

## Dateien umbenennen, verschieben, kopieren 

```
# wenn Zeilverzeichnis nicht existiert -> Fehler ! 
cp -a todo.txt /dokumente/ 
# wenn zielverzeichnis nicht existiert, wird dokumente2 erstellt als file - > Achtung !! 
cp -a todo.txt /dokumente2 

# umbenennen
mv datei1 neuernamedatei1 

# verschieben in Verzeichnis 
mv datei1 /dokumente/
# besser als:
# mv datei1 /dokumente 
# weil hier die Datei dokumente angelegt wird, wenn der Ordner /dokumente nicht existiert !! 

```

## Rechte behalten bei kopieren

```
# -a macht das 
cp -a todo.txt todoneu.txt 

# ohne -a werden symbolische links aufgelöst und die Rechte das ausführenden gesetzt
cp ab cd 

```
