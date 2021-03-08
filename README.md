# Linux Basiswissen 

## Agenda 

  1. [Verzeichnisaufbau](verzeichnisaufbau.md) 
     1. [Dateitypen](dateitypen.md) 
  3. [Basisbefehle](basisbefehle.md)
     1. [In den Root-Benutzer wechseln](sudo.md)  
     1. [Wo bin ich ?](pwd.md)
     1. [Praktische Ausgabe von langen Seite - less](less.md) 
  4. Prozesse 
     [Prozesse anzeigen - ps/pstree -p](prozesse.md)
  1. [Hilfe zu Befehlen](help.md)
  1. [Literatur](literatur.md) 

## Verzeichnisse in Listenansicht mit versteckten Dateien anzeigen

```
ls -la 
```

## Ins Heimatverzeichnis und Wurzelverzeichnis (C: unter Windows) wechseln 

```
# Ins Heimatverzeichnis wechseln 
# cd ohne alles 
cd 

# Ins Wurzelverzeichnis 
cd / 
```

## Wie in ein Verzeichnis wechseln (relativ und absolut) 

```
# relativ - nur in ein Unterverzeichnis meines bestehenden Verzeichnisses
cd etc 

# absolut - welchselt dort rein, egal wo ich bin 
cd /etc 
```

